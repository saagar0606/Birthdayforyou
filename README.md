<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Aditi ❤️</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&family=Dancing+Script:wght@700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #ff4d6d;
            --secondary: #ff8fa3;
            --dark: #0a0a0a;
            --glass: rgba(255, 255, 255, 0.1);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            background-color: var(--dark);
            color: white;
            font-family: 'Poppins', sans-serif;
            overflow-x: hidden;
            min-height: 100vh;
        }

        #bg-hearts {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .screen {
            display: none;
            min-height: 100vh;
            width: 100vw;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
            text-align: center;
            animation: fadeIn 0.8s ease-in-out;
        }

        .active { display: flex; }

        @keyframes fadeIn { from { opacity: 0; transform: scale(0.95); } to { opacity: 1; transform: scale(1); } }

        h1 { font-family: 'Dancing Script', cursive; font-size: 3rem; color: var(--primary); text-shadow: 2px 2px 10px rgba(255,77,109,0.5); }
        
        .btn {
            background: var(--primary);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 50px;
            font-size: 1.1rem;
            cursor: pointer;
            margin-top: 20px;
            box-shadow: 0 4px 15px rgba(255, 77, 109, 0.4);
            transition: 0.3s;
        }

        /* Fixed Balloon & Teddy Grid */
        .fixed-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-top: 25px;
            background: var(--glass);
            padding: 20px;
            border-radius: 20px;
            border: 1px solid rgba(255,255,255,0.1);
        }

        .item-box {
            width: 80px;
            height: 90px;
            background: rgba(255,255,255,0.05);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            cursor: pointer;
            border-radius: 15px;
            transition: 0.3s;
            border: 1px solid rgba(255,255,255,0.1);
        }

        .item-box:hover { background: rgba(255,255,255,0.15); }

        /* Photo Styles */
        .bachpan-img { width: 100%; max-width: 280px; border-radius: 20px; border: 4px solid white; margin: 20px 0; }
        
        .photo-gallery { 
            display: grid; 
            grid-template-columns: repeat(3, 1fr); 
            gap: 10px; 
            width: 100%; 
            margin: 20px 0;
            max-height: 400px;
            overflow-y: auto;
            padding: 10px;
        }
        .photo-gallery img { width: 100%; aspect-ratio: 1; object-fit: cover; border-radius: 10px; }

        /* Letter Box */
        .letter-box {
            background: white;
            color: #222;
            padding: 25px;
            border-radius: 20px;
            max-width: 500px;
            width: 90%;
            max-height: 75vh;
            overflow-y: auto;
            text-align: left;
            line-height: 1.6;
            box-shadow: 0 10px 40px rgba(0,0,0,0.5);
        }

        .box-3d { font-size: 5.5rem; cursor: pointer; animation: bounce 2s infinite; margin: 20px; }
        @keyframes bounce { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-20px); } }

        .shyri { font-style: italic; color: var(--primary); font-weight: 600; text-align: center; margin-bottom: 20px; border-bottom: 1px dashed #ccc; padding-bottom: 10px; }
    </style>
</head>
<body>

    <div id="bg-hearts"></div>

    <div class="screen active" id="s1">
        <h1>Happiest Birthday My Love ❤️</h1>
        <p>Aapke liye ek chota sa tohfa...</p>
        <button class="btn" onclick="nextScreen(2)">Shuru Karein?</button>
    </div>

    <div class="screen" id="s2">
        <h2 id="q-text">Kya aap mere liye ek game khelogi?</h2>
        <div id="game-choice">
            <button class="btn" onclick="startBalloonGame()">Haan Bilkul!</button>
        </div>
        <div id="balloon-game" style="display:none;">
            <p>In 9 Balloons mein 4 ❤️ chupe hain, dhundo!</p>
            <div class="fixed-grid" id="balloon-canvas"></div>
            <p id="b-score" style="margin-top:15px;">Hearts Found: 0/4</p>
        </div>
    </div>

    <div class="screen" id="s3">
        <h2>Your Reward...</h2>
        <div class="box-3d" id="gift1" onclick="openGift(this, '💋', 4)">🎁</div>
        <p>Box kholiye madam ji!</p>
    </div>

    <div class="screen" id="s4">
        <h2>Aapki Bachpan ki Photo 🥺</h2>
        <img src="https://i.ibb.co/jP4RzPmy/bachpan.jpg" class="bachpan-img">
        <p>Nazar na lage, kitni cute ho!</p>
        <button class="btn" onclick="nextScreen(5)">Next Memory ❤️</button>
    </div>

    <div class="screen" id="s5">
        <div class="box-3d" id="env" onclick="this.style.display='none'; document.getElementById('l1').style.display='block';">✉️</div>
        <div class="letter-box" id="l1" style="display:none;">
            <p>Main perfect nahi hoon… lekin perfect banne ki puri koshish kar raha hoon, sirf aapke liye.<br><br>
            Bas ek baat kehni hai… please mera saath kabhi mat chhodna. Kyuki maine aapko shaadi se pehle hi apni wife maana hai, aur sabko proudly bola hai ki yeh meri future wife hai.<br><br>
            Aap sirf meri girlfriend nahi ho, aap meri zimmedari ho, meri dua ho, meri zindagi ho. 🤍</p>
            <button class="btn" onclick="nextScreen(6)">Ek aur Game?</button>
        </div>
    </div>

    <div class="screen" id="s6">
        <h2>Find the Teddy 🧸</h2>
        <p>Find 4 Teddies to unlock final surprise!</p>
        <div class="fixed-grid" id="t-grid"></div>
        <p id="t-score" style="margin-top:15px;">Found: 0/4</p>
    </div>

    <div class="screen" id="s7">
        <div class="letter-box">
            <p class="shyri">सब कुछ कह दिया दुनिया ने मेरे बारे में,<br>पर जो तूने मेरी खामोशी में पढ़ लिया,<br>वो किसी किताब में लिखा ही नहीं था। 🌙</p>
            
            <p><b>Happy Birthday my Bandariya, my Aditi ❤️</b><br><br>
            Aap meri life ki sabse badi miracle ho. Hamare 4 saal hone wale hain aur main aaj bhi wahi Sagar hoon jo aapke liye pagal hai.<br><br>
            Tumhare alawa mera koi nahi hai, and I don’t want anyone else. You are my today, my tomorrow, and my always.</p>
            
            <div class="photo-gallery">
                <img src="https://i.ibb.co/Z6cpjccC/1.jpg"><img src="https://i.ibb.co/N2YM79Mk/2.jpg"><img src="https://i.ibb.co/gbJHvX5c/3.jpg">
                <img src="https://i.ibb.co/whDJNhB8/4.jpg"><img src="https://i.ibb.co/TqbLXVr0/5.jpg"><img src="https://i.ibb.co/DfxBXjNH/6.jpg">
                <img src="https://i.ibb.co/XxtHZ8Q4/7.jpg"><img src="https://i.ibb.co/Nngk1RyR/8.jpg"><img src="https://i.ibb.co/C3NHHQFf/9.jpg">
            </div>
            <button class="btn" onclick="nextScreen(8)">Aakhri Message</button>
        </div>
    </div>

    <div class="screen" id="s8">
        <div class="letter-box" style="text-align: center;">
            <p>Happy birthday my Bandariya cutie... Main duniya ka sabse khush naseeb insaan hoon kyunki aap meri life ho.<br><br>
            Maaf kar dena agar kabhi dukh pahunchaya ho. Aapke bina main kuch nahi hoon.<br><br>
            <b>I love you madam ji! I miss you so much!</b></p>
            <div class="box-3d" onclick="this.innerHTML='🌹';">🎁</div>
            <p>Gulab aapke liye...</p>
            <p style="margin-top:20px; font-size: 0.8rem; color: #888;">- Sagar Yadav</p>
        </div>
    </div>

    <script>
        function nextScreen(n) {
            document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
            document.getElementById('s' + n).classList.add('active');
            window.scrollTo(0,0);
        }

        // Background Hearts
        function createHeart() {
            const h = document.createElement('div');
            h.innerHTML = '❤️';
            h.style.position = 'fixed';
            h.style.left = Math.random() * 100 + 'vw';
            h.style.top = '100vh';
            h.style.fontSize = '20px';
            h.style.opacity = Math.random();
            h.style.transition = '6s linear';
            h.style.color = '#ff4d6d';
            document.getElementById('bg-hearts').appendChild(h);
            setTimeout(() => { h.style.top = '-10vh'; }, 100);
            setTimeout(() => h.remove(), 7000);
        }
        setInterval(createHeart, 400);

        // Balloon Game (Fixed Grid)
        let bCount = 0;
        function startBalloonGame() {
            document.getElementById('game-choice').style.display = 'none';
            document.getElementById('q-text').style.display = 'none';
            document.getElementById('balloon-game').style.display = 'block';
            const area = document.getElementById('balloon-canvas');
            const items = ['❤️', '❤️', '❤️', '❤️', '🎈', '🎈', '🎈', '🎈', '🎈'];
            items.sort(() => Math.random() - 0.5);
            items.forEach(item => {
                const b = document.createElement('div');
                b.className = 'item-box';
                b.innerHTML = '🎈';
                b.onclick = function() {
                    if(this.style.background === 'white') return;
                    this.innerHTML = item;
                    this.style.background = 'white';
                    this.style.color = 'black';
                    if(item === '❤️') {
                        bCount++;
                        document.getElementById('b-score').innerText = `Hearts Found: ${bCount}/4`;
                        if(bCount === 4) setTimeout(() => nextScreen(3), 1000);
                    }
                };
                area.appendChild(b);
            });
        }

        // Teddy Game (Fixed Grid)
        let tCount = 0;
        const tGrid = document.getElementById('t-grid');
        const tItems = ['🧸', '🧸', '🧸', '🧸', '🌸', '🌸', '🌸', '🌸', '🌸'];
        tItems.sort(() => Math.random() - 0.5);
        tItems.forEach(item => {
            const c = document.createElement('div');
            c.className = 'item-box';
            c.innerHTML = '📦';
            c.onclick = function() {
                if(this.style.background === 'white') return;
                this.innerHTML = item;
                this.style.background = 'white';
                this.style.color = 'black';
                if(item === '🧸') {
                    tCount++;
                    document.getElementById('t-score').innerText = `Found: ${tCount}/4`;
                    if(tCount === 4) setTimeout(() => nextScreen(7), 1000);
                }
            };
            tGrid.appendChild(c);
        });

        function openGift(el, emoji, next) {
            el.innerHTML = emoji;
            setTimeout(() => nextScreen(next), 1500);
        }
    </script>
</body>
</html>
