# Placement LMS — Starter Project

A React + Vite starter for a student placement assessment portal.

## Included
- Student registration and login UI
- Admin login and dashboard
- Student registration list
- Reasoning & Aptitude test with a 60-minute countdown
- Automatic submission when the countdown reaches zero while the test page is open
- Score, start time, submission time, duration, and auto-submit status
- Results table and CSV export
- Technical MCQ and Programming Assessment cards marked **Coming Soon**
- Firebase config placeholder
- Sample aptitude questions in `src/data/questions.js`

## Run in VS Code
1. Extract the ZIP.
2. Open the extracted `placement-lms-starter` folder in VS Code.
3. Open Terminal → New Terminal.
4. Run:

   ```bash
   npm install
   npm run dev
   ```

5. Open the local URL printed by Vite, normally `http://localhost:5173`.

## Demo admin login
- Email: `admin@placementlms.local`
- Password: `Admin@123`

Change these before any real use. The demo login is not secure authentication.

## Replace sample questions
Open `src/data/questions.js` and add the questions from your PDF. The answer index is zero-based:
- `answer: 0` = option A
- `answer: 1` = option B
- `answer: 2` = option C
- `answer: 3` = option D

The starter currently has 5 example questions, so the score is out of 5 until you replace/add the full question set.

## Important limitations before real student use
This starter currently stores registration records and results in **localStorage**. That means:
- Data exists only in that browser profile and is not shared across devices.
- Passwords are stored in the browser and this is NOT safe for real student accounts.
- A determined user can alter local browser data.
- The countdown auto-submits while the test page is open, but this is not a server-enforced deadline.

Before real deployment, configure Firebase Authentication + Firestore and security rules, use a trusted backend/server timestamp for test attempts, and connect Google Sheets through a protected Apps Script or backend endpoint. Do not put Google service-account credentials in frontend code.

## Firebase setup placeholder
`src/firebase/config.js` is ready for your Firebase web app configuration. The current demo app does not yet use Firebase for saving records. The next integration step is Firebase Authentication/Firestore, security rules, and a server-enforced timer.

## Google Sheets
Google Sheets integration is not yet connected in this starter. It should be added after the sheet's column structure and the Apps Script/backend endpoint are confirmed. Avoid making the sheet publicly editable.
