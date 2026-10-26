# Sr. Meo's Chicken Food House POS

A local-first starter POS web app for a single cashier on a laptop/desktop.

## Included
- Updated Sr. Meo’s circular logo in the login screen, POS header, printed receipts, and closing reports
- Exactly six products: Lechon Manok, Liempo, Lechon Liog, FC15, FC10, Chicken Skin
- Per-piece / whole-unit quantity sales
- Cash, GCash, and other e-wallet payment methods
- IndexedDB persistence in the browser
- Cashier PIN setup and login
- Inventory, prices, costs, and low-stock thresholds
- Received stock history
- Sales history with date/payment filters and CSV export
- Expense tracking
- Daily closing report, cash-count comparison, print / Save as PDF
- Printable/reprintable receipts (browser print dialog)
- JSON backup and restore
- PWA service worker for offline use after first load

## Run locally
Service workers and IndexedDB are best supported on `localhost` or HTTPS. Do not open `index.html` directly with `file://`.

### Option A: Python
1. Extract the ZIP.
2. Open a terminal in the extracted folder.
3. Run:
   `python3 -m http.server 8000`
4. Visit `http://localhost:8000`.

### Option B: Node
Run any static web server from this folder, then open its local URL.

## First launch
1. Set a 4–8 digit cashier PIN.
2. Open Inventory and enter your actual sell prices, unit costs, starting stock, and low-stock thresholds.
3. Make a small test sale and check the report.
4. Download a backup before using it for real transactions.

## Important limitations
- Data lives in the browser profile on this computer. It does not sync to other computers or automatically upload to a cloud database.
- Offline mode works after the first successful load from localhost/HTTPS. If you need online sync across devices, you need a hosted backend/database and authentication.
- The PIN is a basic local access gate, not enterprise-grade security. Anyone with technical access to the browser profile or device may be able to bypass it.
- Backup JSON excludes the PIN hash. Restore replaces operational data but preserves the current PIN.
- Browser data can be lost if site storage is cleared or the device fails. Keep backups in a safe location.
- This starter does not handle tax rules, official BIR-compliant invoicing, supplier accounts payable, refunds/void audit trails, or split payments.
- "Profit after recorded expenses" is an estimate and does not include unrecorded costs. The cash difference compares counted drawer cash against cash sales only; opening float and cash payouts must be accounted for separately.
- No physical printer is required. Receipt/report printing uses the browser's Print dialog; choose "Save as PDF" if you want a digital copy.

## Recommended production step
Before using it as the store's source of truth, test with sample data, verify backup/restore on a second browser profile, and consider a proper cloud database, encrypted backups, audited refunds, and secure account recovery.
