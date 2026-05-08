# testgithubpages
this is a test GitHub pages site
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>KICK FASHION BOXER</title>
  <link rel="preconnect" href="https://fonts.googleapis.com"/>
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow+Condensed:wght@400;600;700&family=Barlow:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --orange: #FF5500;
      --orange-dim: #cc4400;
      --dark: #080808;
      --card-bg: #111111;
      --surface: #181818;
      --text: #f0ebe3;
      --muted: #888;
      --border: rgba(255,255,255,0.07);
    }

    *, *::before, *::after {
      margin: 0; padding: 0; box-sizing: border-box;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--dark);
      color: var(--text);
      font-family: 'Barlow', sans-serif;
      font-weight: 300;
      overflow-x: hidden;
      cursor: default;
    }

    /* ─── NOISE OVERLAY ─── */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='1'/%3E%3C/svg%3E");
      opacity: 0.025;
      pointer-events: none;
      z-index: 9999;
    }

    /* ─── HEADER ─── */
    header {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      padding: 0 40px;
      height: 70px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-bottom: 1px solid var(--border);
      background: rgba(8,8,8,0.85);
      backdrop-filter: blur(20px);
      -webkit-backdrop-filter: blur(20px);
      transition: background 0.3s;
    }

    .logo {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 24px;
      letter-spacing: 3px;
      color: var(--text);
    }
    .logo span { color: var(--orange); }

    nav { display: flex; align-items: center; gap: 8px; }
    nav a {
      color: var(--muted);
      text-decoration: none;
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 600;
      font-size: 13px;
      letter-spacing: 2px;
      text-transform: uppercase;
      padding: 6px 14px;
      border-radius: 4px;
      transition: color 0.2s, background 0.2s;
    }
    nav a:hover { color: var(--text); background: rgba(255,255,255,0.05); }

    .nav-cta {
      background: var(--orange) !important;
      color: white !important;
      padding: 8px 18px !important;
      border-radius: 6px !important;
    }
    .nav-cta:hover { background: var(--orange-dim) !important; }

    .hamburger {
      display: none;
      flex-direction: column;
      gap: 5px;
      cursor: pointer;
      padding: 4px;
    }
    .hamburger span {
      display: block;
      width: 24px;
      height: 2px;
      background: var(--text);
      border-radius: 2px;
      transition: 0.3s;
    }

    /* ─── MOBILE MENU ─── */
    .mobile-menu {
      display: none;
      position: fixed;
      inset: 0;
      background: var(--dark);
      z-index: 99;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 28px;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.3s;
    }
    .mobile-menu.open { opacity: 1; pointer-events: all; }
    .mobile-menu a {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 48px;
      letter-spacing: 4px;
      color: var(--text);
      text-decoration: none;
      transition: color 0.2s;
    }
    .mobile-menu a:hover { color: var(--orange); }

    /* ─── HERO ─── */
    .hero {
      height: 100vh;
      min-height: 600px;
      position: relative;
      display: grid;
      place-items: center;
      overflow: hidden;
    }

    .hero-bg {
      position: absolute;
      inset: 0;
      background: url('Messi-fan-art-oversized-tshirt-black-india-back_large.webp') center/cover no-repeat;
      transform: scale(1.05);
      transition: transform 12s ease-out;
    }
    .hero-bg.loaded { transform: scale(1); }

    .hero-overlay {
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(8,8,8,0.92) 40%, rgba(8,8,8,0.5) 100%);
    }

    .hero-content {
      position: relative;
      z-index: 2;
      max-width: 1200px;
      width: 100%;
      padding: 0 40px;
      display: grid;
      grid-template-columns: 1fr 1fr;
      align-items: center;
      gap: 60px;
    }

    .hero-text {}

    .hero-label {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 12px;
      letter-spacing: 4px;
      text-transform: uppercase;
      color: var(--orange);
      margin-bottom: 24px;
    }
    .hero-label::before {
      content: '';
      display: block;
      width: 30px;
      height: 1px;
      background: var(--orange);
    }

    .hero h1 {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(72px, 10vw, 140px);
      line-height: 0.9;
      letter-spacing: 2px;
      margin-bottom: 28px;
    }
    .hero h1 .line2 { color: var(--orange); }

    .hero-desc {
      font-size: 16px;
      line-height: 1.7;
      color: rgba(240,235,227,0.6);
      max-width: 380px;
      margin-bottom: 40px;
    }

    .hero-actions { display: flex; gap: 16px; flex-wrap: wrap; }

    .btn-primary {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: var(--orange);
      color: white;
      padding: 16px 32px;
      border: none;
      border-radius: 8px;
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700;
      font-size: 14px;
      letter-spacing: 2px;
      text-transform: uppercase;
      cursor: pointer;
      transition: background 0.2s, transform 0.15s;
      text-decoration: none;
    }
    .btn-primary:hover { background: var(--orange-dim); transform: translateY(-2px); }

    .btn-ghost {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: transparent;
      color: var(--text);
      padding: 15px 32px;
      border: 1px solid rgba(255,255,255,0.2);
      border-radius: 8px;
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700;
      font-size: 14px;
      letter-spacing: 2px;
      text-transform: uppercase;
      cursor: pointer;
      transition: border-color 0.2s, background 0.2s, transform 0.15s;
      text-decoration: none;
    }
    .btn-ghost:hover { border-color: rgba(255,255,255,0.5); background: rgba(255,255,255,0.05); transform: translateY(-2px); }

    .hero-stats {
      display: flex;
      flex-direction: column;
      gap: 24px;
      justify-content: center;
    }

    .stat-card {
      background: rgba(255,255,255,0.04);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 24px 28px;
      backdrop-filter: blur(10px);
      transition: background 0.2s, transform 0.2s;
    }
    .stat-card:hover { background: rgba(255,255,255,0.07); transform: translateX(6px); }

    .stat-number {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 52px;
      letter-spacing: 2px;
      color: var(--orange);
      line-height: 1;
    }
    .stat-label {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 13px;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--muted);
      margin-top: 4px;
    }

    .scroll-hint {
      position: absolute;
      bottom: 36px;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 8px;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 11px;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--muted);
      animation: float 2s ease-in-out infinite;
    }
    .scroll-hint::after {
      content: '';
      display: block;
      width: 1px;
      height: 40px;
      background: linear-gradient(to bottom, var(--muted), transparent);
    }
    @keyframes float { 0%,100%{transform:translateX(-50%) translateY(0)} 50%{transform:translateX(-50%) translateY(6px)} }

    /* ─── MARQUEE ─── */
    .marquee-section {
      overflow: hidden;
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
      padding: 18px 0;
      background: var(--surface);
    }
    .marquee-track {
      display: flex;
      gap: 0;
      width: max-content;
      animation: marquee 20s linear infinite;
    }
    .marquee-item {
      display: flex;
      align-items: center;
      gap: 20px;
      padding: 0 40px;
      font-family: 'Bebas Neue', sans-serif;
      font-size: 20px;
      letter-spacing: 3px;
      color: var(--muted);
      white-space: nowrap;
    }
    .marquee-item .dot {
      width: 6px; height: 6px;
      border-radius: 50%;
      background: var(--orange);
      flex-shrink: 0;
    }
    @keyframes marquee { from{transform:translateX(0)} to{transform:translateX(-50%)} }

    /* ─── SECTIONS ─── */
    .section {
      padding: 100px 40px;
      max-width: 1280px;
      margin: 0 auto;
    }

    .section-header {
      display: flex;
      align-items: flex-end;
      justify-content: space-between;
      margin-bottom: 60px;
      gap: 24px;
      flex-wrap: wrap;
    }

    .section-eyebrow {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 12px;
      letter-spacing: 4px;
      text-transform: uppercase;
      color: var(--orange);
      margin-bottom: 12px;
    }

    .section-title {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(48px, 6vw, 80px);
      letter-spacing: 2px;
      line-height: 0.95;
    }

    .section-link {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 13px;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--orange);
      text-decoration: none;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      transition: gap 0.2s;
      flex-shrink: 0;
    }
    .section-link:hover { gap: 14px; }
    .section-link::after { content: '→'; }

    /* ─── PRODUCT GRID ─── */
    .product-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 24px;
    }

    .product-card {
      background: var(--card-bg);
      border-radius: 16px;
      overflow: hidden;
      border: 1px solid var(--border);
      transition: transform 0.3s, border-color 0.3s;
      position: relative;
      group: true;
    }
    .product-card:hover {
      transform: translateY(-8px);
      border-color: rgba(255,85,0,0.3);
    }

    .card-img-wrap {
      position: relative;
      overflow: hidden;
      height: 340px;
    }
    .card-img-wrap img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.5s ease;
    }
    .product-card:hover .card-img-wrap img { transform: scale(1.06); }

    .card-badge {
      position: absolute;
      top: 16px;
      left: 16px;
      background: var(--orange);
      color: white;
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700;
      font-size: 11px;
      letter-spacing: 2px;
      text-transform: uppercase;
      padding: 5px 12px;
      border-radius: 4px;
    }

    .card-quick-add {
      position: absolute;
      bottom: 16px;
      left: 50%;
      transform: translateX(-50%) translateY(20px);
      opacity: 0;
      width: calc(100% - 32px);
      background: rgba(8,8,8,0.92);
      border: 1px solid rgba(255,85,0,0.5);
      color: var(--orange);
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700;
      font-size: 13px;
      letter-spacing: 2px;
      text-transform: uppercase;
      padding: 12px;
      border-radius: 8px;
      cursor: pointer;
      transition: opacity 0.3s, transform 0.3s, background 0.2s;
      backdrop-filter: blur(10px);
    }
    .product-card:hover .card-quick-add { opacity: 1; transform: translateX(-50%) translateY(0); }
    .card-quick-add:hover { background: var(--orange); color: white; }

    .card-body {
      padding: 22px;
    }

    .card-category {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 11px;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--muted);
      margin-bottom: 8px;
    }

    .card-name {
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 600;
      font-size: 20px;
      letter-spacing: 0.5px;
      margin-bottom: 14px;
      line-height: 1.2;
    }

    .card-footer {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .card-price {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 28px;
      letter-spacing: 1px;
      color: var(--orange);
    }

    .card-sizes {
      display: flex;
      gap: 6px;
    }
    .size-dot {
      width: 28px; height: 28px;
      border-radius: 50%;
      border: 1px solid var(--border);
      display: grid;
      place-items: center;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 10px;
      letter-spacing: 0.5px;
      color: var(--muted);
      cursor: pointer;
      transition: border-color 0.2s, color 0.2s;
    }
    .size-dot:hover { border-color: var(--orange); color: var(--orange); }

    /* ─── FEATURED BANNER ─── */
    .featured-banner {
      margin: 0 40px 100px;
      border-radius: 24px;
      overflow: hidden;
      position: relative;
      height: 500px;
      display: flex;
      align-items: center;
    }
    .featured-bg {
      position: absolute;
      inset: 0;
      background: url('FootballGuy-Navy1.webp') center top/cover;
    }
    .featured-overlay {
      position: absolute;
      inset: 0;
      background: linear-gradient(90deg, rgba(8,8,8,0.95) 40%, rgba(8,8,8,0.2));
    }
    .featured-content {
      position: relative;
      z-index: 2;
      padding: 60px;
      max-width: 520px;
    }
    .featured-tag {
      display: inline-block;
      background: var(--orange);
      color: white;
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700;
      font-size: 11px;
      letter-spacing: 3px;
      text-transform: uppercase;
      padding: 6px 14px;
      border-radius: 4px;
      margin-bottom: 20px;
    }
    .featured-title {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(52px, 6vw, 80px);
      line-height: 0.95;
      letter-spacing: 2px;
      margin-bottom: 16px;
    }
    .featured-desc {
      font-size: 16px;
      color: rgba(240,235,227,0.6);
      line-height: 1.7;
      margin-bottom: 32px;
    }

    /* ─── CATEGORIES STRIP ─── */
    .categories {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 16px;
      margin-bottom: 100px;
      padding: 0 40px;
    }

    .cat-card {
      border-radius: 14px;
      overflow: hidden;
      position: relative;
      height: 220px;
      cursor: pointer;
    }
    .cat-card img {
      width: 100%; height: 100%;
      object-fit: cover;
      transition: transform 0.5s;
    }
    .cat-card:hover img { transform: scale(1.08); }
    .cat-card-overlay {
      position: absolute;
      inset: 0;
      background: linear-gradient(to top, rgba(8,8,8,0.85) 0%, rgba(8,8,8,0.1) 60%);
      display: flex;
      align-items: flex-end;
      padding: 20px;
      transition: background 0.3s;
    }
    .cat-card:hover .cat-card-overlay { background: linear-gradient(to top, rgba(255,85,0,0.6) 0%, rgba(8,8,8,0.1) 60%); }
    .cat-name {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 26px;
      letter-spacing: 2px;
    }

    /* ─── FOOTER ─── */
    footer {
      background: #050505;
      border-top: 1px solid var(--border);
      padding: 60px 40px 40px;
    }
    .footer-top {
      display: grid;
      grid-template-columns: 2fr 1fr 1fr 1fr;
      gap: 60px;
      margin-bottom: 60px;
    }
    .footer-brand .logo { font-size: 28px; display: block; margin-bottom: 16px; }
    .footer-desc {
      font-size: 14px;
      color: var(--muted);
      line-height: 1.8;
      max-width: 260px;
      margin-bottom: 24px;
    }
    .footer-social { display: flex; gap: 10px; }
    .social-btn {
      width: 36px; height: 36px;
      border-radius: 8px;
      border: 1px solid var(--border);
      display: grid;
      place-items: center;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 12px;
      font-weight: 700;
      letter-spacing: 0.5px;
      color: var(--muted);
      cursor: pointer;
      transition: border-color 0.2s, color 0.2s, background 0.2s;
      text-decoration: none;
    }
    .social-btn:hover { border-color: var(--orange); color: var(--orange); background: rgba(255,85,0,0.08); }

    .footer-col h4 {
      font-family: 'Barlow Condensed', sans-serif;
      font-weight: 700;
      font-size: 13px;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--text);
      margin-bottom: 20px;
    }
    .footer-col ul { list-style: none; display: flex; flex-direction: column; gap: 10px; }
    .footer-col ul li a {
      font-size: 14px;
      color: var(--muted);
      text-decoration: none;
      transition: color 0.2s;
    }
    .footer-col ul li a:hover { color: var(--orange); }

    .footer-bottom {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding-top: 32px;
      border-top: 1px solid var(--border);
      flex-wrap: wrap;
      gap: 16px;
    }
    .footer-copy {
      font-size: 13px;
      color: var(--muted);
    }
    .footer-links { display: flex; gap: 20px; }
    .footer-links a {
      font-size: 13px;
      color: var(--muted);
      text-decoration: none;
      transition: color 0.2s;
    }
    .footer-links a:hover { color: var(--text); }

    /* ─── CART TOAST ─── */
    .toast {
      position: fixed;
      bottom: 30px; right: 30px;
      background: var(--surface);
      border: 1px solid rgba(255,85,0,0.4);
      border-radius: 12px;
      padding: 16px 22px;
      display: flex;
      align-items: center;
      gap: 14px;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 15px;
      letter-spacing: 1px;
      transform: translateY(80px);
      opacity: 0;
      transition: transform 0.4s cubic-bezier(0.34,1.56,0.64,1), opacity 0.3s;
      z-index: 999;
    }
    .toast.show { transform: translateY(0); opacity: 1; }
    .toast-icon {
      width: 32px; height: 32px;
      background: rgba(255,85,0,0.15);
      border-radius: 8px;
      display: grid;
      place-items: center;
      color: var(--orange);
      font-size: 16px;
    }

    /* ─── ANIMATIONS ─── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .anim { opacity: 0; animation: fadeUp 0.7s forwards; }
    .anim-d1 { animation-delay: 0.1s; }
    .anim-d2 { animation-delay: 0.25s; }
    .anim-d3 { animation-delay: 0.4s; }
    .anim-d4 { animation-delay: 0.55s; }

    /* ─── RESPONSIVE ─── */
    @media (max-width: 1024px) {
      .hero-content { grid-template-columns: 1fr; }
      .hero-stats { flex-direction: row; flex-wrap: wrap; }
      .stat-card { flex: 1; min-width: 150px; }
      .product-grid { grid-template-columns: repeat(2, 1fr); }
      .footer-top { grid-template-columns: 1fr 1fr; gap: 40px; }
      .categories { grid-template-columns: repeat(2, 1fr); }
    }

    @media (max-width: 768px) {
      header { padding: 0 20px; }
      nav { display: none; }
      .hamburger { display: flex; }
      .mobile-menu { display: flex; }

      .hero-content { padding: 0 20px; }
      .hero h1 { font-size: 64px; }

      .section { padding: 70px 20px; }
      .section-header { flex-direction: column; align-items: flex-start; }

      .product-grid { grid-template-columns: 1fr; }

      .featured-banner { margin: 0 20px 70px; height: auto; }
      .featured-content { padding: 40px 30px; }

      .categories { padding: 0 20px; grid-template-columns: 1fr 1fr; }

      .footer-top { grid-template-columns: 1fr; gap: 40px; }
      footer { padding: 50px 20px 32px; }
      .footer-bottom { flex-direction: column; text-align: center; }
    }
  </style>
</head>

<body>

<!-- Mobile menu -->
<div class="mobile-menu" id="mobileMenu">
  <a href="#" onclick="toggleMenu()">Home</a>
  <a href="#" onclick="toggleMenu()">Shop</a>
  <a href="#" onclick="toggleMenu()">New Arrivals</a>
  <a href="#" onclick="toggleMenu()">T-Shirts</a>
  <a href="#" onclick="toggleMenu()">Hoodies</a>
  <a href="#" onclick="toggleMenu()">Contact</a>
</div>

<!-- Header -->
<header>
  <div class="logo">KICK <span>FASHION</span> BOXER</div>
  <nav>
    <a href="#">Home</a>
    <a href="#">Shop</a>
    <a href="#">New Arrivals</a>
    <a href="#">T-Shirts</a>
    <a href="#">Hoodies</a>
    <a href="#" class="nav-cta">Shop Now</a>
  </nav>
  <div class="hamburger" onclick="toggleMenu()" aria-label="Toggle menu">
    <span></span><span></span><span></span>
  </div>
</header>

<!-- Hero -->
<section class="hero">
  <div class="hero-bg" id="heroBg"></div>
  <div class="hero-overlay"></div>

  <div class="hero-content">
    <div class="hero-text">
      <div class="hero-label anim anim-d1">New Collection 2026</div>
      <h1 class="anim anim-d2">
        Play Hard<br>
        <span class="line2">Dress Harder</span>
      </h1>
      <p class="hero-desc anim anim-d3">
        Streetwear born from the game. Every drop built for those who move fast, look sharp, and never settle.
      </p>
      <div class="hero-actions anim anim-d4">
        <a href="#" class="btn-primary">Shop the Drop →</a>
        <a href="#" class="btn-ghost">New Arrivals</a>
      </div>
    </div>

    <div class="hero-stats">
      <div class="stat-card anim anim-d2">
        <div class="stat-number">200+</div>
        <div class="stat-label">Styles Available</div>
      </div>
      <div class="stat-card anim anim-d3">
        <div class="stat-number">50K</div>
        <div class="stat-label">Happy Customers</div>
      </div>
      <div class="stat-card anim anim-d4">
        <div class="stat-number">100%</div>
        <div class="stat-label">Street Approved</div>
      </div>
    </div>
  </div>

  <div class="scroll-hint">Scroll</div>
</section>

<!-- Marquee -->
<div class="marquee-section">
  <div class="marquee-track">
    <div class="marquee-item"><span class="dot"></span> New Arrivals</div>
    <div class="marquee-item"><span class="dot"></span> Free Shipping Above ₹999</div>
    <div class="marquee-item"><span class="dot"></span> Oversized Tees</div>
    <div class="marquee-item"><span class="dot"></span> Limited Edition Drops</div>
    <div class="marquee-item"><span class="dot"></span> Streetwear Culture</div>
    <div class="marquee-item"><span class="dot"></span> Game-Inspired Fashion</div>
    <div class="marquee-item"><span class="dot"></span> New Arrivals</div>
    <div class="marquee-item"><span class="dot"></span> Free Shipping Above ₹999</div>
    <div class="marquee-item"><span class="dot"></span> Oversized Tees</div>
    <div class="marquee-item"><span class="dot"></span> Limited Edition Drops</div>
    <div class="marquee-item"><span class="dot"></span> Streetwear Culture</div>
    <div class="marquee-item"><span class="dot"></span> Game-Inspired Fashion</div>
  </div>
</div>

<!-- Products -->
<div class="section">
  <div class="section-header">
    <div>
      <div class="section-eyebrow">What's Hot</div>
      <h2 class="section-title">Trending<br>Collection</h2>
    </div>
    <a href="#" class="section-link">View All Products</a>
  </div>

  <div class="product-grid">

    <div class="product-card">
      <div class="card-img-wrap">
        <img src="FootballGuy-Navy1.webp" alt="Football Guy Oversized Tee" loading="lazy"/>
        <div class="card-badge">Bestseller</div>
        <button class="card-quick-add" onclick="addToCart('Football Guy Oversized Tee')">Quick Add</button>
      </div>
      <div class="card-body">
        <div class="card-category">Oversized Tee</div>
        <div class="card-name">Football Guy Oversized Tee</div>
        <div class="card-footer">
          <div class="card-price">₹899</div>
          <div class="card-sizes">
            <div class="size-dot">S</div>
            <div class="size-dot">M</div>
            <div class="size-dot">L</div>
            <div class="size-dot">XL</div>
          </div>
        </div>
      </div>
    </div>

    <div class="product-card">
      <div class="card-img-wrap">
        <img src="images-4.jpg" alt="Broncos Football Tee" loading="lazy"/>
        <div class="card-badge">New Drop</div>
        <button class="card-quick-add" onclick="addToCart('Broncos Football Tee')">Quick Add</button>
      </div>
      <div class="card-body">
        <div class="card-category">Graphic Tee</div>
        <div class="card-name">Broncos Football Tee</div>
        <div class="card-footer">
          <div class="card-price">₹799</div>
          <div class="card-sizes">
            <div class="size-dot">S</div>
            <div class="size-dot">M</div>
            <div class="size-dot">L</div>
            <div class="size-dot">XL</div>
          </div>
        </div>
      </div>
    </div>

    <div class="product-card">
      <div class="card-img-wrap">
        <img src="images-1.jpg" alt="RJL 1973 Long Sleeve" loading="lazy"/>
        <button class="card-quick-add" onclick="addToCart('RJL 1973 Long Sleeve')">Quick Add</button>
      </div>
      <div class="card-body">
        <div class="card-category">Long Sleeve</div>
        <div class="card-name">RJL 1973 Long Sleeve</div>
        <div class="card-footer">
          <div class="card-price">₹1099</div>
          <div class="card-sizes">
            <div class="size-dot">S</div>
            <div class="size-dot">M</div>
            <div class="size-dot">L</div>
            <div class="size-dot">XL</div>
          </div>
        </div>
      </div>
    </div>

    <div class="product-card">
      <div class="card-img-wrap">
        <img src="Messi-fan-art-oversized-tshirt-black-india-back_large.webp" alt="Messi 10 Oversized Tee" loading="lazy"/>
        <div class="card-badge">Fan Fav</div>
        <button class="card-quick-add" onclick="addToCart('Messi 10 Oversized Tee')">Quick Add</button>
      </div>
      <div class="card-body">
        <div class="card-category">Oversized Tee</div>
        <div class="card-name">Messi 10 Oversized Tee</div>
        <div class="card-footer">
          <div class="card-price">₹999</div>
          <div class="card-sizes">
            <div class="size-dot">S</div>
            <div class="size-dot">M</div>
            <div class="size-dot">L</div>
            <div class="size-dot">XL</div>
          </div>
        </div>
      </div>
    </div>

    <div class="product-card">
      <div class="card-img-wrap">
        <img src="download-1.jpg" alt="Super Puma Graphic Tee" loading="lazy"/>
        <div class="card-badge">Limited</div>
        <button class="card-quick-add" onclick="addToCart('Super Puma Graphic Tee')">Quick Add</button>
      </div>
      <div class="card-body">
        <div class="card-category">Graphic Tee</div>
        <div class="card-name">Super Puma Graphic Tee</div>
        <div class="card-footer">
          <div class="card-price">₹949</div>
          <div class="card-sizes">
            <div class="size-dot">S</div>
            <div class="size-dot">M</div>
            <div class="size-dot">L</div>
            <div class="size-dot">XL</div>
          </div>
        </div>
      </div>
    </div>

    <div class="product-card">
      <div class="card-img-wrap">
        <img src="download-2.jpg" alt="Soccer Snapback Cap" loading="lazy"/>
        <div class="card-badge">New</div>
        <button class="card-quick-add" onclick="addToCart('Soccer Snapback Cap')">Quick Add</button>
      </div>
      <div class="card-body">
        <div class="card-category">Headwear</div>
        <div class="card-name">Soccer Snapback Cap</div>
        <div class="card-footer">
          <div class="card-price">₹549</div>
          <div class="card-sizes">
            <div class="size-dot">S</div>
            <div class="size-dot">M</div>
            <div class="size-dot">L</div>
          </div>
        </div>
      </div>
    </div>

  </div>
</div>

<!-- Featured Banner -->
<div class="featured-banner">
  <div class="featured-bg"></div>
  <div class="featured-overlay"></div>
  <div class="featured-content">
    <span class="featured-tag">Limited Drop</span>
    <h2 class="featured-title">Hoodie<br>Season<br>Is Here</h2>
    <p class="featured-desc">Heavy-weight fleece. Dropped shoulders. Built for the block and the court.</p>
    <a href="#" class="btn-primary">Shop Hoodies →</a>
  </div>
</div>

<!-- Categories -->
<div class="categories">
  <div class="cat-card">
    <img src="FootballGuy-Navy1.webp" alt="T-Shirts" loading="lazy"/>
    <div class="cat-card-overlay"><div class="cat-name">T-Shirts</div></div>
  </div>
  <div class="cat-card">
    <img src="images-3.jpg" alt="Hoodies" loading="lazy"/>
    <div class="cat-card-overlay"><div class="cat-name">Hoodies</div></div>
  </div>
  <div class="cat-card">
    <img src="download.jpg" alt="Long Sleeves" loading="lazy"/>
    <div class="cat-card-overlay"><div class="cat-name">Long Sleeves</div></div>
  </div>
  <div class="cat-card">
    <img src="download-2.jpg" alt="Accessories" loading="lazy"/>
    <div class="cat-card-overlay"><div class="cat-name">Accessories</div></div>
  </div>
</div>

<!-- Footer -->
<footer>
  <div class="footer-top">
    <div class="footer-brand">
      <span class="logo">KICK <span>FASHION</span> BOXER</span>
      <p class="footer-desc">
        Streetwear inspired by the game. Made for everyday champions who move with purpose and dress with intention.
      </p>
      <div class="footer-social">
        <a href="#" class="social-btn">IG</a>
        <a href="#" class="social-btn">TW</a>
        <a href="#" class="social-btn">YT</a>
        <a href="#" class="social-btn">WA</a>
      </div>
    </div>

    <div class="footer-col">
      <h4>Shop</h4>
      <ul>
        <li><a href="#">New Arrivals</a></li>
        <li><a href="#">T-Shirts</a></li>
        <li><a href="#">Hoodies</a></li>
        <li><a href="#">Bottoms</a></li>
        <li><a href="#">Accessories</a></li>
      </ul>
    </div>

    <div class="footer-col">
      <h4>Help</h4>
      <ul>
        <li><a href="#">Size Guide</a></li>
        <li><a href="#">Shipping Info</a></li>
        <li><a href="#">Returns</a></li>
        <li><a href="#">Track Order</a></li>
        <li><a href="#">FAQ</a></li>
      </ul>
    </div>

    <div class="footer-col">
      <h4>Contact</h4>
      <ul>
        <li><a href="tel:9211974232">+91 92119 74232</a></li>
        <li><a href="mailto:stephenoah2005@gmail.com">stephenoah2005@gmail.com</a></li>
        <li><a href="#">Instagram DM</a></li>
      </ul>
    </div>
  </div>

  <div class="footer-bottom">
    <div class="footer-copy">© 2026 Kick Fashion Boxer. All rights reserved.</div>
    <div class="footer-links">
      <a href="#">Privacy Policy</a>
      <a href="#">Terms of Use</a>
      <a href="#">Cookies</a>
    </div>
  </div>
</footer>

<!-- Toast -->
<div class="toast" id="toast">
  <div class="toast-icon">✓</div>
  <span id="toastMsg">Added to cart</span>
</div>

<script>
  // Hero ready
  document.getElementById('heroBg').classList.add('loaded');

  // Mobile menu
  function toggleMenu() {
    const menu = document.getElementById('mobileMenu');
    menu.classList.toggle('open');
  }

  // Toast
  let toastTimer;
  function addToCart(name) {
    const toast = document.getElementById('toast');
    const msg = document.getElementById('toastMsg');
    msg.textContent = name + ' added to cart';
    toast.classList.add('show');
    clearTimeout(toastTimer);
    toastTimer = setTimeout(() => toast.classList.remove('show'), 3000);
  }

  // Header scroll effect
  const header = document.querySelector('header');
  window.addEventListener('scroll', () => {
    if (window.scrollY > 60) {
      header.style.background = 'rgba(8,8,8,0.97)';
    } else {
      header.style.background = 'rgba(8,8,8,0.85)';
    }
  });

  // Intersection observer for cards
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.opacity = '1';
        e.target.style.transform = 'translateY(0)';
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.product-card, .cat-card, .stat-card').forEach((el, i) => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(24px)';
    el.style.transition = `opacity 0.6s ease ${i * 0.08}s, transform 0.6s ease ${i * 0.08}s, border-color 0.3s`;
    observer.observe(el);
  });
</script>

</body>
</html>
