<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>✨ Cosmic Links - Ultimate Animation Experience</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* ====== RESET & BASE STYLES ====== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        :root {
            --primary: #8a2be2;
            --secondary: #00ff88;
            --accent: #ff0080;
            --bg-dark: #0a0a1a;
            --bg-darker: #050510;
            --text-light: #ffffff;
            --text-glow: #00ffff;
        }
        
        body {
            background-color: var(--bg-darker);
            color: var(--text-light);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }
        
        /* ====== BACKGROUND LAYERS ====== */
        .bg-layer-1 {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 30%, rgba(138, 43, 226, 0.15) 0%, transparent 50%),
                radial-gradient(circle at 80% 70%, rgba(0, 255, 136, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 80%, rgba(255, 0, 128, 0.1) 0%, transparent 50%);
            z-index: -3;
            animation: bgPulse 15s infinite alternate;
        }
        
        .bg-layer-2 {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(255, 255, 255, 0.03) 2px, rgba(255, 255, 255, 0.03) 4px);
            z-index: -2;
            animation: gridMove 20s linear infinite;
        }
        
        .floating-shapes {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }
        
        .shape {
            position: absolute;
            border-radius: 50%;
            filter: blur(40px);
            opacity: 0.4;
            animation: floatShape 25s infinite linear;
        }
        
        .shape:nth-child(1) {
            width: 300px;
            height: 300px;
            background: var(--primary);
            top: 10%;
            left: 5%;
            animation-delay: 0s;
        }
        
        .shape:nth-child(2) {
            width: 400px;
            height: 400px;
            background: var(--secondary);
            top: 60%;
            right: 10%;
            animation-delay: -5s;
            animation-duration: 30s;
        }
        
        .shape:nth-child(3) {
            width: 250px;
            height: 250px;
            background: var(--accent);
            bottom: 20%;
            left: 20%;
            animation-delay: -10s;
            animation-duration: 20s;
        }
        
        /* ====== MAIN CONTAINER ====== */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 30px;
            position: relative;
            z-index: 10;
        }
        
        /* ====== HEADER SECTION ====== */
        .header {
            text-align: center;
            padding: 60px 20px;
            position: relative;
            overflow: hidden;
        }
        
        .title-container {
            position: relative;
            display: inline-block;
        }
        
        .main-title {
            font-size: 4.5rem;
            font-weight: 900;
            background: linear-gradient(90deg, var(--primary), var(--secondary), var(--accent), var(--primary));
            background-size: 300% 100%;
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-transform: uppercase;
            letter-spacing: 3px;
            margin-bottom: 20px;
            animation: gradientShift 8s infinite linear, titleFloat 6s infinite ease-in-out;
            text-shadow: 0 0 30px rgba(138, 43, 226, 0.5);
            position: relative;
            z-index: 2;
        }
        
        .title-glow {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--secondary), var(--accent), var(--primary));
            background-size: 300% 100%;
            filter: blur(25px);
            opacity: 0.7;
            z-index: 1;
            animation: gradientShift 8s infinite linear;
        }
        
        .subtitle {
            font-size: 1.5rem;
            color: rgba(255, 255, 255, 0.8);
            max-width: 600px;
            margin: 0 auto 40px;
            line-height: 1.6;
            animation: fadeInUp 1.5s ease-out;
        }
        
        /* ====== SOCIAL LINKS SECTION ====== */
        .social-section {
            padding: 40px 0;
        }
        
        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 60px;
            position: relative;
            display: inline-block;
            left: 50%;
            transform: translateX(-50%);
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, transparent, var(--secondary), transparent);
            border-radius: 2px;
        }
        
        .links-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 60px;
        }
        
        .link-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 40px 30px;
            text-align: center;
            position: relative;
            overflow: hidden;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 1px solid rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            animation: cardEntrance 1s ease-out;
            animation-fill-mode: both;
        }
        
        .link-card:nth-child(1) { animation-delay: 0.2s; }
        .link-card:nth-child(2) { animation-delay: 0.4s; }
        .link-card:nth-child(3) { animation-delay: 0.6s; }
        
        .link-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: left 0.7s ease;
        }
        
        .link-card:hover::before {
            left: 100%;
        }
        
        .link-card:hover {
            transform: translateY(-15px) scale(1.03);
            box-shadow: 
                0 20px 40px rgba(0, 0, 0, 0.4),
                0 0 0 1px rgba(0, 255, 136, 0.2),
                0 0 60px rgba(138, 43, 226, 0.3);
            border-color: var(--secondary);
        }
        
        .link-icon {
            font-size: 4rem;
            margin-bottom: 25px;
            display: inline-block;
            transition: all 0.5s ease;
        }
        
        .link-card:hover .link-icon {
            transform: scale(1.2) rotate(10deg);
        }
        
        .youtube .link-icon { color: #FF0000; }
        .instagram .link-icon { 
            background: radial-gradient(circle at 30% 107%, #fdf497 0%, #fdf497 5%, #fd5949 45%, #d6249f 60%, #285AEB 90%);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .facebook .link-icon { color: #1877F2; }
        
        .link-title {
            font-size: 2rem;
            margin-bottom: 15px;
            font-weight: 700;
            background: linear-gradient(90deg, #fff, var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .link-desc {
            color: rgba(255, 255, 255, 0.7);
            margin-bottom: 30px;
            line-height: 1.6;
            font-size: 1.1rem;
        }
        
        .link-button {
            display: inline-block;
            padding: 15px 35px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1.1rem;
            letter-spacing: 1px;
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
            box-shadow: 0 10px 20px rgba(138, 43, 226, 0.3);
        }
        
        .link-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: left 0.7s ease;
        }
        
        .link-button:hover::before {
            left: 100%;
        }
        
        .link-button:hover {
            transform: translateY(-5px);
            box-shadow: 
                0 15px 30px rgba(138, 43, 226, 0.5),
                0 0 30px rgba(255, 0, 128, 0.3);
        }
        
        /* ====== PARTICLE SYSTEM ====== */
        .particles-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 5;
        }
        
        .particle {
            position: absolute;
            border-radius: 50%;
            background: var(--text-glow);
            box-shadow: 0 0 10px var(--text-glow), 0 0 20px var(--text-glow);
            animation: particleFloat 15s infinite linear;
        }
        
        /* ====== ANIMATED ORBS ====== */
        .orb-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 4;
        }
        
        .orb {
            position: absolute;
            width: 100px;
            height: 100px;
            border-radius: 50%;
            filter: blur(30px);
            opacity: 0.3;
            animation: orbMove 40s infinite linear;
        }
        
        .orb-1 {
            background: var(--primary);
            top: 20%;
            left: 10%;
            animation-delay: 0s;
        }
        
        .orb-2 {
            background: var(--secondary);
            top: 70%;
            right: 15%;
            animation-delay: -10s;
            animation-duration: 35s;
        }
        
        .orb-3 {
            background: var(--accent);
            bottom: 30%;
            left: 30%;
            animation-delay: -20s;
            animation-duration: 45s;
        }
        
        /* ====== FOOTER ====== */
        .footer {
            text-align: center;
            padding: 60px 20px 30px;
            margin-top: 80px;
            position: relative;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .footer-text {
            color: rgba(255, 255, 255, 0.6);
            font-size: 1.1rem;
            margin-bottom: 20px;
        }
        
        .footer-glow {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 1px;
            background: linear-gradient(90deg, transparent, var(--secondary), transparent);
            box-shadow: 0 0 20px var(--secondary);
        }
        
        /* ====== ANIMATION KEYFRAMES ====== */
        @keyframes bgPulse {
            0% { opacity: 0.8; }
            50% { opacity: 1; }
            100% { opacity: 0.8; }
        }
        
        @keyframes gridMove {
            0% { transform: translateY(0); }
            100% { transform: translateY(4px); }
        }
        
        @keyframes floatShape {
            0% { transform: translate(0, 0) rotate(0deg); }
            25% { transform: translate(30px, -50px) rotate(90deg); }
            50% { transform: translate(0, -100px) rotate(180deg); }
            75% { transform: translate(-30px, -50px) rotate(270deg); }
            100% { transform: translate(0, 0) rotate(360deg); }
        }
        
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        @keyframes titleFloat {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes cardEntrance {
            from {
                opacity: 0;
                transform: translateY(50px) scale(0.9);
            }
            to {
                opacity: 1;
                transform: translateY(0) scale(1);
            }
        }
        
        @keyframes particleFloat {
            0% {
                transform: translateY(100vh) translateX(0) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100px) translateX(100px) rotate(360deg);
                opacity: 0;
            }
        }
        
        @keyframes orbMove {
            0% {
                transform: translate(0, 0) scale(1);
            }
            25% {
                transform: translate(50vw, 30vh) scale(1.2);
            }
            50% {
                transform: translate(30vw, 70vh) scale(0.8);
            }
            75% {
                transform: translate(70vw, 50vh) scale(1.1);
            }
            100% {
                transform: translate(0, 0) scale(1);
            }
        }
        
        /* ====== RESPONSIVE DESIGN ====== */
        @media (max-width: 768px) {
            .main-title {
                font-size: 3rem;
            }
            
            .subtitle {
                font-size: 1.2rem;
                padding: 0 20px;
            }
            
            .links-grid {
                grid-template-columns: 1fr;
            }
            
            .link-card {
                padding: 30px 20px;
            }
            
            .link-title {
                font-size: 1.8rem;
            }
        }
        
        /* ====== SPECIAL EFFECTS ====== */
        .cursor-follower {
            position: fixed;
            width: 20px;
            height: 20px;
            background: radial-gradient(circle, var(--secondary), transparent 70%);
            border-radius: 50%;
            pointer-events: none;
            z-index: 9999;
            mix-blend-mode: screen;
            transition: transform 0.1s ease;
        }
        
        .ripple {
            position: absolute;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(0, 255, 136, 0.3), transparent 70%);
            transform: scale(0);
            animation: rippleEffect 1s linear;
            pointer-events: none;
        }
        
        @keyframes rippleEffect {
            to {
                transform: scale(4);
                opacity: 0;
            }
        }
        
        /* ====== LOADING ANIMATION ====== */
        .loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--bg-darker);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 10000;
            transition: opacity 0.8s ease, visibility 0.8s ease;
        }
        
        .loading-content {
            text-align: center;
        }
        
        .loading-spinner {
            width: 80px;
            height: 80px;
            border: 5px solid rgba(255, 255, 255, 0.1);
            border-top: 5px solid var(--secondary);
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin: 0 auto 30px;
        }
        
        .loading-text {
            font-size: 1.5rem;
            color: var(--secondary);
            letter-spacing: 2px;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        /* ====== SCROLL ANIMATIONS ====== */
        .scroll-hint {
            position: absolute;
            bottom: 40px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            flex-direction: column;
            align-items: center;
            color: rgba(255, 255, 255, 0.7);
            animation: bounce 2s infinite;
        }
        
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateX(-50%) translateY(0); }
            40% { transform: translateX(-50%) translateY(-10px); }
            60% { transform: translateX(-50%) translateY(-5px); }
        }
    </style>
</head>
<body>
    <!-- Loading Screen -->
    <div class="loading-screen" id="loadingScreen">
        <div class="loading-content">
            <div class="loading-spinner"></div>
            <div class="loading-text">COSMIC LINKS LOADING...</div>
        </div>
    </div>
    
    <!-- Background Layers -->
    <div class="bg-layer-1"></div>
    <div class="bg-layer-2"></div>
    
    <!-- Floating Shapes -->
    <div class="floating-shapes">
        <div class="shape"></div>
        <div class="shape"></div>
        <div class="shape"></div>
    </div>
    
    <!-- Orbs -->
    <div class="orb-container">
        <div class="orb orb-1"></div>
        <div class="orb orb-2"></div>
        <div class="orb orb-3"></div>
    </div>
    
    <!-- Particles will be generated by JS -->
    <div class="particles-container" id="particlesContainer"></div>
    
    <!-- Cursor Follower -->
    <div class="cursor-follower" id="cursorFollower"></div>
    
    <!-- Main Container -->
    <div class="container">
        <!-- Header -->
        <header class="header">
            <div class="title-container">
                <div class="title-glow"></div>
                <h1 class="main-title">Cosmic Links</h1>
            </div>
            
            <p class="subtitle">
                Eng ajoyib ijtimoiy tarmoqlarga ulaning. Bu saytda har bir element jonli, 
                harakatlanuvchi va hayratlanarli darajada chiroyli animatsiyalar bilan to'ldirilgan.
            </p>
            
            <div class="scroll-hint">
                <i class="fas fa-chevron-down" style="font-size: 1.5rem; margin-bottom: 10px;"></i>
                <span>Pastga o'ting</span>
            </div>
        </header>
        
        <!-- Social Links Section -->
        <section class="social-section">
            <h2 class="section-title">Bizning Kanallar</h2>
            
            <div class="links-grid">
                <!-- YouTube Card -->
                <div class="link-card youtube">
                    <div class="link-icon">
                        <i class="fab fa-youtube"></i>
                    </div>
                    <h3 class="link-title">YouTube</h3>
                    <p class="link-desc">
                        Videolar, darslar, vaqt o'tkazish uchun qiziqarli kontentlar.
                        Har kuni yangi videolar bilan.
                    </p>
                    <a href="https://youtube.com" target="_blank" class="link-button">
                        Kanaga O'tish <i class="fas fa-arrow-right" style="margin-left: 10px;"></i>
                    </a>
                </div>
                
                <!-- Instagram Card -->
                <div class="link-card instagram">
                    <div class="link-icon">
                        <i class="fab fa-instagram"></i>
                    </div>
                    <h3 class="link-title">Instagram</h3>
                    <p class="link-desc">
                        Fotolar, storylar, reelslar. Bizning hayotimizdan lavhalar.
                        Har kuni yangi postlar.
                    </p>
                    <a href="https://instagram.com" target="_blank" class="link-button">
                        Profilga O'tish <i class="fas fa-arrow-right" style="margin-left: 10px;"></i>
                    </a>
                </div>
                
                <!-- Facebook Card -->
                <div class="link-card facebook">
                    <div class="link-icon">
                        <i class="fab fa-facebook"></i>
                    </div>
                    <h3 class="link-title">Facebook</h3>
                    <p class="link-desc">
                        Yangiliklar, tadbirlar, hamjamiyat. Do'stlaringiz bilan ulashing.
                    </p>
                    <a href="https://facebook.com" target="_blank" class="link-button">
                        Sahifaga O'tish <i class="fas fa-arrow-right" style="margin-left: 10px;"></i>
                    </a>
                </div>
            </div>
        </section>
        
        <!-- Footer -->
        <footer class="footer">
            <p class="footer-text">
                &copy; 2024 Cosmic Links. Barcha huquqlar himoyalangan.<br>
                Bu sayt faqat animatsiya namoyishi uchun yaratilgan.
            </p>
            <div class="footer-glow"></div>
        </footer>
    </div>
    
    <script>
        // ========== SAYT YUKLANGANDA ANIMATSIYA ==========
        document.addEventListener('DOMContentLoaded', function() {
            const loadingScreen = document.getElementById('loadingScreen');
            
            // 3 soniyadan keyin loading screen ni olib tashlash
            setTimeout(() => {
                loadingScreen.style.opacity = '0';
                loadingScreen.style.visibility = 'hidden';
                
                // Sayt yuklanganda audio efekti (agar kerak bo'lsa)
                playEntranceSound();
                
                // Particle systemni ishga tushirish
                createParticles();
                
                // Cursor follower ishga tushirish
                initCursorFollower();
                
                // Ripple effekti ishga tushirish
                initRippleEffect();
                
                // Scroll animatsiyalari
                initScrollAnimations();
            }, 3000);
        });
        
        // ========== PARTICLE SYSTEM ==========
        function createParticles() {
            const container = document.getElementById('particlesContainer');
            const particleCount = 100;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                // Tasodifiy o'lcham va joylashuv
                const size = Math.random() * 5 + 2;
                const posX = Math.random() * 100;
                const delay = Math.random() * 15;
                const duration = Math.random() * 10 + 10;
                
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                particle.style.left = `${posX}%`;
                particle.style.animationDelay = `${delay}s`;
                particle.style.animationDuration = `${duration}s`;
                
                // Rangi
                const colors = ['#8a2be2', '#00ff88', '#ff0080', '#00ffff'];
                const color = colors[Math.floor(Math.random() * colors.length)];
                particle.style.background = color;
                particle.style.boxShadow = `0 0 10px ${color}, 0 0 20px ${color}`;
                
                container.appendChild(particle);
            }
        }
        
        // ========== CURSOR FOLLOWER ==========
        function initCursorFollower() {
            const follower = document.getElementById('cursorFollower');
            let mouseX = 0, mouseY = 0;
            let followerX = 0, followerY = 0;
            
            document.addEventListener('mousemove', function(e) {
                mouseX = e.clientX;
                mouseY = e.clientY;
            });
            
            function animateFollower() {
                // Smooth follow
                followerX += (mouseX - followerX - 10) * 0.1;
                followerY += (mouseY - followerY - 10) * 0.1;
                
                follower.style.left = `${followerX}px`;
                follower.style.top = `${followerY}px`;
                
                // Kursor hover qilganda kattalashishi
                const hoverElements = document.querySelectorAll('.link-card, .link-button');
                let isHovering = false;
                
                hoverElements.forEach(el => {
                    const rect = el.getBoundingClientRect();
                    if (
                        mouseX >= rect.left &&
                        mouseX <= rect.right &&
                        mouseY >= rect.top &&
                        mouseY <= rect.bottom
                    ) {
                        isHovering = true;
                    }
                });
                
                if (isHovering) {
                    follower.style.transform = 'scale(1.5)';
                    follower.style.background = 'radial-gradient(circle, #ff0080, transparent 70%)';
                } else {
                    follower.style.transform = 'scale(1)';
                    follower.style.background = 'radial-gradient(circle, #00ff88, transparent 70%)';
                }
                
                requestAnimationFrame(animateFollower);
            }
            
            animateFollower();
        }
        
        // ========== RIPPLE EFFECT ==========
        function initRippleEffect() {
            document.addEventListener('click', function(e) {
                const ripple = document.createElement('div');
                ripple.classList.add('ripple');
                
                ripple.style.left = `${e.clientX}px`;
                ripple.style.top = `${e.clientY}px`;
                
                document.body.appendChild(ripple);
                
                // Animatsiya tugagach elementni olib tashlash
                setTimeout(() => {
                    ripple.remove();
                }, 1000);
            });
        }
        
        // ========== SCROLL ANIMATIONS ==========
        function initScrollAnimations() {
            const cards = document.querySelectorAll('.link-card');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animation = 'cardEntrance 1s ease-out forwards';
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0) scale(1)';
                    }
                });
            }, {
                threshold: 0.1
            });
            
            cards.forEach(card => {
                observer.observe(card);
            });
            
            // Scroll davomida background rangini o'zgartirish
            window.addEventListener('scroll', function() {
                const scrolled = window.pageYOffset;
                const maxScroll = document.body.scrollHeight - window.innerHeight;
                const scrollPercent = scrolled / maxScroll;
                
                // Background rangini o'zgartirish
                const hue = scrollPercent * 360;
                document.documentElement.style.setProperty('--primary', `hsl(${hue}, 70%, 55%)`);
                document.documentElement.style.setProperty('--secondary', `hsl(${(hue + 120) % 360}, 70%, 55%)`);
                document.documentElement.style.setProperty('--accent', `hsl(${(hue + 240) % 360}, 70%, 55%)`);
            });
        }
        
        // ========== ENTRANCE SOUND EFFECT ==========
        function playEntranceSound() {
            // Bu faqat audio ruxsati bor brauzerlar uchun
            try {
                // Audio kontekst yaratish
                const AudioContext = window.AudioContext || window.webkitAudioContext;
                if (AudioContext) {
                    const audioContext = new AudioContext();
                    
                    // Sintezator yaratish
                    const oscillator = audioContext.createOscillator();
                    const gainNode = audioContext.createGain();
                    
                    oscillator.connect(gainNode);
                    gainNode.connect(audioContext.destination);
                    
                    // Sozlamalar
                    oscillator.type = 'sine';
                    oscillator.frequency.setValueAtTime(220, audioContext.currentTime);
                    oscillator.frequency.exponentialRampToValueAtTime(880, audioContext.currentTime + 0.5);
                    
                    gainNode.gain.setValueAtTime(0.1, audioContext.currentTime);
                    gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.5);
                    
                    // Chalinish va to'xtatish
                    oscillator.start();
                    oscillator.stop(audioContext.currentTime + 0.5);
                }
            } catch (e) {
                console.log("Audio efekti ishlamadi, brauzer ruxsat bermadi");
            }
        }
        
        // ========== DYNAMIC TITLE COLOR CHANGE ==========
        function updateTitleColors() {
            const title = document.querySelector('.main-title');
            let hue = 0;
            
            setInterval(() => {
                hue = (hue + 1) % 360;
                title.style.background = `linear-gradient(90deg, 
                    hsl(${hue}, 70%, 55%), 
                    hsl(${(hue + 120) % 360}, 70%, 55%), 
                    hsl(${(hue + 240) % 360}, 70%, 55%), 
                    hsl(${hue}, 70%, 55%))`;
                title.style.backgroundSize = '300% 100%';
            }, 50);
        }
        
        // Titl ranglarini yangilashni ishga tushirish
        updateTitleColors();
        
        // ========== RANDOM SHAPE GENERATOR ==========
        setInterval(() => {
            const shapesContainer = document.querySelector('.floating-shapes');
            const shape = document.createElement('div');
            shape.classList.add('shape');
            
            // Tasodifiy xususiyatlar
            const size = Math.random() * 200 + 50;
            const posX = Math.random() * 100;
            const posY = Math.random() * 100;
            const hue = Math.random() * 360;
            const duration = Math.random() * 20 + 20;
            
            shape.style.width = `${size}px`;
            shape.style.height = `${size}px`;
            shape.style.left = `${posX}%`;
            shape.style.top = `${posY}%`;
            shape.style.background = `hsl(${hue}, 70%, 55%)`;
            shape.style.animationDuration = `${duration}s`;
            
            shapesContainer.appendChild(shape);
            
            // 30 soniyadan keyin olib tashlash
            setTimeout(() => {
                shape.remove();
            }, 30000);
        }, 5000);
        
        // ========== BACKGROUND INTERACTIVITY ==========
        document.addEventListener('mousemove', (e) => {
            const x = e.clientX / window.innerWidth;
            const y = e.clientY / window.innerHeight;
            
            // Background gradientni siljitish
            document.querySelector('.bg-layer-1').style.background = 
                `radial-gradient(circle at ${x * 100}% ${y * 100}%, rgba(138, 43, 226, 0.15) 0%, transparent 50%),
                 radial-gradient(circle at ${(1 - x) * 100}% ${(1 - y) * 100}%, rgba(0, 255, 136, 0.1) 0%, transparent 50%),
                 radial-gradient(circle at ${y * 100}% ${x * 100}%, rgba(255, 0, 128, 0.1) 0%, transparent 50%)`;
        });
        
        // ========== BUTTON HOVER SOUND EFFECT ==========
        const buttons = document.querySelectorAll('.link-button');
        
        buttons.forEach(button => {
            button.addEventListener('mouseenter', () => {
                try {
                    const AudioContext = window.AudioContext || window.webkitAudioContext;
                    if (AudioContext) {
                        const audioContext = new AudioContext();
                        const oscillator = audioContext.createOscillator();
                        const gainNode = audioContext.createGain();
                        
                        oscillator.connect(gainNode);
                        gainNode.connect(audioContext.destination);
                        
                        oscillator.type = 'sine';
                        oscillator.frequency.setValueAtTime(440, audioContext.currentTime);
                        
                        gainNode.gain.setValueAtTime(0.05, audioContext.currentTime);
                        gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.1);
                        
                        oscillator.start();
                        oscillator.stop(audioContext.currentTime + 0.1);
                    }
                } catch (e) {
                    // Audio ishlamasa, hech narsa qilmaymiz
                }
            });
        });
    </script>
</body>
</html>
