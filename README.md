# ZIA Natural Soap Collection

## Run locally (Windows)
1. Install Python 3.11 or newer.
2. Open PowerShell in this folder.
3. Run: `py -m venv .venv`
4. Run: `.venv\Scripts\Activate.ps1`
5. Run: `python -m pip install -r requirements.txt`
6. Set a development secret: `$env:SECRET_KEY = [guid]::NewGuid().ToString('N')`
7. Run: `python app.py`
8. Open `http://127.0.0.1:5000`.

## Deploy on Render
1. Upload this folder to a GitHub repository.
2. Create a new **Web Service** on Render and connect the repository.
3. Build command: `pip install -r requirements.txt`
4. Start command: `gunicorn app:app --bind 0.0.0.0:$PORT --workers 2 --timeout 60`
5. Add environment variable `SECRET_KEY` with a long random secret value.
6. Deploy and check `/health`.

## Before taking real customer orders
- `WHATSAPP_NUMBER` must be the business's WhatsApp number in international digits without `+`.
- Update product names, prices and descriptions in `app.py`.
- A poster is included in `static/poster.svg`; you can replace it with a real image later.
- This starter saves orders to `orders.json`. Many cloud hosts have ephemeral local storage; connect a persistent disk or a database before relying on it for real orders. Back up customer data securely.
- Online payment is not implemented. “UPI - Coming Soon” is only a placeholder; customers are not charged online.
- Add your actual shipping, privacy, refund and terms policies before public launch.
