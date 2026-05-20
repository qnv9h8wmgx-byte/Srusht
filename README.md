<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mihwar - وێبسایتەکەت</title>
</head>
<body>

    <h1>بەخێربێن بۆ وێبەکەت</h1>
    <input type="email" id="email" placeholder="ئیمەیڵەکەت بنووسە">
    <input type="password" id="password" placeholder="پاسۆردەکەت بنووسە">
    <button id="signupBtn">دروستکردنی ئەکاونت</button>

    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/9.22.0/firebase-app.js";
        import { getAuth, createUserWithEmailAndPassword } from "https://www.gstatic.com/firebasejs/9.22.0/firebase-auth.js";

        const firebaseConfig = {
            apiKey: "AIzaSyCP95VdnXvP7ShSe9o5fh8iVSBAvSSqZ-s",
            authDomain: "mihwar-b7269.firebaseapp.com",
            projectId: "mihwar-b7269",
            storageBucket: "mihwar-b7269.firebasestorage.app",
            messagingSenderId: "972115287921",
            appId: "1:972115287921:web:1c65682cd8166a8e1760d0"
        };

        const app = initializeApp(firebaseConfig);
        const auth = getAuth(app);

        document.getElementById("signupBtn").addEventListener("click", () => {
            const email = document.getElementById("email").value;
            const password = document.getElementById("password").value;

            createUserWithEmailAndPassword(auth, email, password)
                .then((userCredential) => {
                    alert("سەرکەوتوو بوو! ئەکاونتەکەت دروست بوو.");
                })
                .catch((error) => {
                    alert("هەڵەیەک ڕوویدا: " + error.message);
                });
        });
    </script>
</body>
</html>
