# Introduction

This project is done using third party Nordigen Node example with Express.js API to create a dashboard where users details, acount balances and transactions data will be displayed in the UI after getting authorisation and authentication with the chosen bank.

## Set-up

---

You'll need to get your `SECRET_ID` and `SECRET_KEY` from the [Nordigen's Open Banking Portal](https://ob.nordigen.com/).
In **index.js** file provide the token as a parameter for `NordigenClient`.

```javascript
// Pass secretId and secretKey to NordigenClient instance as a string or load from .env file
// Client details can be generated from OB portal
const client = new NordigenClient({
  secretId: process.env.SECRET_ID,
  secretKey: process.env.SECRET_KEY,
});
```

To initialize session with a bank, you have to specify `country` (a two-letter country code)

```javascript
const COUNTRY = "FI";
```

## Installation

---

Install dependencies

```bash
npm install
```

Start project

```bash
npm start
```

### 1. Go to http://localhost:5000/ and select bank

<p align="center">
    <img align="center" src="./resources/_media/f_3_select_aspsp.png" width="200" />
</p>

### 2. Provide consent

<p align="center">
  <img src="./resources/_media/f_4_ng_agreement.jpg" width="200" />
  <img src="./resources/_media/f_4.1_ng_redirect.png" width="200" /> 
</p>

### 3. Sign into bank (Institution)

<p align="center">
  <img src="./resources/_media/f_5_aspsps_signin.png" width="230" />
  <img src="./resources/_media/f_5.1_aspsps_signin.jpg" width="200" /> 
  <img src="./resources/_media/f_5.2_aspsps_signin.jpg" width="200" /> 
</p>

<p align="center">
  <img src="./resources/_media/f_5.3_aspsp_auth.jpg" width="200" /> 
</p>

### 4. Select accounts

<p align="center">
  <img src="./resources/_media/f_6_aspsp_accs.jpg" width="200" />
</p>

### 5. You will be redirected to specified `REDIRECT_URI` `http://localhost:3000/` in our case it is a dashboard with users details, acount balances and transactions. Make sure client is running under the `REDIRECT_URI` in your browser.
