# dapps-explorer

This repository contains JSON metadata used by our mobile wallet apps to render a dynamic **DApps Explorer** interface. It lists curated decentralized applications (dApps) that support wallet connectivity, enabling users to interact with Web3 apps directly from within the wallet.

---

## 📦 Purpose

The data in this repository powers the in-app dApps Explorer page. The mobile wallet fetches this JSON data to display supported dApps in real time.

---

## 📁 Repository Structure

- `/data/dapps.json` — Main list of supported dApps.
- `/locales/` — Contains translations per language (e.g., `en.json`, `es.json`, etc.).

Example entry in `dapps.json`:

```json
{
  "id": "qearn_app_id",
  "nameId": "qearn_name",
  "icon": "https://framerusercontent.com/images/OlRHyS54DdB86UYF7BlAZbFQ.png",
  "url": "https://www.qearn.org/",
  "descriptionId": "qearn_description"
}
```

### 🔑 Field Descriptions

- `id`: Unique string identifier for the dApp.
- `nameId`: Localization key for the dApp’s name.
- `descriptionId`: Localization key for the dApp’s description.
- `icon`: URL to the dApp's icon image.
- `url`: Public URL or entry point for the dApp.

---

## ➕ How to Add a New dApp

### 1. Update `dapps.json`

Add a new object to the `"dapps"` array in `/data/dapps.json`:

```json
{
  "id": "my_app_unique_id",
  "nameId": "my_app_name",
  "descriptionId": "my_app_description",
  "icon": "https://example.com/icons/my_app_icon.png",
  "url": "https://my_app_url.com"
}
```

### 2. Add Translations

Add the corresponding localized texts to each language file in `/locales/`.

**Example: `/locales/en.json`**
```json
{
  "qearn_name": "QEarn",
  "qearn_description": "Earn Rewards by Staking $QUBIC."
}
```

**Example: `/locales/es.json`**
```json
{
  "qearn_name": "QEarn",
  "qearn_description": "Gana recompensas haciendo 'staking' con $QUBIC."
}
```

> 💡 **Note:** English (`/locales/en.json`) is mandatory and used as the default fallback. If a translation is missing in another language, the app will display the English version.

---

### ✅ Summary Checklist

- [ ] Add a new entry in `/data/dapps.json`.
- [ ] Use unique `id`, and valid `nameId` and `descriptionId` keys.
- [ ] Add corresponding entries in `/locales/en.json` (required) and other languages as needed.
- [ ] Ensure `icon` and `url` are valid and publicly accessible.

---

## 🛠️ Contributing

We welcome contributions! To add or update a dApp:

1. Fork the repository.
2. Add the new dApp entry in `/data/dapps.json`.
3. Add localized texts in the relevant `/locales/` files.
4. Validate your JSON.
5. Open a pull request with a clear description of your changes.

---