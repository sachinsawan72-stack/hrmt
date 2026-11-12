# TeamDesk HR 🏢

A lightweight, single-file HR Management System powered by Firebase. Manage employees, attendance, payroll, and documents securely with role-based access control.

## ✨ Features
- **Employee Management:** Add, edit, and manage employee records seamlessly.
- **Attendance & Leave:** Track daily attendance and manage leave requests.
- **Payroll:** Auto-calculate salary, PF, ESIC, PT, and generate PDF payslips.
- **Documents:** Upload and verify employee documents with expiry alerts.
- **HR Letters:** Generate official letters (Joining, Relieving, Experience, NOC, etc.).
- **Role-Based Access:** Secure access for Admin, HR, and Viewer roles.
- **Cloud Sync:** Real-time data sync using Firebase Firestore.
- **Dark Mode:** Built-in dark theme support.

## 🛠️ Tech Stack
- **Frontend:** HTML5, CSS3, Vanilla JavaScript (No frameworks)
- **Backend/Database:** Firebase (Authentication & Firestore)
- **Hosting:** Vercel / Netlify / Local Browser

## 🚀 Setup & Installation

### 1. Firebase Setup
1. Create a new project on [Firebase Console](https://console.firebase.google.com/).
2. Enable **Authentication** and select the **Email/Password** provider.
3. Create a **Cloud Firestore Database** (Start in test mode or apply custom rules).
4. Register a Web App in Project Settings and copy your Firebase config (`apiKey`, `appId`, etc.).

### 2. Local Setup
1. Open `teamdesk-hr.html` (or `index.html`) in any text editor (VS Code, Notepad++).
2. Scroll down to the bottom `<script type="module">` section.
3. Find the `CFG` object and replace `"PASTE_API_KEY"` with your actual Firebase API Key.
4. Save the file and open it directly in your web browser.

### 3. Create Your First Admin User
1. Go to **Firebase Console > Authentication > Users** and add your Admin email and password.
2. Copy the **User UID** of the newly created user.
3. Go to **Firestore Database > Start Collection** and name it `users`.
4. Click **Add Document** and paste the **User UID** as the Document ID.
5. Add the following fields to the document:
   - `email` (string): your admin email
   - `name` (string): Admin Name
   - `role` (string): `Admin`
6. Save the document. You can now log in to the app!

## 🌐 Deploy to Vercel
1. Rename your HTML file to `index.html`.
2. Place it inside a folder (e.g., `teamdesk-hr`).
3. Go to [Vercel New Project](https://vercel.com/new), log in, and drag & drop the folder into the deploy box.
4. Within seconds, your app will be live on a custom Vercel URL!

## 🔒 Security & Roles
This app uses strict Firestore Security Rules. 
- **Admin:** Full access, can create HR/Viewer users, manage payroll and settings.
- **HR:** Can manage employees, attendance, and leaves. Can only edit records they created.
- **Viewer:** Read-only access to the dashboard and reports.

*Note: Users without a corresponding document in the `users` Firestore collection will be automatically signed out with a "No role assigned" error.*

## 📝 License
MIT License. Free to use and modify.