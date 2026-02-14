# 💌 HMMI Love Letter Untold

> A public, anonymous love‑letter board powered by **GitHub Pages + Google Apps Script + Google Sheets**.
> Visitors submit messages via a form, and the data is securely stored in a Google Spreadsheet in real‑time.

---

## ✨ Overview

**HMMI Love Letter Untold** is a lightweight web application that mimics a Google Form–style interface where users can send anonymous messages (love letters, appreciation notes, or confessions). The form is hosted on **GitHub Pages**, while submissions are processed by **Google Apps Script** and stored in **Google Sheets** as a backend database.

No server, database, or hosting subscription is required.

---

## 🚀 Features

* 📄 Google‑Form‑like user interface
* 🧾 Anonymous submission (no login required)
* 🌐 Publicly accessible via GitHub Pages
* ⚡ Real‑time storage to Google Sheets
* 🇮🇩 Indonesian date & time format
* 📨 Supports multiple messages (up to 3 + remark)
* 🛡️ No backend server required (serverless architecture)
* 📱 Mobile‑friendly responsive design

---

## 🧰 Tech Stack

| Component   | Technology                         |
| ----------- | ---------------------------------- |
| Frontend    | HTML, CSS, JavaScript              |
| Hosting     | GitHub Pages                       |
| Backend API | Google Apps Script Web App         |
| Database    | Google Sheets                      |
| Styling     | Custom CSS (Google Forms inspired) |

---

## 🏗️ Architecture

```
User Browser
     ↓
GitHub Pages (HTML Form)
     ↓ POST
Google Apps Script Web App
     ↓
Google Sheets (Database)
```

The browser sends form data to the Apps Script endpoint. The script processes the data and appends a new row to the spreadsheet.

---

## 📂 Project Structure

```
love_letter/
│── index.html
│── README.md
```

---

## ⚙️ Setup Guide

### 1️⃣ Create Google Spreadsheet

1. Go to **Google Sheets**
2. Create a new spreadsheet
3. Rename the first tab to:

```
Sheet1
```

4. Create header row:

```
Waktu | From | To | Pesan 1 | Pesan 2 | Pesan 3 | Remark
```

---

### 2️⃣ Create Apps Script Web App

1. Open: [https://script.google.com](https://script.google.com)
2. New Project
3. Paste the Apps Script backend code
4. Replace:

```
SHEET_ID = "YOUR_SPREADSHEET_ID"
```

5. Run `init()` once (to grant permissions)

#### Deploy

```
Deploy → New Deployment → Web App
```

Settings:

* Execute as: **Me**
* Who has access: **Anyone**

Copy the generated Web App URL.

---

### 3️⃣ Configure Frontend

In `index.html`, replace:

```
const SCRIPT_URL = "YOUR_WEB_APP_URL";
```

with your deployed Apps Script URL.

---

### 4️⃣ Publish via GitHub Pages

1. Create a GitHub repository
2. Upload `index.html`
3. Go to:

```
Settings → Pages
```

4. Source:

```
Deploy from branch → main → /root
```

5. Save

Your website will be available at:

```
https://yourusername.github.io/love_letter/
```

---

## 🧪 Testing

1. Open the website
2. Fill the form
3. Click **Kirim**
4. Check Google Sheets

A new row should appear automatically within 1–3 seconds.

---

## 🛠️ Troubleshooting

### Form says success but no data in Sheet

* Ensure Apps Script deployed as **Anyone**
* Run `init()` once
* Confirm spreadsheet tab name = `Sheet1`
* Redeploy a **New Version**

### CORS error

Do not use JSON fetch. Use FormData submission (already implemented in this project).

### API opens Google Drive page

Spreadsheet permission issue — re‑authorize the Web App and redeploy.

---

## 🔒 Privacy Notice

This project intentionally **does not collect email or login data**. All information stored comes only from what the user writes in the form fields.

---

## 🌱 Possible Improvements

* Public message board (display letters on a webpage)
* Admin panel to delete messages
* Moderation filter (bad words detection)
* Image attachment support
* Email notification for admins

---

## 📸 Screenshots

<img width="1920" height="1128" alt="image" src="https://github.com/user-attachments/assets/bb743641-2415-458b-84dc-95de3ee3e45f" />

![WhatsApp Image 2026-02-14 at 20 37 09](https://github.com/user-attachments/assets/40cea081-6830-43b2-b2b0-9687bc5a670c)


Developed by **Roby Sunjaya**
Using Google Apps Script & GitHub Pages


## ⭐ Support

If you like this project, please consider giving it a **star ⭐** on GitHub to support development!
