# Fom-Rizki-To-you.
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>From Rizki Resaldi To you</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #fce4ec; /* Pink muda halus */
            font-family: 'Arial', sans-serif;
        }

        .container {
            text-align: center;
            background: white;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            width: 350px;
            position: relative;
        }

        #gif {
            width: 100%;
            max-width: 250px;
            border-radius: 10px;
            margin-bottom: 20px;
        }

        h2 {
            color: #333;
            font-size: 24px;
            margin-bottom: 30px;
        }

        .buttons {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            min-height: 50px;
        }

        button {
            padding: 10px 25px;
            font-size: 16px;
            font-weight: bold;
            border: none;
            border-radius: 20px;
            cursor: pointer;
            transition: transform 0.2s;
        }

        #yes-btn {
            background-color: #ff5e7e;
            color: white;
        }

        #no-btn {
            background-color: #ff5e7e;
            color: white;
            position: relative; /* Berubah jadi absolute lewat JS saat dikejar */
            z-index: 999;
        }
    </style>
</head>
<body>

    <div class="container">
        <img id="gif" src="https://media.tenor.com/7S8f4N2M8SgAAAAi/cute-bear.gif" alt="Asking Bear">
        <h2 id="question">Do you love Rizki Resaldi?</h2>
        
        <div class="buttons">
            <button id="yes-btn">Yes</button>
            <button id="no-btn">No</button>
        </div>
    </div>

    <script>
         const noBtn = document.getElementById('no-btn');
    const yesBtn = document.getElementById('yes-btn');
    const question = document.getElementById('question');
    const gif = document.getElementById('gif');
    const container = document.querySelector('.container');

    // Fungsi membuat tombol "No" lari tapi tetap di dalam kotak putih
    noBtn.addEventListener('mouseover', () => {
        // Ambil ukuran kotak putih (container)
        const containerRect = container.getBoundingClientRect();
        const btnRect = noBtn.getBoundingClientRect();

        // Hitung batas maksimal agar tombol tidak keluar dari kotak putih
        const maxX = containerRect.width - btnRect.width;
        const maxY = containerRect.height - btnRect.height;

        // Tentukan posisi acak di dalam batas tersebut
        const randomX = Math.floor(Math.random() * maxX);
        const randomY = Math.floor(Math.random() * maxY);

        // Terapkan posisi baru
        noBtn.style.position = 'absolute';
        noBtn.style.left = randomX + 'px';
        noBtn.style.top = randomY + 'px';
    });

    // Aksi ketika klik "Yes"
    yesBtn.addEventListener('click', () => {
        question.innerHTML = "I knew it! ❤️";
        // Link animasi baru yang lebih stabil
        gif.src = "https://media.tenor.com/97y_tX_f0eUAAAAi/milk-and-mocha-hug.gif";
        noBtn.style.display = 'none';
    });
</script>
</body>
</html>
