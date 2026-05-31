# First-key-The-heart-of-an-Astrologer
[first key.html](https://github.com/user-attachments/files/28438103/first.key.html)
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Сердце астролога | Полная версия</title>
    <!-- Шрифты: каллиграфический Great Vibes для светлой темы, готический UnifrakturMaguntia для тёмной -->
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;1,400&family=Inter:opsz,wght@14..32,300;400;500;600;700;800&family=Crimson+Text:ital,wght@0,400;0,600;0,700;1,400&family=Great+Vibes&family=UnifrakturMaguntia&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            transition: background-color 0.4s ease, color 0.3s ease, border-color 0.3s ease, box-shadow 0.3s ease;
        }

        body {
            min-height: 100vh;
            position: relative;
            overflow-x: hidden;
            font-size: 18px;
            transition: background-color 0.5s ease, background-image 0.5s ease;
            opacity: 0;
            animation: fadeInBody 0.8s ease forwards;
        }

        @keyframes fadeInBody {
            0% { opacity: 0; }
            100% { opacity: 1; }
        }

        /* ========= АНИМАЦИЯ ДЛЯ КАРТОЧЕК ========= */
        .character-card, .royal-card, .artifact-card, .map-card, .house-card {
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 0.6s ease forwards;
        }

        /* Разные задержки для карточек, чтобы появлялись по очереди */
        .character-card:nth-child(1) { animation-delay: 0.1s; }
        .character-card:nth-child(2) { animation-delay: 0.2s; }
        .character-card:nth-child(3) { animation-delay: 0.3s; }
        .character-card:nth-child(4) { animation-delay: 0.4s; }
        .character-card:nth-child(5) { animation-delay: 0.5s; }
        .character-card:nth-child(6) { animation-delay: 0.6s; }

        .royal-card:nth-child(1) { animation-delay: 0.1s; }
        .royal-card:nth-child(2) { animation-delay: 0.2s; }
        .artifact-card:nth-child(1) { animation-delay: 0.1s; }
        .artifact-card:nth-child(2) { animation-delay: 0.2s; }
        .artifact-card:nth-child(3) { animation-delay: 0.3s; }
        .artifact-card:nth-child(4) { animation-delay: 0.4s; }
        .artifact-card:nth-child(5) { animation-delay: 0.5s; }
        .house-card:nth-child(1) { animation-delay: 0.1s; }
        .house-card:nth-child(2) { animation-delay: 0.2s; }
        .map-accordion-item:nth-child(1) .map-accordion-header { animation-delay: 0.1s; }
        .map-accordion-item:nth-child(2) .map-accordion-header { animation-delay: 0.2s; }
        .map-accordion-item:nth-child(3) .map-accordion-header { animation-delay: 0.3s; }
        .map-accordion-item:nth-child(4) .map-accordion-header { animation-delay: 0.4s; }

        @keyframes fadeInUp {
            0% {
                opacity: 0;
                transform: translateY(20px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Анимация для навигации и заголовков */
        .fixed-nav, .section-header, .royal-nav, .artifacts-nav, footer {
            opacity: 0;
            animation: fadeInUp 0.6s ease forwards;
        }
        .fixed-nav { animation-delay: 0s; }
        .section-header { animation-delay: 0.1s; }
        .royal-nav { animation-delay: 0.15s; }
        .artifacts-nav { animation-delay: 0.2s; }
        footer { animation-delay: 0.5s; }

        /* ========= ФИКСИРОВАННАЯ НАВИГАЦИЯ ========= */
        .fixed-nav {
            position: sticky;
            top: 0;
            z-index: 100;
            backdrop-filter: blur(12px);
            padding: 0.8rem 2rem;
            margin-bottom: 1rem;
            transition: all 0.2s;
            text-align: center;
            transition: background-color 0.3s ease, backdrop-filter 0.3s ease;
        }
        .fixed-nav .title-row {
            display: flex;
            justify-content: center;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
            margin-bottom: 0.5rem;
        }
        .fixed-nav .title-area {
            text-align: center;
        }
        .fixed-nav .title-area h1 {
            font-size: 2rem;
            background: linear-gradient(135deg, #b56a2c, #6b3f1f);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            letter-spacing: 1px;
            transition: text-shadow 0.3s ease, filter 0.3s ease;
        }
        .fixed-nav .title-area h1::before {
            display: inline-block;
            margin-right: 8px;
            background: linear-gradient(135deg, #b56a2c, #6b3f1f);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }
        body.light-theme .fixed-nav .title-area h1::before {
            content: "✶";
            font-size: 1.9rem;
        }
        body.dark-theme .fixed-nav .title-area h1::before {
            content: "⛧";
            font-size: 1.9rem;
        }
        body.light-theme .fixed-nav .title-area h1 {
            text-shadow: 3px 3px 8px rgba(80, 45, 15, 0.35);
        }
        body.dark-theme .fixed-nav .title-area h1 {
            text-shadow: 0 0 6px rgba(200, 140, 60, 0.45), 0 0 2px rgba(200, 140, 60, 0.3);
            filter: drop-shadow(0 0 3px rgba(180, 120, 50, 0.4));
        }
        .fixed-nav .title-area p {
            font-size: 0.85rem;
            opacity: 0.7;
        }
        .fixed-nav .toggle-switch {
            background: rgba(0,0,0,0.08);
            padding: 0.3rem 1rem;
            border-radius: 60px;
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
        }
        .fixed-nav .nav-links {
            display: flex;
            flex-wrap: nowrap;
            justify-content: flex-start;
            gap: 1.5rem;
            margin-top: 0.8rem;
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 60px;
            width: 100%;
            margin-left: auto;
            margin-right: auto;
            overflow-x: auto;
            overflow-y: hidden;
            -webkit-overflow-scrolling: touch;
            scrollbar-width: thin;
        }
        .fixed-nav .nav-links::-webkit-scrollbar {
            height: 3px;
        }
        .fixed-nav .nav-links::-webkit-scrollbar-track {
            background: rgba(0,0,0,0.1);
            border-radius: 10px;
        }
        .fixed-nav .nav-links::-webkit-scrollbar-thumb {
            background: rgba(0,0,0,0.3);
            border-radius: 10px;
        }
        .fixed-nav .nav-link {
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            padding: 0.4rem 1rem;
            border-radius: 40px;
            transition: 0.2s;
            white-space: nowrap;
        }
        .toggle-label {
            font-size: 0.9rem;
        }
        .switch {
            position: relative;
            display: inline-block;
            width: 56px;
            height: 28px;
        }
        .switch input {
            opacity: 0;
            width: 0;
            height: 0;
        }
        .slider {
            position: absolute;
            cursor: pointer;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: #ccc;
            border-radius: 34px;
            transition: 0.3s;
        }
        .slider:before {
            position: absolute;
            content: "☀️";
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1rem;
            height: 22px;
            width: 22px;
            left: 3px;
            bottom: 3px;
            background-color: white;
            border-radius: 50%;
            transition: 0.3s;
            box-shadow: 0 1px 3px rgba(0,0,0,0.2);
        }
        input:checked + .slider:before {
            content: "🌙";
            transform: translateX(28px);
        }
        input:checked + .slider {
            background-color: #3a2c28;
        }

        /* ========= МОБИЛЬНЫЕ ПРАВКИ (ГОРИЗОНТАЛЬНАЯ ПРОКРУТКА) ========= */
        @media (max-width: 900px) {
            .fixed-nav {
                padding: 0.6rem 1rem;
            }
            .fixed-nav .title-area h1 {
                font-size: 1.5rem;
            }
            .fixed-nav .title-area p {
                font-size: 0.7rem;
            }
            .fixed-nav .nav-links {
                gap: 0.8rem;
                padding: 0.4rem 0.8rem;
            }
            .fixed-nav .nav-link {
                font-size: 0.75rem;
                padding: 0.3rem 0.7rem;
            }
            .toggle-label {
                font-size: 0.7rem;
            }
            .toggle-switch {
                padding: 0.2rem 0.7rem;
            }
            .switch {
                width: 42px;
                height: 22px;
            }
            .slider:before {
                height: 16px;
                width: 16px;
                font-size: 0.7rem;
            }
            input:checked + .slider:before {
                transform: translateX(20px);
            }
            .section-header h2 {
                font-size: 1.6rem;
            }
            .card-name {
                font-size: 1.3rem;
            }
            .artifact-card.card-tarot::after,
            .artifact-card.card-star-keys::after {
                width: 40px;
                height: 40px;
                top: 12px;
                left: 12px;
            }
            .artifact-card.card-tarot .artifact-name,
            .artifact-card.card-star-keys .artifact-name {
                padding-left: 60px;
            }
            .royal-nav-btn, .art-nav-btn, .subnav-btn {
                padding: 0.4rem 1rem;
                font-size: 0.8rem;
            }
        }

        .archive-container {
            max-width: 1300px;
            margin: 0 auto;
            padding: 0 2rem 3rem;
        }

        /* ========= СЕТКИ ========= */
        .characters-grid, .royal-grid, .artifact-grid, .map-regions-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin: 2rem 0 3rem;
            scroll-margin-top: 120px;
        }
        .character-card, .royal-card, .artifact-card, .map-card {
            border-radius: 32px;
            padding: 1.5rem;
            backdrop-filter: blur(4px);
            transition: transform 0.25s, box-shadow 0.3s, background-color 0.2s;
            cursor: pointer;
        }
        .character-card:hover, .royal-card:hover, .artifact-card:hover, .map-card:hover {
            transform: translateY(-6px);
        }
        .card-name {
            font-size: 1.8rem;
            font-weight: 600;
            margin-bottom: 0.6rem;
            border-left: 4px solid #d9a13b;
            padding-left: 0.8rem;
        }
        .card-role {
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            margin-bottom: 1rem;
            opacity: 0.8;
        }
        .card-desc {
            font-size: 1rem;
            line-height: 1.45;
            margin-bottom: 1rem;
        }
        .card-tag, .royal-tag, .artifact-tag, .map-tag {
            display: inline-block;
            padding: 0.25rem 0.9rem;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 600;
        }
        
        /* Убираем эмодзи из карточек артефактов */
        .artifact-icon {
            display: none;
        }

        /* ========= РАЗДЕЛЫ ========= */
        .map-section, .royal-section, .artifacts-section {
            margin: 3rem 0 2rem;
            padding: 2rem 1.5rem;
            border-radius: 48px;
            scroll-margin-top: 120px;
            transition: background-color 0.4s ease, border-color 0.3s ease;
        }
        .section-header {
            text-align: center;
            margin-bottom: 2rem;
        }
        .section-header h2 {
            font-size: 2.2rem;
            letter-spacing: 2px;
        }
        .royal-nav, .artifacts-nav, .royal-subnav {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin: 1.5rem 0 2rem;
            flex-wrap: wrap;
        }
        .royal-nav-btn, .art-nav-btn, .subnav-btn {
            padding: 0.7rem 2rem;
            border-radius: 40px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: 0.2s;
            border: none;
            font-family: inherit;
        }
        .royal-category, .artifact-category {
            display: none;
        }
        .royal-category.active-category, .artifact-category.active-category {
            display: block;
        }
        .royal-grid {
            display: none;
        }
        .royal-grid.active-subcat {
            display: grid;
        }
        .historical-text {
            font-size: 1rem;
            line-height: 1.55;
            margin: 1rem 0;
            padding: 1.2rem;
            border-radius: 28px;
            transition: background-color 0.3s ease;
        }

        /* ========= МОДАЛКИ ========= */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(6px);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        .modal.show {
            display: flex;
            opacity: 1;
        }
        .modal-content {
            max-width: 600px;
            width: 90%;
            border-radius: 48px;
            padding: 2rem;
            position: relative;
            max-height: 85vh;
            overflow-y: auto;
        }
        .modal-close {
            position: absolute;
            top: 1rem;
            right: 1.5rem;
            font-size: 2rem;
            cursor: pointer;
        }
        .dossier-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
            margin: 1.5rem 0;
        }
        .dossier-item {
            border-bottom: 1px dashed rgba(128,128,128,0.3);
            padding-bottom: 0.5rem;
        }
        .dossier-label {
            font-size: 0.8rem;
            font-weight: 600;
            opacity: 0.8;
        }
        .dossier-value {
            font-size: 1.1rem;
            font-weight: 500;
            margin-top: 0.2rem;
        }
        .magic-desc, .history-desc {
            margin-top: 1rem;
            padding: 1rem;
            border-radius: 24px;
            font-size: 1rem;
            line-height: 1.45;
        }

        /* ========= СВЕТЛАЯ ТЕМА (каллиграфический шрифт) ========= */
        body.light-theme {
            background: #fef5e8;
            font-family: 'Playfair Display', 'Times New Roman', serif;
            color: #3a2a1f;
            font-size: 18px;
            position: relative;
            background-image: radial-gradient(circle at 15% 25%, rgba(200, 160, 100, 0.25) 2px, transparent 2px), radial-gradient(circle at 75% 60%, rgba(180, 130, 70, 0.2) 3px, transparent 3px), radial-gradient(circle at 45% 85%, rgba(190, 140, 80, 0.22) 2.5px, transparent 2.5px), repeating-linear-gradient(45deg, rgba(180, 140, 90, 0.06) 0px, rgba(180, 140, 90, 0.06) 2px, transparent 2px, transparent 8px), repeating-linear-gradient(135deg, rgba(160, 120, 70, 0.05) 0px, rgba(160, 120, 70, 0.05) 1px, transparent 1px, transparent 12px);
            background-size: 80px 80px, 150px 150px, 200px 200px, 60px 60px, 80px 80px;
        }
        /* Каллиграфические заголовки Great Vibes на светлой теме */
        body.light-theme .section-header h2,
        body.light-theme .fixed-nav .title-area h1,
        body.light-theme .modal-title,
        body.light-theme .card-name,
        body.light-theme .royal-nav-btn,
        body.light-theme .art-nav-btn,
        body.light-theme .subnav-btn,
        body.light-theme .house-name {
            font-family: 'Great Vibes', 'Playfair Display', cursive;
            font-weight: normal;
            letter-spacing: 1px;
        }
        body.light-theme .fixed-nav .title-area h1 {
            font-family: 'Great Vibes', cursive;
            font-size: 2.2rem;
        }
        body.light-theme .fixed-nav { background: rgba(254, 245, 232, 0.96); border-bottom: 1px solid #e8d5bc; }
        body.light-theme .fixed-nav .nav-links { background: #f0e2d0; }
        body.light-theme .nav-link { color: #7a4a2a; font-family: 'Playfair Display', serif; }
        body.light-theme .nav-link:hover { background: #c98a4a; color: white; }
        body.light-theme .toggle-switch { background: #e8d5bc; border: 1px solid #c9a87a; box-shadow: 0 0 6px rgba(170, 120, 60, 0.2); }
        body.light-theme .toggle-label { color: #5a3a22; }
        body.light-theme .switch .slider { background-color: #c9a87a; }
        body.light-theme .switch .slider:before { background-color: #fef0e0; }
        body.light-theme .switch input:checked + .slider { background-color: #d9a13b; }
        body.light-theme .character-card, body.light-theme .royal-card, body.light-theme .artifact-card, body.light-theme .map-card { background: rgba(255, 248, 240, 0.92); border: 1px solid #e8d5bc; }
        body.light-theme .character-card:hover, body.light-theme .royal-card:hover, body.light-theme .artifact-card:hover, body.light-theme .map-card:hover { background: #fff6ea; }
        body.light-theme .map-section, body.light-theme .royal-section, body.light-theme .artifacts-section { background: rgba(255, 245, 235, 0.65); border: 1px solid #e8d5bc; }
        body.light-theme .royal-nav-btn, body.light-theme .art-nav-btn, body.light-theme .subnav-btn { background: #f0e2d0; color: #6a4528; border: 1px solid #e0c8a8; }
        body.light-theme .royal-nav-btn.active, body.light-theme .art-nav-btn.active, body.light-theme .subnav-btn.active { background: #d9a13b; color: white; }
        body.light-theme .historical-text, body.light-theme .magic-desc, body.light-theme .history-desc { background: rgba(0, 0, 0, 0.04); }
        body.light-theme .modal-content { background: #fffaf2; border: 1px solid #e8d5bc; }
        body.light-theme::before {
            content: "✧ ✦ ✧ ✦ ✶ ✷ ✸ ✹ ✺ ✻ ⚹ ✹ ✸ ✧";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            font-size: 140px;
            font-weight: normal;
            text-align: center;
            pointer-events: none;
            color: rgba(180, 130, 70, 0.1);
            white-space: normal;
            word-break: break-all;
            line-height: 1.2;
            z-index: 0;
            font-family: monospace;
            letter-spacing: 25px;
            transform: rotate(-5deg);
        }
        body.light-theme::after { display: none; }

        /* ========= ТЁМНАЯ ТЕМА (готический руноподобный шрифт) ========= */
        body.dark-theme {
            background: #0c0a08;
            color: #e3d5c2;
            font-family: 'Crimson Text', 'Inter', 'Courier New', monospace;
            font-size: 18px;
            font-weight: 400;
            background-image: radial-gradient(circle at 20% 30%, rgba(160, 40, 40, 0.15) 8px, transparent 8px), radial-gradient(circle at 80% 70%, rgba(180, 50, 45, 0.12) 12px, transparent 12px), repeating-linear-gradient(0deg, rgba(120, 30, 25, 0.1) 0px, rgba(120, 30, 25, 0.1) 3px, transparent 3px, transparent 30px), repeating-linear-gradient(90deg, rgba(100, 25, 20, 0.08) 0px, rgba(100, 25, 20, 0.08) 2px, transparent 2px, transparent 25px);
            background-size: 200px 200px, 250px 250px, 60px 60px, 70px 70px;
            position: relative;
        }
        /* Готические заголовки UnifrakturMaguntia на тёмной теме */
        body.dark-theme .card-name, 
        body.dark-theme .royal-card .card-name,
        body.dark-theme .modal-title,
        body.dark-theme .section-header h2,
        body.dark-theme .fixed-nav .title-area h1,
        body.dark-theme .royal-nav-btn,
        body.dark-theme .art-nav-btn,
        body.dark-theme .subnav-btn,
        body.dark-theme .house-name {
            font-family: 'UnifrakturMaguntia', 'Courier New', monospace;
            letter-spacing: 2px;
            font-weight: normal;
            font-style: normal;
        }
        body.dark-theme .fixed-nav .title-area h1 {
            font-size: 2rem;
        }
        body.dark-theme .fixed-nav { background: rgba(12, 10, 8, 0.96); border-bottom: 1px solid #4f3827; }
        body.dark-theme .fixed-nav .nav-links { background: #2a1e18; }
        body.dark-theme .nav-link { color: #dac29c; font-family: 'Inter', monospace; }
        body.dark-theme .nav-link:hover { background: #a56e3e; color: #1a1511; }
        body.dark-theme .toggle-switch { background: #3a2a24; border: 1px solid #c69c6d; box-shadow: 0 0 8px rgba(198, 156, 109, 0.3); }
        body.dark-theme .toggle-label { color: #f0d8b0; }
        body.dark-theme .switch .slider { background-color: #5a3a2a; }
        body.dark-theme .switch .slider:before { background-color: #f5e2b0; box-shadow: 0 0 4px #ffdd99; }
        body.dark-theme .switch input:checked + .slider { background-color: #a56e3e; }
        body.dark-theme .character-card, body.dark-theme .royal-card, body.dark-theme .artifact-card, body.dark-theme .map-card { background: #1e1915; border: 1px solid #4f3827; }
        body.dark-theme .character-card:hover, body.dark-theme .royal-card:hover, body.dark-theme .artifact-card:hover, body.dark-theme .map-card:hover { background: #3a2c24; }
        body.dark-theme .map-section, body.dark-theme .royal-section, body.dark-theme .artifacts-section { background: rgba(20, 15, 12, 0.8); border: 1px solid #4f3827; }
        body.dark-theme .royal-nav-btn, body.dark-theme .art-nav-btn, body.dark-theme .subnav-btn { background: #2a211c; color: #dac29c; border: 1px solid #5e3a2a; }
        body.dark-theme .royal-nav-btn.active, body.dark-theme .art-nav-btn.active, body.dark-theme .subnav-btn.active { background: #a56e3e; color: #1a1511; }
        body.dark-theme .historical-text, body.dark-theme .magic-desc, body.dark-theme .history-desc { background: rgba(255,255,200,0.05); }
        body.dark-theme .modal-content { background: #1a1511; border: 1px solid #5e3e2c; }
        body.dark-theme::before {
            content: "⛧ ⛤ ⛧ ⛤ ⛧";
            position: fixed;
            bottom: 20px;
            left: 0;
            width: 100%;
            text-align: center;
            font-size: 48px;
            letter-spacing: 35px;
            opacity: 0.2;
            pointer-events: none;
            color: #aa4a3a;
            font-family: monospace;
            z-index: 0;
        }
        body.dark-theme::after {
            content: "✹ ✺ ✻ ✼ ✽ ✾ ✿ ❀ ⛧ ⛤ ✠ ᚠ ᚢ ᚦ ᚨ ᚱ ᚲ ᚷ ᚹ ᚺ ᚾ ᛁ ᛃ ᛇ ᛈ ᛉ ᛊ";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            font-size: 110px;
            font-weight: normal;
            text-align: center;
            pointer-events: none;
            color: rgba(140, 45, 40, 0.12);
            white-space: normal;
            word-break: break-all;
            line-height: 1.3;
            z-index: 0;
            font-family: monospace;
            letter-spacing: 18px;
            transform: rotate(3deg);
        }
        body.dark-theme .archive-container { position: relative; z-index: 2; }

        /* ========= ФОН ДЛЯ АРТЕФАКТОВ ========= */
        #astralCategory .artifact-card { position: relative; overflow: hidden; }
        #astralCategory .artifact-card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url('пнг для архива/tarot.png');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            opacity: 0.2;
            pointer-events: none;
            z-index: 0;
            border-radius: 32px;
            transition: opacity 0.3s;
        }
        #astralCategory .artifact-card:hover::before { opacity: 0.35; }
        #astralCategory .artifact-card .artifact-icon,
        #astralCategory .artifact-card .artifact-name,
        #astralCategory .artifact-card .artifact-desc,
        #astralCategory .artifact-card .artifact-tag { position: relative; z-index: 2; }

        #necroCategory .artifact-card { position: relative; overflow: hidden; }
        #necroCategory .artifact-card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            pointer-events: none;
            z-index: 0;
            border-radius: 32px;
            transition: opacity 0.3s;
        }
        body.light-theme #necroCategory .artifact-card::before {
            background-image: url('пнг для архива/necromancy.png');
            opacity: 0.15;
        }
        body.dark-theme #necroCategory .artifact-card::before {
            background-image: url('пнг для архива/necromancy.png');
            opacity: 0.3;
        }
        #necroCategory .artifact-card:hover::before { opacity: 0.4; }
        #necroCategory .artifact-card .artifact-icon,
        #necroCategory .artifact-card .artifact-name,
        #necroCategory .artifact-card .artifact-desc,
        #necroCategory .artifact-card .artifact-tag { position: relative; z-index: 2; }

        /* ========= PNG-ИКОНКИ В МОДАЛЬНЫХ ОКНАХ ========= */
        .artifact-modal.tarot-modal .artifact-modal-icon { display: none; }
        .artifact-modal.tarot-modal .modal-content::before {
            content: "";
            display: block;
            width: 70px;
            height: 70px;
            background-image: url('пнг для архива/sun_tarot.png');
            background-size: contain;
            background-repeat: no-repeat;
            margin: 0 auto 15px auto;
        }
        .artifact-modal.keys-modal .artifact-modal-icon { display: none; }
        .artifact-modal.keys-modal .modal-content::before {
            content: "";
            display: block;
            width: 70px;
            height: 70px;
            background-image: url('пнг для архива/key_light.png');
            background-size: contain;
            background-repeat: no-repeat;
            margin: 0 auto 15px auto;
        }

        /* ========= СТИЛИ ДЛЯ КАРТЫ (АККОРДЕОН) ========= */
        .map-list {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }
        .map-accordion-item {
            border-radius: 24px;
            overflow: hidden;
            transition: all 0.2s;
        }
        .map-accordion-header {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem 1.5rem;
            cursor: pointer;
            transition: 0.2s;
            font-weight: 600;
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 0.6s ease forwards;
        }
        .map-accordion-header:hover {
            background: rgba(0,0,0,0.05);
        }
        .map-accordion-icon {
            font-size: 1.8rem;
        }
        .map-accordion-title {
            font-size: 1.2rem;
            flex: 1;
            text-align: left;
        }
        .map-accordion-arrow {
            font-size: 1.2rem;
            transition: transform 0.2s;
        }
        .map-accordion-item.active .map-accordion-arrow {
            transform: rotate(90deg);
        }
        .map-accordion-content {
            max-height: 0;
            padding: 0 1.5rem;
            overflow: hidden;
            transition: max-height 0.3s ease-out, padding 0.3s ease;
        }
        .map-accordion-item.active .map-accordion-content {
            max-height: 300px;
            padding: 0 1.5rem 1.2rem 1.5rem;
        }
        .map-accordion-content p {
            margin: 0.5rem 0;
            line-height: 1.5;
        }
        body.light-theme .map-accordion-header {
            background: rgba(255, 245, 235, 0.8);
            border: 1px solid #e8d5bc;
        }
        body.dark-theme .map-accordion-header {
            background: rgba(30, 25, 21, 0.9);
            border: 1px solid #4f3827;
        }
        body.light-theme .map-accordion-content {
            background: rgba(255, 248, 240, 0.6);
        }
        body.dark-theme .map-accordion-content {
            background: rgba(20, 15, 12, 0.8);
        }

        /* ========= СТИЛИ ДЛЯ ПРИДВОРНЫХ ДОМОВ ========= */
        .houses-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.5rem;
            margin-top: 1rem;
        }
        .house-card {
            padding: 1.2rem;
            border-radius: 28px;
            transition: transform 0.2s, background 0.2s;
            cursor: pointer;
        }
        .house-card:hover {
            transform: translateY(-4px);
        }
        .house-icon {
            font-size: 2rem;
            margin-bottom: 0.5rem;
        }
        .house-name {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 0.3rem;
        }
        .house-motto {
            font-style: italic;
            font-size: 0.85rem;
            opacity: 0.8;
            margin-bottom: 0.5rem;
        }
        .house-desc {
            font-size: 0.9rem;
            line-height: 1.4;
        }
        body.light-theme .house-card {
            background: rgba(255, 248, 240, 0.7);
            border: 1px solid #e8d5bc;
        }
        body.dark-theme .house-card {
            background: rgba(30, 25, 21, 0.8);
            border: 1px solid #4f3827;
        }

        @media (max-width: 700px) {
            .archive-container { padding: 0 1rem 2rem; }
            body, body.light-theme, body.dark-theme { font-size: 16px; }
            .card-name { font-size: 1.5rem; }
            .royal-subnav { gap: 0.8rem; }
            .subnav-btn { padding: 0.5rem 1rem; font-size: 0.8rem; }
        }
        footer {
            text-align: center;
            margin-top: 3rem;
            opacity: 0.6;
            font-size: 0.8rem;
        }
    </style>
</head>
<body class="light-theme">
    <div class="fixed-nav">
        <div class="title-row">
            <div class="title-area">
                <h1>Сердце астролога: первый ключ</h1>
                <p>Нажми на карточку — откроется полное досье</p>
            </div>
            <div class="toggle-switch">
                <span class="toggle-label">🌿 Астральная</span>
                <label class="switch">
                    <input type="checkbox" id="themeToggle">
                    <span class="slider"></span>
                </label>
                <span class="toggle-label">🦴 Некромантия</span>
            </div>
        </div>
        <div class="nav-links">
            <div class="nav-link" data-nav="dossier">📜 ДОСЬЕ ПЕРСОНАЖЕЙ</div>
            <div class="nav-link" data-nav="map">🗺️ КАРТА</div>
            <div class="nav-link" data-nav="royal">👑 КОРОЛЕВСКАЯ ДИНАСТИЯ</div>
            <div class="nav-link" data-nav="artifacts">⚱️ АРТЕФАКТЫ</div>
        </div>
    </div>

    <div class="archive-container">
        <!-- ========= ПЕРСОНАЖИ ========= -->
        <div class="section-header">
            <h2>📜 Персонажи</h2>
            <p>Герои этого мира — нажми на карточку, чтобы узнать тайны</p>
        </div>
        <div class="characters-grid" id="charactersGrid"></div>

        <!-- ========= КАРТА (АККОРДЕОН) ========= -->
        <div class="map-section" id="mapSection">
            <div class="section-header"><h2>🗺️ Карта Эфемерных Земель</h2><p>Звёздные тропы и некрополи — нажми на регион, чтобы узнать подробности</p></div>
            <div class="map-list" id="mapAccordion"></div>
            <p style="text-align:center; margin-top:1rem;"><small>✦ Позже здесь появится PNG-карта ✦</small></p>
        </div>

        <!-- ========= КОРОЛЕВСКАЯ ДИНАСТИЯ + ПРИДВОРНЫЕ ДОМА ========= -->
        <div class="royal-section" id="royalSection">
            <div class="section-header"><h2>👑 Королевская династия</h2><p>Кровь древних правителей и знатные дома</p></div>
            <div class="royal-nav">
                <button class="royal-nav-btn active" data-royal-cat="royal">🏰 Королевская кровь</button>
                <button class="royal-nav-btn" data-royal-cat="houses">🏛️ Придворные дома</button>
            </div>
            <!-- Королевская кровь -->
            <div class="royal-category active-category" id="royalBloodCategory">
                <div class="royal-subnav">
                    <button class="subnav-btn active" data-subcat="first">🏰 Первое поколение</button>
                    <button class="subnav-btn" data-subcat="new">👑 Новое поколение</button>
                    <button class="subnav-btn" data-subcat="heirs">⭐ Наследники</button>
                </div>
                <div class="historical-text" id="royalHistoricalText">📜 <strong>Король-Астролог Артемий I</strong> объединил земли под знаком Солнца и Луны. Королева-Ведьма Мелисандра открыла врата между мирами. Их правление длилось 400 лет и оставило после себя Семь Ключей.</div>
                <div id="firstGenGrid" class="royal-grid active-subcat"></div>
                <div id="newGenGrid" class="royal-grid"></div>
                <div id="heirsGrid" class="royal-grid"></div>
            </div>
            <!-- Придворные дома -->
            <div class="royal-category" id="housesCategory">
                <div class="houses-grid" id="housesGrid"></div>
            </div>
        </div>

        <!-- ========= АРТЕФАКТЫ ========= -->
        <div class="artifacts-section" id="artifactsSection">
            <div class="section-header"><h2>🏺 Сокровищница Артефактов</h2><p>Реликвии света и тьмы</p></div>
            <div class="artifacts-nav">
                <button class="art-nav-btn active" data-art-cat="astral">✨ Астрологические</button>
                <button class="art-nav-btn" data-art-cat="necro">💀 Некромантии</button>
            </div>
            <div class="artifact-category active-category" id="astralCategory">
                <div class="artifact-grid" id="astralArtifactsGrid"></div>
            </div>
            <div class="artifact-category" id="necroCategory">
                <div class="artifact-grid" id="necroArtifactsGrid"></div>
            </div>
        </div>
        <footer>✦ Свет и Тьма. Нажми на карточку — откроется детальное досье. Карта и артефакты ждут твоего прикосновения ✦</footer>
    </div>

    <!-- МОДАЛЬНЫЕ ОКНА -->
    <div id="dossierModal" class="modal"><div class="modal-content"><span class="modal-close">&times;</span><div class="modal-title" id="modalName"></div><div class="modal-sub" id="modalSub"></div><div class="dossier-grid" id="dossierFields"></div><div class="magic-desc"><strong>✨ Магия:</strong> <span id="magicDetails"></span></div></div></div>
    <div id="artifactModal" class="modal artifact-modal"><div class="modal-content"><span class="modal-close">&times;</span><div class="artifact-icon" id="artifactModalIcon">🏺</div><div class="modal-title" id="artifactModalName"></div><div class="modal-sub" id="artifactModalSub"></div><div class="dossier-grid" id="artifactDossierFields"></div><div class="magic-desc"><strong>🔮 Магические способности:</strong> <span id="artifactMagicDetails"></span></div><div class="history-desc"><strong>📜 Легенда:</strong> <span id="artifactHistory"></span></div></div></div>
    <div id="royalModal" class="modal"><div class="modal-content"><span class="modal-close">&times;</span><div class="modal-title" id="royalModalName"></div><div class="modal-sub" id="royalModalRole"></div><div class="dossier-grid" id="royalDossierFields"></div><div class="magic-desc"><strong>✨ Магический дар:</strong> <span id="royalMagic"></span></div><div class="history-desc"><strong>📜 Интересный факт:</strong> <span id="royalFact"></span></div></div></div>
    <div id="houseModal" class="modal"><div class="modal-content"><span class="modal-close">&times;</span><div class="modal-title" id="houseModalName"></div><div class="modal-sub" id="houseModalMotto"></div><div class="dossier-grid" id="houseDossierFields"></div><div class="magic-desc"><strong>🏛️ О доме:</strong> <span id="houseDescription"></span></div><div class="history-desc"><strong>📜 Интересный факт:</strong> <span id="houseFact"></span></div></div></div>

    <script>
        // ========= 1. ПЕРСОНАЖИ =========
        const charactersData = [
            { name: "Виалье Адельва", role: "✦ Духовный астролог ✦", shortDesc: "Юный лорд семьи Адельва, заканчивает 4 курс Института магии им. Св. Сальмари.", tag: "♒ астролог-практикант", height: "172 см", weight: "70 кг", age: "26 лет", residence: "Институт магии им. Св. Сальмари", magicDesc: "Использует астральные артефакты для материализации маны. Читает судьбу по звёздам, перемещается в астрале, ориентируется в межзвёздном пространстве и знает расположение самых выгодных вселенных.", generalDesc: "Юный лорд семьи Адельва, третий из пяти детей, второй сын. Заканчивает 4 курс высшего образования из 6. После появления личных документов у Мерлина (Велес Фокс), стал официальным Доминусом и получил титул Барона звездного дома. После окончания Института получит право на владение 5 отдельными мирами и повысит статус до Графа. На теле имеет четыре родимых астрологических следа (солнце и луна на каждом бедре, созвездие Водолея внизу живота и аркан звезды между лопаток). К 30 годам появится ещё один.", artifacts: "Владеет 10 золотыми зодиакальными ключами (призывают и материализуют духов Зодиаков) и 72 серебряными созвездиальными ключами (призывают и материализуют духов Созвездий). Также имеет карты Таро (не оригинальные, серебряные), ноктурлабиум и звёздный кнут." },
            { name: "Велес (Уильям) Фокс", role: "✦ Некромант ✦", shortDesc: "Мерлин (Доминус - Виалье Адельва). Происхождением со вселенной третьего кольца.", tag: "⭐ некромант-теоретик", height: "187 см", weight: "85 кг", age: "24 года", residence: "Институт магии им. Св. Сальмари", magicDesc: "Использует ритуальные письмена и сборники демонологии для магии поддержки (маг-теоретик). В будущем получит право на использование магии призыва и практике общения с мёртвыми (после окончания 2 курса).", generalDesc: "Мерлин (Доминус - Виалье Адельва). Происхождением со вселенной третьего кольца. Единственный ребёнок в семье, отец неизвестен, мать - Джейн Фокс. В данный момент находится на 1 курсе обучения Института. Не имеет статуса, но обладает выдающимися способностями и объёмным резервом маны (необычно для уроженца третьего кольца). После окончания первого курса получит право на хранение личных артефактов (до 3 предметов), в данный момент пользуется амулетами из личной коллекции Доминуса. Метка Мерлина проявилась на лбу (из-за принадлежания представителю астрологической магии метка имеет форму шестиконечной звезды). К 25 годам появится родимая метка некроманта.", artifacts: "Фульгурит, ритуальный нож, нож из нержавеющей стали, ожерелье из астрального нефрита." }
        ];

        // ========= 2. КАРТА (АККОРДЕОН) =========
        const mapRegionsData = [
            { name: "Астральный Архипелаг", icon: "✨🌊", description: "Семь островов, соединённых мостами из лунного света. Здесь обитают провидцы и звёздные драконы. Главный город — Звездоград." },
            { name: "Некрополь Теней", icon: "💀🏚️", description: "Земли, где грань между жизнью и смертью истончена. Тени прошлого бродят среди руин. Резиденция Морвена — Склепы Эфемерной Гряды." },
            { name: "Королевский Домен", icon: "👑🏰", description: "Сердце королевства. Здесь находятся Тронный Зал и руины Солнечного Замка. Земли, хранящие память о первых королях." },
            { name: "Долина Артефактов", icon: "🏺🔮", description: "Таинственная долина, где спрятаны древние артефакты. Музей Вечных Реликвий ждёт искателей. Говорят, здесь исполняются желания." }
        ];

        function renderMapAccordion() {
            const container = document.getElementById('mapAccordion');
            if (!container) return;
            container.innerHTML = '';
            mapRegionsData.forEach((region, idx) => {
                const item = document.createElement('div');
                item.className = 'map-accordion-item';
                item.innerHTML = `
                    <div class="map-accordion-header" data-idx="${idx}" style="animation-delay: ${0.1 + idx * 0.1}s">
                        <span class="map-accordion-icon">${region.icon}</span>
                        <span class="map-accordion-title">${region.name}</span>
                        <span class="map-accordion-arrow">▶</span>
                    </div>
                    <div class="map-accordion-content">
                        <p>${region.description}</p>
                    </div>
                `;
                container.appendChild(item);
            });
            document.querySelectorAll('.map-accordion-header').forEach(header => {
                header.addEventListener('click', () => {
                    const parent = header.parentElement;
                    parent.classList.toggle('active');
                });
            });
        }

        // ========= 3. КОРОЛЕВСКАЯ СЕМЬЯ =========
        const firstGen = [
            { name: "Артемий I", role: "Король-Астролог, основатель", icon: "👑🔭", age: "вечность в легендах", magic: "Звёздное провидение", fact: "Построил первый замок на костях дракона.", residence: "Замок Сириус" },
            { name: "Мелисандра", role: "Королева-Ведьма", icon: "🌙🐉", age: "бессмертна в сказаниях", magic: "Межмировая магия", fact: "Могла говорить с тенями умерших королей.", residence: "Чёрный Чертог" }
        ];
        const newGen = [
            { name: "Вальдемар II", role: "Король Теней и Света", icon: "⚔️👑", age: "187 лет", magic: "Баланс Некроса", fact: "Лично участвовал в битве за Долину Артефактов.", residence: "Тронный Зал" },
            { name: "Ирма", role: "Королева Целительница", icon: "🌹✨", age: "163 года", magic: "Жизненная магия роз", fact: "Вырастила целебный сад посреди пустоши.", residence: "Белый Сад" }
        ];
        const heirs = [
            { name: "Амелия", role: "Наследная принцесса", icon: "👸🌟", age: "47 лет", magic: "Астральный доспех", fact: "Первая женщина-командор звёздной стражи.", residence: "Башня Рассвета" },
            { name: "Корнелиус", role: "Принц-инквизитор", icon: "🤴📜", age: "41 год", magic: "Правда крови", fact: "Раскрыл заговор теней в Совете.", residence: "Цитадель" }
        ];

        // ========= 4. ПРИДВОРНЫЕ ДОМА =========
        const housesData = [
            { name: "Дом Лунного Света", icon: "🌙✨", motto: "«Тишина скрывает правду»", description: "Древний род шпионов и дипломатов. Их влияние простирается от теней до трона. Хранители ночных секретов.", fact: "Члены дома никогда не произносят своё имя вслух в присутствии посторонних." },
            { name: "Дом Тернового Венца", icon: "🌹⚔️", motto: "«Кровью и шипами»", description: "Военачальники и хранители границ. Верны короне, но опасны для врагов. Их крепость стоит на краю Некрополя.", fact: "Говорят, что каждый воин дома носит шип из чёрной розы на шее." }
        ];

        // ========= АРТЕФАКТЫ =========
        const astralArtifacts = [
            { name: "Карты Таро", icon: "", category: "Астрологический", tag: "прорицание", magicAbility: "Предсказывают судьбу по звёздному расположению. Каждая карта — ключ к астральной проекции.", history: "Созданы первым астрологом Элианом. Колода сама выбирает владельца.", customClass: "card-tarot" },
            { name: "Звёздные ключи", icon: "", category: "Астрологический", tag: "пространство", magicAbility: "Открывают врата между созвездиями. Проявляют звёздную тропу.", history: "Выкованы из метеоритного железа в день равноденствия.", customClass: "card-star-keys" },
            { name: "Звёздный кнут", icon: "", category: "Астрологический", tag: "световой удар", magicAbility: "Излучает звёздную плазму, рассеивает тёмные чары.", history: "Принадлежал звёздной страже. Его щелчок слышен по всему архипелагу.", customClass: "" },
            { name: "Ноктурлабиум", icon: "", category: "Астрологический", tag: "навигация", magicAbility: "Позволяет видеть невидимые созвездия и рассчитывать духовные приливы.", history: "Спасён из рухнувшей обсерватории.", customClass: "" },
            { name: "Доска Уиджа (звёздный вариант)", icon: "", category: "Астрологический", tag: "спиритизм", magicAbility: "Общается с астральными сущностями.", history: "Создана на стыке астрологии и некромантии.", customClass: "" }
        ];
        const necroArtifacts = [
            { name: "Фульгурит", icon: "", category: "Некромантический", tag: "электрический некроз", magicAbility: "Хранит голоса умерших во время грозы.", history: "Образовался на месте удара молнии в древнем некрополе.", customClass: "" },
            { name: "Ритуальный нож (Атламе)", icon: "", category: "Некромантический", tag: "жертвоприношение", magicAbility: "Разрезает грань между жизнью и смертью.", history: "Выкован на могильном пепле.", customClass: "" },
            { name: "Амулет-ожерелье из астрального нефрита", icon: "", category: "Некромантический", tag: "защита", magicAbility: "Защищает от магического истощения.", history: "Камни падают из параллельного измерения.", customClass: "" },
            { name: "Нереп нерождённого дитя", icon: "", category: "Некромантический", tag: "духовная связь", magicAbility: "Воскрешает невысказанные судьбы.", history: "Хранится в Склепах Эфемерной Гряды.", customClass: "" },
            { name: "Нож из нержавеющей стали", icon: "", category: "Некромантический", tag: "антипроклятие", magicAbility: "Отражает проклятия.", history: "Обработан в водах реки Леты.", customClass: "" }
        ];

        // ========= ФУНКЦИИ РЕНДЕРА =========
        function renderGrid(containerId, arr, type, onClickHandler) {
            const container = document.getElementById(containerId);
            if (!container) return;
            container.innerHTML = '';
            arr.forEach(item => {
                const card = document.createElement('div');
                let className = type === 'royal' ? 'royal-card' : (type === 'map' ? 'map-card' : 'artifact-card');
                if (type === 'artifact' && item.customClass) {
                    className += ' ' + item.customClass;
                }
                card.className = className;
                if (type === 'royal') {
                    card.innerHTML = `<div class="royal-icon">${item.icon}</div><div class="card-name">${item.name}</div><div class="card-role">${item.role}</div><span class="royal-tag">👑 династия</span>`;
                } else if (type === 'map') {
                    card.innerHTML = `<div class="map-icon">${item.icon}</div><div class="card-name">${item.name}</div><div class="card-desc">${item.description.substring(0, 80)}...</div><span class="map-tag">${item.tag}</span>`; 
                } else {
                    card.innerHTML = `<div class="artifact-icon"></div><div class="card-name">${item.name}</div><div class="card-desc">${item.magicAbility.substring(0, 70)}...</div><span class="artifact-tag">${item.tag}</span>`;
                }
                card.onclick = () => onClickHandler(item);
                container.appendChild(card);
            });
        }

        function renderHouses() {
            const container = document.getElementById('housesGrid');
            if (!container) return;
            container.innerHTML = '';
            housesData.forEach(house => {
                const card = document.createElement('div');
                card.className = 'house-card';
                card.innerHTML = `
                    <div class="house-icon">${house.icon}</div>
                    <div class="house-name">${house.name}</div>
                    <div class="house-motto">${house.motto}</div>
                    <div class="house-desc">${house.description.substring(0, 80)}...</div>
                `;
                card.onclick = () => openHouseModal(house);
                container.appendChild(card);
            });
        }

        function openMapModal(region) {
            document.getElementById('artifactModalName').innerText = region.name;
            document.getElementById('artifactModalSub').innerText = "Регион карты";
            document.getElementById('artifactModalIcon').innerText = region.icon;
            document.getElementById('artifactDossierFields').innerHTML = `<div class="dossier-item"><div class="dossier-label">🏷️ ТЕГ</div><div class="dossier-value">${region.tag}</div></div>`;
            document.getElementById('artifactMagicDetails').innerText = region.description;
            document.getElementById('artifactHistory').innerText = "Это место ждёт своего исследователя.";
            document.getElementById('artifactModal').classList.add('show');
            document.body.style.overflow = 'hidden';
        }

        function openHouseModal(house) {
            document.getElementById('houseModalName').innerText = house.name;
            document.getElementById('houseModalMotto').innerText = house.motto;
            document.getElementById('houseDossierFields').innerHTML = `<div class="dossier-item"><div class="dossier-label">🏷️ ДЕВИЗ</div><div class="dossier-value">${house.motto}</div></div>`;
            document.getElementById('houseDescription').innerText = house.description;
            document.getElementById('houseFact').innerText = house.fact;
            document.getElementById('houseModal').classList.add('show');
            document.body.style.overflow = 'hidden';
        }

        function openArtifactModal(artifact) {
            document.getElementById('artifactModalName').innerText = artifact.name;
            document.getElementById('artifactModalSub').innerText = artifact.category;
            const modalIcon = document.getElementById('artifactModalIcon');
            const modal = document.getElementById('artifactModal');
            if (artifact.name === "Карты Таро") {
                modalIcon.style.display = "none";
                modal.classList.add('tarot-modal');
            } else if (artifact.name === "Звёздные ключи") {
                modalIcon.style.display = "none";
                modal.classList.add('keys-modal');
            } else {
                modalIcon.style.display = "flex";
                modalIcon.innerText = "🏺";
                modal.classList.remove('tarot-modal', 'keys-modal');
            }
            document.getElementById('artifactDossierFields').innerHTML = `
                <div class="dossier-item"><div class="dossier-label">🏷️ ТЕГ</div><div class="dossier-value">${artifact.tag}</div></div>
                <div class="dossier-item"><div class="dossier-label">⚡ МАГИЧЕСКАЯ ШКОЛА</div><div class="dossier-value">${artifact.category.includes('Астрологический') ? 'Астральная магия' : 'Некромантия'}</div></div>
            `;
            document.getElementById('artifactMagicDetails').innerText = artifact.magicAbility;
            document.getElementById('artifactHistory').innerText = artifact.history;
            modal.classList.add('show');
            document.body.style.overflow = 'hidden';
        }

        function openRoyalModal(p) {
            document.getElementById('royalModalName').innerText = p.name;
            document.getElementById('royalModalRole').innerText = p.role;
            document.getElementById('royalDossierFields').innerHTML = `<div class="dossier-item"><div class="dossier-label">📖 ВОЗРАСТ</div><div class="dossier-value">${p.age}</div></div><div class="dossier-item"><div class="dossier-label">🏠 РЕЗИДЕНЦИЯ</div><div class="dossier-value">${p.residence}</div></div>`;
            document.getElementById('royalMagic').innerText = p.magic;
            document.getElementById('royalFact').innerText = p.fact;
            document.getElementById('royalModal').classList.add('show');
            document.body.style.overflow = 'hidden';
        }

        function closeModals() {
            document.querySelectorAll('.modal').forEach(m => m.classList.remove('show'));
            document.body.style.overflow = '';
        }
        document.querySelectorAll('.modal-close').forEach(btn => btn.addEventListener('click', closeModals));
        window.addEventListener('click', (e) => { if (e.target.classList.contains('modal')) closeModals(); });

        // Рендер персонажей
        const grid = document.getElementById('charactersGrid');
        charactersData.forEach(c => {
            const card = document.createElement('div'); card.className = 'character-card';
            card.innerHTML = `<div class="card-name">${c.name}</div><div class="card-role">${c.role}</div><div class="card-desc">${c.shortDesc}</div><span class="card-tag">${c.tag}</span>`;
            card.onclick = () => {
                document.getElementById('modalName').innerText = c.name;
                document.getElementById('modalSub').innerText = c.role;
                document.getElementById('dossierFields').innerHTML = `
                    <div class="dossier-item"><div class="dossier-label">📏 РОСТ</div><div class="dossier-value">${c.height}</div></div>
                    <div class="dossier-item"><div class="dossier-label">⚖️ ВЕС</div><div class="dossier-value">${c.weight}</div></div>
                    <div class="dossier-item"><div class="dossier-label">🎂 ВОЗРАСТ</div><div class="dossier-value">${c.age}</div></div>
                    <div class="dossier-item"><div class="dossier-label">🏠 РЕЗИДЕНЦИЯ</div><div class="dossier-value">${c.residence}</div></div>
                    <div class="dossier-item"><div class="dossier-label">📖 ОБЩАЯ ХАРАКТЕРИСТИКА</div><div class="dossier-value">${c.generalDesc || '—'}</div></div>
                    <div class="dossier-item"><div class="dossier-label">🏺 ОСНОВНЫЕ АРТЕФАКТЫ</div><div class="dossier-value">${c.artifacts || '—'}</div></div>
                `;
                document.getElementById('magicDetails').innerText = c.magicDesc;
                document.getElementById('dossierModal').classList.add('show');
                document.body.style.overflow = 'hidden';
            };
            grid.appendChild(card);
        });

        renderMapAccordion();
        renderGrid('firstGenGrid', firstGen, 'royal', openRoyalModal);
        renderGrid('newGenGrid', newGen, 'royal', openRoyalModal);
        renderGrid('heirsGrid', heirs, 'royal', openRoyalModal);
        renderGrid('astralArtifactsGrid', astralArtifacts, 'artifact', openArtifactModal);
        renderGrid('necroArtifactsGrid', necroArtifacts, 'artifact', openArtifactModal);
        renderHouses();

        // Переключение подкатегорий королевской крови
        function initRoyalSubnav() {
            const btns = document.querySelectorAll('.subnav-btn');
            const grids = {
                first: document.getElementById('firstGenGrid'),
                new: document.getElementById('newGenGrid'),
                heirs: document.getElementById('heirsGrid')
            };
            const texts = {
                first: "📜 <strong>Король-Астролог Артемий I</strong> объединил земли под знаком Солнца и Луны. Королева-Ведьма Мелисандра открыла врата между мирами. Их правление длилось 400 лет и оставило после себя Семь Ключей.",
                new: "📜 <strong>Вальдемар II</strong> и королева <strong>Ирма</strong> правят в эпоху равновесия. Их союз укрепил границы и возродил древние традиции.",
                heirs: "📜 <strong>Принцесса Амелия</strong> и принц <strong>Корнелиус</strong> — будущее династии. Они обучаются магии и управлению, чтобы принять трон."
            };
            btns.forEach(btn => {
                btn.addEventListener('click', () => {
                    btns.forEach(b => b.classList.remove('active'));
                    btn.classList.add('active');
                    const subcat = btn.getAttribute('data-subcat');
                    Object.keys(grids).forEach(key => {
                        grids[key].classList.remove('active-subcat');
                    });
                    grids[subcat].classList.add('active-subcat');
                    const historicalDiv = document.getElementById('royalHistoricalText');
                    if (historicalDiv) historicalDiv.innerHTML = texts[subcat];
                });
            });
        }

        // Переключение категорий (Королевская кровь / Придворные дома)
        function initRoyalNav() {
            const btnBlood = document.querySelector('[data-royal-cat="royal"]');
            const btnHouses = document.querySelector('[data-royal-cat="houses"]');
            const bloodCat = document.getElementById('royalBloodCategory');
            const housesCat = document.getElementById('housesCategory');
            if (btnBlood && btnHouses) {
                btnBlood.addEventListener('click', () => {
                    btnBlood.classList.add('active');
                    btnHouses.classList.remove('active');
                    bloodCat.classList.add('active-category');
                    housesCat.classList.remove('active-category');
                });
                btnHouses.addEventListener('click', () => {
                    btnHouses.classList.add('active');
                    btnBlood.classList.remove('active');
                    housesCat.classList.add('active-category');
                    bloodCat.classList.remove('active-category');
                });
            }
        }
        initRoyalNav();
        initRoyalSubnav();

        // Переключение категорий артефактов
        function initArtifactNav() {
            const btns = document.querySelectorAll('.art-nav-btn');
            const astralCat = document.getElementById('astralCategory');
            const necroCat = document.getElementById('necroCategory');
            btns.forEach(btn => {
                btn.addEventListener('click', () => {
                    btns.forEach(b => b.classList.remove('active'));
                    btn.classList.add('active');
                    const cat = btn.getAttribute('data-art-cat');
                    if (cat === 'astral') {
                        astralCat.classList.add('active-category');
                        necroCat.classList.remove('active-category');
                    } else {
                        necroCat.classList.add('active-category');
                        astralCat.classList.remove('active-category');
                    }
                });
            });
        }
        initArtifactNav();

        // ТЕМА
        const themeToggle = document.getElementById('themeToggle');
        const bodyEl = document.body;
        function setTheme(isDark) {
            if (isDark) { bodyEl.classList.remove('light-theme'); bodyEl.classList.add('dark-theme'); localStorage.setItem('theme', 'dark'); }
            else { bodyEl.classList.remove('dark-theme'); bodyEl.classList.add('light-theme'); localStorage.setItem('theme', 'light'); }
            themeToggle.checked = isDark;
        }
        const savedTheme = localStorage.getItem('theme');
        if (savedTheme === 'dark') setTheme(true);
        else setTheme(false);
        themeToggle.addEventListener('change', (e) => setTheme(e.target.checked));

        // НАВИГАЦИЯ ПО РАЗДЕЛАМ
        function scrollToSection(id) { document.getElementById(id)?.scrollIntoView({ behavior: 'smooth', block: 'start' }); }
        document.querySelectorAll('.nav-link').forEach(link => {
            const txt = link.innerText;
            link.addEventListener('click', () => {
                if (txt.includes('ДОСЬЕ')) scrollToSection('charactersGrid');
                else if (txt.includes('КАРТА')) scrollToSection('mapSection');
                else if (txt.includes('ДИНАСТИЯ')) scrollToSection('royalSection');
                else if (txt.includes('АРТЕФАКТЫ')) scrollToSection('artifactsSection');
            });
        });
    </script>
</body>
</html>
