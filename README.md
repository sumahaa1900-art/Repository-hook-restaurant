<!doctype html>
<html lang="en">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Hook Fish and Chicken - The best fresh seafood and chicken restaurant in Detroit">
  <title>Hook Fish and Chicken - Fresh Seafood &amp; Chicken</title>
  <script src="/_sdk/element_sdk.js"></script>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
      height: 100%;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 100%);
      color: #ffffff;
      min-height: 100%;
      overflow-x: hidden;
      box-sizing: border-box;
    }

    /* Navigation */
    nav {
      position: fixed;
      top: 0;
      width: 100%;
      background: rgba(10, 14, 39, 0.98);
      backdrop-filter: blur(15px);
      z-index: 1000;
      box-shadow: 0 4px 30px rgba(255, 107, 107, 0.3);
      border-bottom: 2px solid #ff6b6b;
    }

    .nav-container {
      max-width: 1400px;
      margin: 0 auto;
      padding: 20px 40px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-size: 28px;
      font-weight: 900;
      background: linear-gradient(135deg, #ff6b6b 0%, #ffd93d 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      text-transform: uppercase;
      letter-spacing: 3px;
    }

    .nav-links {
      display: flex;
      gap: 20px;
      list-style: none;
      align-items: center;
    }

    .nav-links a {
      color: #ffffff;
      text-decoration: none;
      font-weight: 600;
      padding: 12px 25px;
      border-radius: 30px;
      transition: all 0.4s;
      font-size: 16px;
      position: relative;
      overflow: hidden;
    }

    .nav-links a::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, #ff6b6b, #ffd93d);
      transition: left 0.4s;
      z-index: -1;
      border-radius: 30px;
    }

    .nav-links a:hover::before {
      left: 0;
    }

    .nav-links a:hover {
      transform: translateY(-3px);
      box-shadow: 0 10px 25px rgba(255, 107, 107, 0.4);
    }

    /* Hero Section */
    .hero {
      margin-top: 80px;
      min-height: 600px;
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
      background: linear-gradient(135deg, rgba(10, 14, 39, 0.95) 0%, rgba(26, 31, 58, 0.95) 100%),
                  url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><rect fill="%23ff6b6b" opacity="0.1" width="1200" height="600"/><circle cx="200" cy="100" r="80" fill="%23ffd93d" opacity="0.15"/><circle cx="1000" cy="400" r="100" fill="%23ff6b6b" opacity="0.1"/><circle cx="600" cy="300" r="60" fill="%23ffd93d" opacity="0.12"/></svg>');
      background-size: cover;
      background-position: center;
      padding: 100px 40px;
      overflow: hidden;
    }

    .hero::before {
      content: '';
      position: absolute;
      top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: radial-gradient(circle, rgba(255, 107, 107, 0.15) 0%, transparent 70%);
      animation: heroGlow 8s ease-in-out infinite;
    }

    @keyframes heroGlow {
      0%, 100% { transform: translate(0, 0) scale(1); }
      50% { transform: translate(30px, 30px) scale(1.1); }
    }

    .hero-content {
      text-align: center;
      z-index: 1;
      max-width: 1000px;
      animation: fadeInUp 1s ease;
    }

    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(40px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .hero-title {
      font-size: 72px;
      font-weight: 900;
      margin: 0 0 30px 0;
      background: linear-gradient(135deg, #ff6b6b 0%, #ffd93d 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      letter-spacing: 4px;
      text-transform: uppercase;
      line-height: 1.2;
    }

    .hero-subtitle {
      font-size: 32px;
      color: #e0e0e0;
      margin: 30px 0 60px 0;
      font-weight: 400;
      letter-spacing: 2px;
    }

    .cta-buttons {
      display: flex;
      gap: 20px;
      justify-content: center;
      flex-wrap: wrap;
    }

    .cta-button {
      padding: 20px 50px;
      font-size: 22px;
      font-weight: 700;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      background: linear-gradient(135deg, #ff6b6b 0%, #ff8787 100%);
      color: white;
      text-decoration: none;
      display: inline-flex;
      align-items: center;
      gap: 12px;
      box-shadow: 0 10px 35px rgba(255, 107, 107, 0.4);
      transition: all 0.4s;
    }

    .cta-button:hover {
      transform: translateY(-5px) scale(1.05);
      box-shadow: 0 15px 45px rgba(255, 107, 107, 0.6);
    }

    .cta-button.secondary {
      background: linear-gradient(135deg, #ffd93d 0%, #ffed4e 100%);
      color: #0a0e27;
    }

    /* Contact Bar */
    .contact-bar {
      background: linear-gradient(135deg, #ff6b6b 0%, #ffd93d 100%);
      padding: 25px 40px;
      box-shadow: 0 5px 25px rgba(0, 0, 0, 0.3);
    }

    .contact-info {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 60px;
      flex-wrap: wrap;
      max-width: 1400px;
      margin: 0 auto;
    }

    .contact-item {
      display: flex;
      align-items: center;
      gap: 12px;
      font-size: 18px;
      font-weight: 700;
      color: white;
      cursor: pointer;
      transition: transform 0.3s;
    }

    .contact-item:hover {
      transform: scale(1.05);
    }

    .contact-icon {
      font-size: 26px;
    }

    /* About Section */
    .about-section {
      padding: 100px 40px;
      max-width: 1400px;
      margin: 0 auto;
    }

    .about-content {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 60px;
      align-items: center;
    }

    .about-text h2 {
      font-size: 56px;
      font-weight: 800;
      margin: 0 0 30px 0;
      background: linear-gradient(135deg, #ff6b6b 0%, #ffd93d 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      text-transform: uppercase;
      letter-spacing: 3px;
    }

    .about-text p {
      font-size: 20px;
      line-height: 1.8;
      color: #e0e0e0;
      margin-bottom: 20px;
    }

    .about-image {
      position: relative;
      border-radius: 30px;
      overflow: hidden;
      box-shadow: 0 20px 60px rgba(255, 107, 107, 0.3);
      height: 400px;
      background: linear-gradient(135deg, rgba(255, 107, 107, 0.2), rgba(255, 217, 61, 0.2));
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .about-image svg {
      width: 80%;
      height: 80%;
      filter: drop-shadow(0 10px 30px rgba(255, 107, 107, 0.4));
    }

    /* Features Grid */
    .features-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 30px;
      margin-top: 60px;
    }

    .feature-card {
      background: rgba(26, 31, 58, 0.5);
      padding: 40px;
      border-radius: 20px;
      text-align: center;
      transition: all 0.4s;
      border: 2px solid rgba(255, 107, 107, 0.2);
    }

    .feature-card:hover {
      transform: translateY(-10px);
      border-color: #ff6b6b;
      box-shadow: 0 20px 50px rgba(255, 107, 107, 0.3);
      background: rgba(26, 31, 58, 0.8);
    }

    .feature-icon {
      font-size: 60px;
      margin-bottom: 20px;
      display: block;
    }

    .feature-title {
      font-size: 24px;
      font-weight: 700;
      color: #ffffff;
      margin-bottom: 15px;
    }

    .feature-text {
      font-size: 16px;
      color: #b0b0b0;
      line-height: 1.6;
    }

    /* Menu Categories */
    .menu-categories {
      padding: 80px 40px;
      max-width: 1400px;
      margin: 0 auto;
    }

    .section-title {
      text-align: center;
      font-size: 56px;
      font-weight: 800;
      margin: 0 0 20px 0;
      background: linear-gradient(135deg, #ff6b6b 0%, #ffd93d 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      text-transform: uppercase;
      letter-spacing: 3px;
    }

    .section-subtitle {
      text-align: center;
      font-size: 20px;
      color: #b0b0b0;
      margin: 0 0 60px 0;
    }

    .categories-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 30px;
    }

    .category-card {
      background: linear-gradient(145deg, #1a1f3a, #0f1229);
      border: 2px solid rgba(255, 107, 107, 0.3);
      padding: 40px;
      border-radius: 25px;
      cursor: pointer;
      transition: all 0.4s;
      text-align: center;
      position: relative;
      overflow: hidden;
    }

    .category-card::before {
      content: '';
      position: absolute;
      top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: radial-gradient(circle, rgba(255, 107, 107, 0.1) 0%, transparent 70%);
      opacity: 0;
      transition: opacity 0.4s;
    }

    .category-card:hover::before {
      opacity: 1;
    }

    .category-card:hover {
      transform: translateY(-10px) scale(1.02);
      border-color: #ff6b6b;
      box-shadow: 0 20px 50px rgba(255, 107, 107, 0.4);
      background: linear-gradient(145deg, #2a2f4a, #1f2439);
    }

    .category-card:hover .category-icon {
      transform: scale(1.2) rotate(5deg);
    }

    .category-icon {
      font-size: 70px;
      margin-bottom: 20px;
      display: block;
      transition: transform 0.4s;
    }

    .category-name {
      font-size: 26px;
      font-weight: 700;
      color: #ffffff;
      margin: 0;
    }

    .category-description {
      font-size: 16px;
      color: #b0b0b0;
      margin-top: 10px;
    }

    /* Menu Modal */
    .menu-modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 100%);
      z-index: 3000;
      overflow-y: auto;
    }

    .menu-modal.active {
      display: block;
      animation: fadeIn 0.3s ease;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    .menu-modal-header {
      position: sticky;
      top: 0;
      background: rgba(10, 14, 39, 0.98);
      backdrop-filter: blur(15px);
      padding: 25px 40px;
      border-bottom: 2px solid #ff6b6b;
      display: flex;
      justify-content: space-between;
      align-items: center;
      z-index: 100;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.5);
    }

    .menu-modal-title {
      font-size: 36px;
      font-weight: 800;
      background: linear-gradient(135deg, #ff6b6b 0%, #ffd93d 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      margin: 0;
    }

    .close-btn {
      background: linear-gradient(135deg, #ff6b6b, #ffd93d);
      border: none;
      color: white;
      font-size: 32px;
      width: 60px;
      height: 60px;
      border-radius: 50%;
      cursor: pointer;
      transition: all 0.3s;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      box-shadow: 0 5px 20px rgba(255, 107, 107, 0.4);
    }

    .close-btn:hover {
      transform: rotate(90deg) scale(1.1);
      box-shadow: 0 8px 30px rgba(255, 107, 107, 0.6);
    }

    /* Quick Index */
    .quick-index {
      padding: 40px;
      max-width: 1400px;
      margin: 0 auto;
    }

    .quick-index-title {
      font-size: 28px;
      font-weight: 700;
      color: #ffffff;
      margin: 0 0 30px 0;
      text-align: center;
    }

    .index-list {
      display: flex;
      flex-wrap: wrap;
      gap: 15px;
      justify-content: center;
    }

    .index-item {
      background: rgba(255, 107, 107, 0.1);
      padding: 15px 30px;
      border-radius: 30px;
      cursor: pointer;
      transition: all 0.3s;
      font-weight: 600;
      color: #ffffff;
      font-size: 16px;
    }

    .index-item:hover {
      background: rgba(255, 107, 107, 0.25);
      transform: translateY(-3px);
      box-shadow: 0 8px 20px rgba(255, 107, 107, 0.3);
    }

    .index-item.active {
      background: linear-gradient(135deg, #ff6b6b, #ffd93d);
      box-shadow: 0 8px 25px rgba(255, 107, 107, 0.5);
    }

    /* Products List */
    .products-list {
      padding: 20px 40px 60px;
      max-width: 1400px;
      margin: 0 auto;
    }

    .product-item {
      background: rgba(26, 31, 58, 0.4);
      padding: 35px;
      margin-bottom: 20px;
      border-radius: 15px;
      transition: all 0.4s;
      scroll-margin-top: 180px;
      border: 1px solid rgba(255, 107, 107, 0.1);
    }

    .product-item:hover {
      background: rgba(26, 31, 58, 0.7);
      transform: translateX(-10px);
      box-shadow: 0 10px 30px rgba(255, 107, 107, 0.2);
      border-color: rgba(255, 107, 107, 0.3);
    }

    .product-item.highlight {
      background: rgba(255, 107, 107, 0.15);
      box-shadow: 0 15px 45px rgba(255, 107, 107, 0.5);
      animation: highlightPulse 2s ease;
    }

    @keyframes highlightPulse {
      0%, 100% { box-shadow: 0 15px 45px rgba(255, 107, 107, 0.5); }
      50% { box-shadow: 0 20px 60px rgba(255, 107, 107, 0.7); }
    }

    .product-header {
      margin-bottom: 20px;
      padding-bottom: 15px;
      border-bottom: 1px solid rgba(255, 107, 107, 0.2);
    }

    .product-name {
      font-size: 26px;
      font-weight: 700;
      color: #ffffff;
      margin: 0 0 10px 0;
    }

    .product-description {
      font-size: 16px;
      color: #b0b0b0;
      margin: 0;
      line-height: 1.6;
    }

    .product-sizes {
      display: flex;
      flex-direction: column;
      gap: 12px;
      margin-top: 20px;
    }

    .size-row {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 18px 25px;
      background: rgba(255, 107, 107, 0.08);
      border-radius: 12px;
      transition: all 0.3s;
    }

    .size-row:hover {
      background: rgba(255, 107, 107, 0.18);
      transform: translateX(-8px);
    }

    .size-label {
      font-size: 18px;
      font-weight: 600;
      color: #ffffff;
    }

    .size-price {
      font-size: 22px;
      font-weight: 700;
      background: linear-gradient(135deg, #ff6b6b, #ffd93d);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .single-price-box {
      text-align: center;
      padding: 25px;
      background: rgba(255, 107, 107, 0.15);
      border-radius: 15px;
      margin-top: 20px;
    }

    .single-price-box .size-price {
      font-size: 32px;
    }

    /* Order Button in Product */
    .order-product-btn {
      margin-top: 20px;
      padding: 15px 40px;
      background: linear-gradient(135deg, #25D366, #128C7E);
      color: white;
      border: none;
      border-radius: 30px;
      font-size: 18px;
      font-weight: 700;
      cursor: pointer;
      transition: all 0.3s;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      box-shadow: 0 5px 20px rgba(37, 211, 102, 0.3);
    }

    .order-product-btn:hover {
      transform: translateY(-3px);
      box-shadow: 0 8px 30px rgba(37, 211, 102, 0.5);
    }

    /* Map Section */
    .map-section {
      padding: 80px 40px;
      max-width: 1400px;
      margin: 0 auto;
    }

    .map-container {
      border-radius: 25px;
      overflow: hidden;
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
      height: 500px;
      margin-top: 40px;
      border: 3px solid rgba(255, 107, 107, 0.3);
    }

    .map-container iframe {
      width: 100%;
      height: 100%;
      border: none;
    }

    /* Social Media Section */
    .social-section {
      padding: 60px 40px;
      text-align: center;
      background: rgba(26, 31, 58, 0.5);
    }

    .social-title {
      font-size: 42px;
      font-weight: 800;
      margin: 0 0 40px 0;
      background: linear-gradient(135deg, #ff6b6b 0%, #ffd93d 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .social-buttons {
      display: flex;
      justify-content: center;
      gap: 30px;
      flex-wrap: wrap;
    }

    .social-btn {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 36px;
      cursor: pointer;
      transition: all 0.4s;
      text-decoration: none;
      box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
    }

    .social-btn:hover {
      transform: translateY(-10px) scale(1.1);
    }

    .social-btn.whatsapp {
      background: linear-gradient(135deg, #25D366, #128C7E);
    }

    .social-btn.facebook {
      background: linear-gradient(135deg, #1877F2, #0C63D4);
    }

    .social-btn.instagram {
      background: linear-gradient(135deg, #E4405F, #C13584, #833AB4);
    }

    .social-btn.phone {
      background: linear-gradient(135deg, #ff6b6b, #ff8787);
    }

    /* Footer */
    footer {
      background: rgba(10, 14, 39, 0.95);
      padding: 60px 40px 30px;
      border-top: 2px solid #ff6b6b;
      box-shadow: 0 -5px 30px rgba(0, 0, 0, 0.5);
    }

    .footer-content {
      max-width: 1400px;
      margin: 0 auto;
      text-align: center;
    }

    .footer-text {
      color: #b0b0b0;
      font-size: 16px;
      margin: 12px 0;
      line-height: 1.8;
    }

    .footer-highlight {
      background: linear-gradient(135deg, #ff6b6b, #ffd93d);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      font-weight: 700;
      font-size: 20px;
    }

    .footer-divider {
      height: 2px;
      background: linear-gradient(90deg, transparent, #ff6b6b, transparent);
      margin: 30px 0;
    }

    /* Toast Notification */
    .toast {
      position: fixed;
      bottom: -100px;
      right: 40px;
      background: linear-gradient(135deg, #25D366, #128C7E);
      color: white;
      padding: 20px 30px;
      border-radius: 15px;
      box-shadow: 0 10px 40px rgba(37, 211, 102, 0.4);
      z-index: 5000;
      transition: bottom 0.5s;
      font-size: 18px;
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 15px;
    }

    .toast.show {
      bottom: 40px;
    }

    /* Responsive */
    @media (max-width: 1024px) {
      .about-content {
        grid-template-columns: 1fr;
      }
      
      .about-image {
        order: -1;
      }
    }

    @media (max-width: 900px) {
      .hero-title { font-size: 48px; }
      .hero-subtitle { font-size: 22px; }
      .section-title { font-size: 40px; }
      .nav-links { gap: 15px; }
      .nav-links a { padding: 10px 18px; font-size: 14px; }
      .contact-info { gap: 25px; }
      .categories-grid { grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); }
    }

    @media (max-width: 600px) {
      .nav-container { 
        flex-direction: column; 
        gap: 20px; 
        padding: 20px; 
      }
      
      .logo { font-size: 22px; }
      
      .hero { 
        padding: 60px 20px; 
        margin-top: 120px;
      }
      
      .hero-title { font-size: 36px; }
      .hero-subtitle { font-size: 18px; }
      .section-title { font-size: 32px; }
      
      .cta-buttons {
        flex-direction: column;
        align-items: center;
      }
      
      .cta-button { 
        padding: 16px 40px; 
        font-size: 18px; 
        width: 100%;
        max-width: 300px;
        justify-content: center;
      }
      
      .contact-item { 
        flex-direction: column; 
        text-align: center; 
        gap: 8px; 
      }
      
      .categories-grid { 
        grid-template-columns: 1fr; 
      }
      
      .menu-modal-header { padding: 20px; }
      .menu-modal-title { font-size: 26px; }
      .close-btn { width: 50px; height: 50px; font-size: 28px; }
      .quick-index, .products-list { padding: 20px; }
      .product-item { padding: 25px; }
      
      .about-text h2 { font-size: 36px; }
      .about-text p { font-size: 18px; }
      
      .social-buttons { gap: 20px; }
      .social-btn { width: 70px; height: 70px; font-size: 32px; }
      
      .toast {
        right: 20px;
        left: 20px;
        text-align: center;
      }
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
  <script src="https://cdn.tailwindcss.com" type="text/javascript"></script>
 </head>
 <body><!-- Navigation -->
  <nav>
   <div class="nav-container">
    <div class="logo">
     🐟 HOOK FISH &amp; CHICKEN 🍗
    </div>
    <ul class="nav-links">
     <li><a href="#home">Home</a></li>
     <li><a href="#about">About Us</a></li>
     <li><a href="#menu">Menu</a></li>
     <li><a href="#location">Location</a></li>
     <li><a href="tel:313-861-5555">Call Us</a></li>
    </ul>
   </div>
  </nav><!-- Hero Section -->
  <section class="hero" id="home">
   <div class="hero-content">
    <h1 class="hero-title">Fresh Seafood &amp; Chicken</h1>
    <p class="hero-subtitle">Delicious, Fresh, Every Day 🌊✨</p>
    <div class="cta-buttons"><a href="https://wa.me/13138615555" target="_blank" rel="noopener noreferrer" class="cta-button"> <span>📱</span> Order via WhatsApp </a> <a href="tel:313-861-5555" class="cta-button secondary"> <span>📞</span> Call Now </a>
    </div>
   </div>
  </section><!-- Contact Info Bar -->
  <div class="contact-bar">
   <div class="contact-info">
    <div class="contact-item" onclick="window.open('tel:313-861-5555')"><span class="contact-icon">📞</span> <span>313-861-5555</span>
    </div>
    <div class="contact-item" onclick="window.open('https://maps.google.com/maps/place//data=!4m2!3m1!1s0x8824c9539d154b23:0x32182f8b2adf7eb?entry=s&amp;sa=X&amp;ved=2ahUKEwit7Yqbs_-QAxU01vACHf5LBHIQ4kB6BAgEEAA', '_blank', 'noopener,noreferrer')"><span class="contact-icon">📍</span> <span>10600 W. 7 MILE RD., Detroit, MI 48221</span>
    </div>
    <div class="contact-item"><span class="contact-icon">🕐</span> <span>Mon-Thu: 10AM-10PM | Fri-Sat: 10AM-11PM | Sun: 10AM-10PM</span>
    </div>
   </div>
  </div><!-- About Section -->
  <section class="about-section" id="about">
   <div class="about-content">
    <div class="about-text">
     <h2>About Us</h2>
     <p>🐟 <strong>Hook Fish and Chicken</strong> has been Detroit's favorite destination for fresh seafood and delicious chicken for years.</p>
     <p>🌟 We pride ourselves on serving the finest quality fish and seafood, prepared fresh daily with secret recipes that make every bite unforgettable.</p>
     <p>👨‍🍳 Our team of professional chefs works passionately to ensure high quality in every dish we serve to our valued customers.</p>
    </div>
    <div class="about-image">
     <svg viewbox="0 0 400 400" xmlns="http://www.w3.org/2000/svg"><!-- Fish --> <ellipse cx="200" cy="180" rx="100" ry="60" fill="#ff6b6b" opacity="0.8" /> <circle cx="160" cy="165" r="8" fill="white" /> <circle cx="163" cy="165" r="4" fill="#0a0e27" /> <path d="M 280 180 L 330 160 L 330 200 Z" fill="#ff8787" /> <!-- Chicken Leg --> <ellipse cx="220" cy="280" rx="40" ry="55" fill="#ffd93d" opacity="0.9" /> <rect x="210" y="320" width="20" height="40" rx="5" fill="#ffed4e" /> <circle cx="220" cy="320" r="8" fill="#fff" /> <!-- Decorative elements --> <circle cx="100" cy="100" r="15" fill="#ffd93d" opacity="0.3" /> <circle cx="320" cy="300" r="20" fill="#ff6b6b" opacity="0.3" /> <circle cx="80" cy="320" r="12" fill="#ffd93d" opacity="0.4" />
     </svg>
    </div>
   </div><!-- Features Grid -->
   <div class="features-grid">
    <div class="feature-card"><span class="feature-icon">🐟</span>
     <h3 class="feature-title">Fresh Daily</h3>
     <p class="feature-text">We select the finest fresh fish and seafood every day</p>
    </div>
    <div class="feature-card"><span class="feature-icon">👨‍🍳</span>
     <h3 class="feature-title">Expert Chefs</h3>
     <p class="feature-text">Team of skilled chefs with years of seafood expertise</p>
    </div>
    <div class="feature-card"><span class="feature-icon">⏰</span>
     <h3 class="feature-title">Quick Service</h3>
     <p class="feature-text">Fast preparation and service for all your orders</p>
    </div>
    <div class="feature-card"><span class="feature-icon">💯</span>
     <h3 class="feature-title">Quality Guaranteed</h3>
     <p class="feature-text">We guarantee the highest quality in every dish we serve</p>
    </div>
   </div>
  </section><!-- Menu Categories Section -->
  <section class="menu-categories" id="menu">
   <h2 class="section-title">Our Menu</h2>
   <p class="section-subtitle">Click to explore our delicious dishes 🍽️</p>
   <div class="categories-grid">
    <div class="category-card" onclick="openMenu('combos')"><span class="category-icon">🍱</span>
     <h3 class="category-name">Special Combos</h3>
     <p class="category-description">Featured meals at best prices</p>
    </div>
    <div class="category-card" onclick="openMenu('fish')"><span class="category-icon">🐟</span>
     <h3 class="category-name">Fresh Fish</h3>
     <p class="category-description">Finest quality fresh fish</p>
    </div>
    <div class="category-card" onclick="openMenu('chicken')"><span class="category-icon">🍗</span>
     <h3 class="category-name">Fresh Chicken</h3>
     <p class="category-description">Fresh chicken with special recipes</p>
    </div>
    <div class="category-card" onclick="openMenu('seafood')"><span class="category-icon">🦐</span>
     <h3 class="category-name">Seafood</h3>
     <p class="category-description">Shrimp, crab, and more</p>
    </div>
    <div class="category-card" onclick="openMenu('sides')"><span class="category-icon">🍟</span>
     <h3 class="category-name">Side Dishes</h3>
     <p class="category-description">Fries, rice, and tasty additions</p>
    </div>
    <div class="category-card" onclick="openMenu('desserts')"><span class="category-icon">🍰</span>
     <h3 class="category-name">Desserts</h3>
     <p class="category-description">Fresh and delicious sweets</p>
    </div>
   </div>
  </section><!-- Map Section -->
  <section class="map-section" id="location">
   <h2 class="section-title">Our Location</h2>
   <p class="section-subtitle">Visit us in Detroit 📍</p>
   <div class="map-container"><iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2945.8234567891234!2d-83.2!3d42.43!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8824c9539d154b23%3A0x32182f8b2adf7eb!2zSG9vayBGaXNoICYgQ2hpY2tlbg!5e0!3m2!1sen!2sus!4v1234567890123!5m2!1sen!2sus" allowfullscreen loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
   </div>
  </section><!-- Social Media Section -->
  <section class="social-section">
   <h2 class="social-title">Connect With Us 💬</h2>
   <div class="social-buttons"><a href="https://wa.me/13138615555" target="_blank" rel="noopener noreferrer" class="social-btn whatsapp" title="WhatsApp"> <span>💬</span> </a> <a href="tel:313-861-5555" class="social-btn phone" title="Call Us"> <span>📞</span> </a> <a href="#" target="_blank" rel="noopener noreferrer" class="social-btn facebook" title="Facebook"> <span>📘</span> </a> <a href="#" target="_blank" rel="noopener noreferrer" class="social-btn instagram" title="Instagram"> <span>📸</span> </a>
   </div>
  </section><!-- Footer -->
  <footer>
   <div class="footer-content">
    <p class="footer-text"><span class="footer-highlight">🐟 HOOK FISH AND CHICKEN 🍗</span></p>
    <p class="footer-text">Fresh, Delicious, Every Day 🌊✨</p>
    <div class="footer-divider"></div>
    <p class="footer-text">📍 10600 W. 7 MILE RD., Detroit, MI 48221</p>
    <p class="footer-text">📞 313-861-5555 • Open 7 Days a Week</p>
    <p class="footer-text">🕐 Mon-Thu: 10AM-10PM | Fri-Sat: 10AM-11PM | Sun: 10AM-10PM</p>
    <p class="footer-text">🛍️ Pick-Up Service Available</p>
    <div class="footer-divider"></div>
    <p class="footer-text">© 2024 Hook Fish and Chicken. All rights reserved.</p>
   </div>
  </footer><!-- Menu Modal -->
  <div class="menu-modal" id="menuModal">
   <div class="menu-modal-header">
    <h2 class="menu-modal-title" id="modalTitle">Menu</h2><button class="close-btn" onclick="closeMenu()">×</button>
   </div>
   <div class="quick-index">
    <h3 class="quick-index-title">Quick Navigation 🔍</h3>
    <div class="index-list" id="indexList"></div>
   </div>
   <div class="products-list" id="productsList"></div>
  </div><!-- Toast Notification -->
  <div class="toast" id="toast"><span>✅</span> <span id="toastMessage">Success!</span>
  </div>
  <script>
    const menuData = {
      combos: [
        { name: '1: 2 PCS Whiting + 6 JUMBO SHRIMP', description: 'Includes 2 whole wings or 2 wing dings, fries & bread', price: 14.99 },
        { name: '2: 2 PCS Orange Roughy + 6 JUMBO SHRIMP', description: 'Includes 2 whole wings or 2 wing dings, fries & bread', price: 15.99 },
        { name: '3: 2 PCS Catfish + 6 JUMBO SHRIMP', description: 'Includes 2 whole wings or 2 wing dings, fries & bread', price: 15.99 },
        { name: '4: 2 PCS White Bass + 6 JUMBO SHRIMP', description: 'Includes 2 whole wings or 2 wing dings, fries & bread', price: 15.99 },
        { name: '5: 2 PCS Perch + 6 JUMBO SHRIMP', description: 'Includes 2 whole wings or 2 wing dings, fries & bread', price: 15.99 },
        { name: '6: 2 PCS Tilapia + 6 JUMBO SHRIMP', description: 'Includes 2 whole wings or 2 wing dings, fries & bread', price: 15.99 },
        { name: '7: 10 JUMBO SHRIMP', description: 'With fries & bread', price: 15.99 },
        { name: '8: 2 PCS Any Fish + 10 JUMBO SHRIMP', description: 'With fries & bread', price: 15.99 },
        { name: '9: 20 PCS Ocean Perch', description: 'With fries & bread', price: 15.99 },
        { name: '10: 20 PCS Catfish', description: 'With fries & bread', price: 15.99 },
        { name: '11: 20 PCS Tilapia', description: 'With fries & bread', price: 15.99 },
        { name: '12: 20 PCS Whiting', description: 'With fries & bread', price: 16.99 },
        { name: '13: 10 LARGE SHRIMP', description: 'With fries & bread', price: 17.99 },
        { name: '14: 5 LARGE SHRIMP + 6 JUMBO SHRIMP', description: 'With fries & bread', price: 16.99 },
        { name: '15: 10 LARGE SHRIMP', description: 'With fries & bread', price: 17.99 },
        { name: '16: 10 WHOLE WINGS / 10 WING DINGS', description: 'With fries & bread', price: 15.99 },
        { name: '17: 20 WING DINGS', description: 'With fries & bread', price: 14.99 },
        { name: '18: 3 WHOLE WINGS', description: 'With fries & bread', price: 14.99 },
        { name: '19: 10 LARGE SHRIMP + 2 TENDERS + 2 Any Fish', description: 'With fries', price: 15.99 },
        { name: '20: 3 TENDER + FRIES', description: 'Chicken tenders with fries', price: 12.99 },
        { name: '21: 15 LARGE SHRIMP + 2 WHOLE WINGS + 2 Any Fish', description: 'With fries', price: 15.99 },
        { name: '22: 5 WHOLE WINGS + 10 WING DINGS + 2 Any Fish', description: 'With fries', price: 16.99 },
        { name: '23: 10 PCS Catfish', description: 'Bulk pack', price: 42.99 },
        { name: '24: 30 WING DINGS', description: 'Bulk pack', price: 26.99 },
        { name: '25: 20 WHOLE WINGS + 10 PCS Any Fish + LARGE FRIES', description: 'Big family pack', price: 49.99 },
        { name: '26: 15 PCS Orange Roughy', description: 'Bulk pack', price: 61.99 },
        { name: '27: 20 PCS Tilapia', description: 'Bulk pack', price: 66.99 },
        { name: '28: 40 WHOLE WINGS + 20 PCS Any Fish + LARGE FRIES', description: 'Mega family pack', price: 81.99 },
        { name: '29: 100 WING DINGS / 100 JUMBO SHRIMP', description: 'Party pack', price: 81.99 },
        { name: '⭐ NEW 30: 15 WHOLE WINGS + 5 PCS Any Fish + 1/2 LB Shrimp + Large Fries + 2 Pop', description: 'Special deal!', price: 49.99 },
        { name: '⭐ NEW 31: 100 PCS Fish + 15 PCS Wings + 20 Large Shrimp', description: 'Mega deal! (Fries and 2 Liter Pop NOT included)', price: 59.99 }
      ],
      fish: [
        { name: 'Whiting Fillets', description: 'Fresh whiting, perfectly fried', sizes: [
          { name: '1 PC', price: 5.99 },
          { name: '2 PCS', price: 6.99 },
          { name: 'Dinner (3 PCS)', price: 10.99 },
          { name: 'Bucket', price: 14.99 }
        ]},
        { name: 'Swai', description: 'Fresh swai fillet', sizes: [
          { name: '1 PC', price: 5.99 },
          { name: '2 PCS', price: 7.99 },
          { name: 'Dinner (3 PCS)', price: 12.99 },
          { name: 'Bucket', price: 15.99 }
        ]},
        { name: 'Tilapia', description: 'Fresh and light tilapia fillet', sizes: [
          { name: '1 PC', price: 6.99 },
          { name: '2 PCS', price: 8.99 },
          { name: 'Dinner (3 PCS)', price: 13.49 },
          { name: 'Bucket', price: 16.99 }
        ]},
        { name: 'Catfish', description: 'Premium catfish fillet', sizes: [
          { name: '1 PC', price: 6.99 },
          { name: '2 PCS', price: 8.99 },
          { name: 'Dinner (3 PCS)', price: 13.49 },
          { name: 'Bucket', price: 16.99 }
        ]},
        { name: 'Ocean Perch', description: 'Fresh ocean perch', sizes: [
          { name: '1 PC', price: 7.99 },
          { name: '2 PCS', price: 9.99 },
          { name: 'Dinner (3 PCS)', price: 14.49 },
          { name: 'Bucket', price: 17.99 }
        ]},
        { name: 'White Bass', description: 'Fresh white bass', sizes: [
          { name: '1 PC', price: 7.99 },
          { name: '2 PCS', price: 9.99 },
          { name: 'Dinner (3 PCS)', price: 14.49 },
          { name: 'Bucket', price: 17.99 }
        ]},
        { name: 'Orange Roughy Fillets', description: 'Premium orange roughy fillet', sizes: [
          { name: '1 PC', price: 8.99 },
          { name: '2 PCS', price: 10.99 },
          { name: 'Dinner (3 PCS)', price: 15.99 },
          { name: 'Bucket', price: 18.99 }
        ]},
        { name: 'Red Snapper', description: 'Fresh red snapper fillet', sizes: [
          { name: '1 PC', price: 8.99 },
          { name: '2 PCS', price: 10.99 },
          { name: 'Dinner (3 PCS)', price: 15.99 },
          { name: 'Bucket', price: 18.99 }
        ]},
        { name: 'Cod Fish', description: 'Premium cod fillet', sizes: [
          { name: '1 PC', price: 7.99 },
          { name: '2 PCS', price: 9.99 },
          { name: 'Dinner (3 PCS)', price: 14.99 },
          { name: 'Bucket', price: 17.99 }
        ]},
        { name: 'Smelts', description: 'Fresh smelts', sizes: [
          { name: '1 PC', price: 4.99 },
          { name: '2 PCS', price: 6.99 },
          { name: 'Dinner (3 PCS)', price: 11.99 }
        ]},
        { name: 'Flounder', description: 'Fresh flounder fillet', sizes: [
          { name: '1 PC', price: 5.99 },
          { name: '2 PCS', price: 7.99 },
          { name: 'Dinner (3 PCS)', price: 12.99 }
        ]},
        { name: 'Catfish Nuggets', description: 'Bite-sized catfish pieces', sizes: [
          { name: '1 PC', price: 4.99 },
          { name: '2 PCS', price: 6.99 },
          { name: 'Dinner (3 PCS)', price: 8.99 }
        ]},
        { name: 'Whiting By The Piece', description: 'Bulk whiting fish', sizes: [
          { name: '10 PCS', price: 18.00 },
          { name: '15 PCS', price: 26.00 },
          { name: '20 PCS', price: 33.00 },
          { name: '30 PCS', price: 43.00 }
        ]},
        { name: 'Catfish By The Piece', description: 'Bulk catfish', sizes: [
          { name: '10 PCS', price: 22.00 },
          { name: '15 PCS', price: 33.00 },
          { name: '20 PCS', price: 40.00 },
          { name: '30 PCS', price: 53.00 }
        ]},
        { name: 'Ocean Perch By The Piece', description: 'Bulk ocean perch', sizes: [
          { name: '10 PCS', price: 28.00 },
          { name: '15 PCS', price: 38.00 },
          { name: '20 PCS', price: 48.00 },
          { name: '30 PCS', price: 58.00 }
        ]},
        { name: 'Tilapia By The Piece', description: 'Bulk tilapia', sizes: [
          { name: '10 PCS', price: 19.00 },
          { name: '15 PCS', price: 28.00 },
          { name: '20 PCS', price: 33.00 },
          { name: '30 PCS', price: 43.00 }
        ]},
        { name: 'Swai By The Piece', description: 'Bulk swai fish', sizes: [
          { name: '10 PCS', price: 18.00 },
          { name: '15 PCS', price: 28.00 },
          { name: '20 PCS', price: 33.00 },
          { name: '30 PCS', price: 43.00 }
        ]},
        { name: 'Orange Roughy By The Piece', description: 'Bulk orange roughy', sizes: [
          { name: '10 PCS', price: 30.00 },
          { name: '15 PCS', price: 34.00 },
          { name: '20 PCS', price: 45.00 },
          { name: '30 PCS', price: 65.00 }
        ]}
      ],
      chicken: [
        { name: 'Whole Wings', description: 'Fresh whole chicken wings', sizes: [
          { name: '5 PC', price: 6.99 },
          { name: '10 PC', price: 12.99 },
          { name: '15 PC', price: 17.99 },
          { name: '20 PC', price: 24.99 },
          { name: '30 PC', price: 33.99 },
          { name: '50 PC', price: 56.99 },
          { name: '75 PC', price: 79.99 },
          { name: '100 PC', price: 107.99 }
        ]},
        { name: 'Wing Dings', description: 'Crispy wing pieces', sizes: [
          { name: '5 PC', price: 4.99 },
          { name: '10 PC', price: 8.99 },
          { name: '15 PC', price: 12.99 },
          { name: '20 PC', price: 16.99 },
          { name: '30 PC', price: 22.99 },
          { name: '50 PC', price: 32.99 },
          { name: '75 PC', price: 49.99 },
          { name: '100 PC', price: 69.99 }
        ]},
        { name: 'Tender', description: 'Tender and delicious chicken strips', sizes: [
          { name: '5 PCS', price: 8.99 },
          { name: '10 PCS', price: 14.99 },
          { name: '15 PCS', price: 21.99 },
          { name: '20 PCS', price: 27.99 },
          { name: '30 PCS', price: 37.99 },
          { name: '40 PCS', price: 48.99 },
          { name: '50 PCS', price: 58.99 }
        ]},
        { name: 'Legs & Thighs', description: 'Fresh chicken legs and thighs', sizes: [
          { name: '3 PCS', price: 3.99 },
          { name: '6 PCS', price: 7.99 },
          { name: '10 PCS', price: 12.99 },
          { name: '20 PCS', price: 29.99 }
        ]},
        { name: 'Gizzards', description: 'Fried chicken gizzards', sizes: [
          { name: '1/2 LB', price: 7.99 },
          { name: '1 LB', price: 12.99 }
        ]},
        { name: 'Liver', description: 'Fried chicken livers', sizes: [
          { name: '1/2 LB', price: 6.99 },
          { name: '1 LB', price: 10.99 }
        ]}
      ],
      seafood: [
        { name: 'Large Shrimp', description: 'Fresh large shrimp', sizes: [
          { name: '1/4 LB', price: 6.99 },
          { name: '1/2 LB', price: 10.99 },
          { name: '1 LB', price: 14.99 },
          { name: '3 LB', price: 39.99 },
          { name: '5 LB', price: 59.99 }
        ]},
        { name: 'Jumbo Shrimp', description: 'Premium jumbo shrimp', sizes: [
          { name: '1/4 LB', price: 8.99 },
          { name: '1/2 LB', price: 12.99 },
          { name: '1 LB', price: 16.99 },
          { name: '3 LB', price: 44.99 },
          { name: '5 LB', price: 69.99 }
        ]},
        { name: 'Scallops', description: 'Fresh sea scallops', sizes: [
          { name: '1/2 LB', price: 9.99 },
          { name: '1 LB', price: 16.99 }
        ]},
        { name: 'Oysters', description: 'Fresh oysters', sizes: [
          { name: '1/2 LB', price: 8.99 },
          { name: '1 LB', price: 14.99 }
        ]},
        { name: 'Crab Legs', description: 'Premium crab legs (Market Price)', sizes: [
          { name: '3-4 LBS', price: 44.99 },
          { name: '5 LBS', price: 59.99 }
        ]},
        { name: 'Lobster Tails', description: 'Fresh lobster tails', price: 'Market Price' }
      ],
      sides: [
        { name: 'French Fries', description: 'Crispy golden fries', sizes: [
          { name: 'Small', price: 2.99 },
          { name: 'Medium', price: 4.99 },
          { name: 'Family', price: 6.99 }
        ]},
        { name: 'Onion Rings', description: 'Crispy onion rings', sizes: [
          { name: 'Small', price: 2.99 },
          { name: 'Medium', price: 4.99 },
          { name: 'Family', price: 8.99 }
        ]},
        { name: 'Rice', description: 'Soft white rice', sizes: [
          { name: 'Small', price: 3.99 },
          { name: 'Medium', price: 5.99 },
          { name: 'Family', price: 9.99 }
        ]},
        { name: 'Coleslaw', description: 'Creamy coleslaw', sizes: [
          { name: 'Small', price: 1.49 },
          { name: 'Medium', price: 4.99 },
          { name: 'Family', price: 8.99 }
        ]},
        { name: 'Mushrooms', description: 'Breaded and fried mushrooms', sizes: [
          { name: 'Small', price: 2.99 },
          { name: 'Medium', price: 4.99 },
          { name: 'Family', price: 8.99 }
        ]},
        { name: 'Cheese Sticks', description: 'Mozzarella cheese sticks', sizes: [
          { name: 'Small', price: 2.99 },
          { name: 'Medium', price: 5.99 }
        ]},
        { name: 'Okra', description: 'Fried okra', sizes: [
          { name: 'Small', price: 2.99 },
          { name: 'Medium', price: 5.99 }
        ]},
        { name: 'Crab Cake', description: 'Delicious crab cakes', sizes: [
          { name: 'Small', price: 2.99 },
          { name: 'Medium', price: 5.99 }
        ]},
        { name: 'Clams', description: 'Fried baby clams', sizes: [
          { name: 'Small', price: 2.99 },
          { name: 'Medium', price: 5.99 }
        ]},
        { name: 'Stuffed Jalapenos', description: 'Spicy peppers stuffed with cream cheese', sizes: [
          { name: 'Small', price: 2.99 },
          { name: 'Medium', price: 5.99 }
        ]},
        { name: 'Extra Jalapenos (By the Piece)', description: 'Extra jalapenos', price: 1.00 }
      ],
      desserts: [
        { name: 'Delicious Cakes 🍰', description: 'Ask us about our delicious available cakes! Fresh and very tasty.', price: 'Ask for pricing' }
      ]
    };

    const menuTitles = {
      combos: 'Special Combos 🍱',
      fish: 'Fresh Fish 🐟',
      chicken: 'Fresh Chicken 🍗',
      seafood: 'Seafood 🦐',
      sides: 'Side Dishes 🍟',
      desserts: 'Desserts 🍰'
    };

    let currentHighlight = null;
    let currentCategory = '';

    function openMenu(category) {
      currentCategory = category;
      const modal = document.getElementById('menuModal');
      const modalTitle = document.getElementById('modalTitle');
      const indexList = document.getElementById('indexList');
      const productsList = document.getElementById('productsList');

      modalTitle.textContent = menuTitles[category];
      indexList.innerHTML = '';
      productsList.innerHTML = '';
      currentHighlight = null;

      const items = menuData[category];
      
      items.forEach((item, idx) => {
        const indexBtn = document.createElement('div');
        indexBtn.className = 'index-item';
        indexBtn.textContent = item.name;
        indexBtn.id = `idx-${category}-${idx}`;
        indexBtn.onclick = () => {
          if (currentHighlight) {
            currentHighlight.classList.remove('active');
          }
          indexBtn.classList.add('active');
          currentHighlight = indexBtn;

          const productCard = document.getElementById(`prod-${category}-${idx}`);
          if (productCard) {
            document.querySelectorAll('.product-item').forEach(card => {
              card.classList.remove('highlight');
            });
            
            productCard.classList.add('highlight');
            productCard.scrollIntoView({ behavior: 'smooth', block: 'start' });

            setTimeout(() => {
              productCard.classList.remove('highlight');
            }, 3000);
          }
        };
        indexList.appendChild(indexBtn);

        const productCard = document.createElement('div');
        productCard.className = 'product-item';
        productCard.id = `prod-${category}-${idx}`;

        let content = `
          <div class="product-header">
            <h3 class="product-name">${item.name}</h3>
            <p class="product-description">${item.description}</p>
          </div>
        `;

        if (item.sizes) {
          content += '<div class="product-sizes">';
          item.sizes.forEach(size => {
            content += `
              <div class="size-row">
                <span class="size-label">${size.name}</span>
                <span class="size-price">$${size.price.toFixed(2)}</span>
              </div>
            `;
          });
          content += '</div>';
        } else if (item.price) {
          if (typeof item.price === 'number') {
            content += `
              <div class="single-price-box">
                <span class="size-price">$${item.price.toFixed(2)}</span>
              </div>
            `;
          } else {
            content += `
              <div class="single-price-box">
                <span class="size-price">${item.price}</span>
              </div>
            `;
          }
        }

        content += `
          <button class="order-product-btn" onclick="orderViaWhatsApp('${item.name.replace(/'/g, "\\'")}')">
            <span>💬</span>
            Order via WhatsApp
          </button>
        `;

        productCard.innerHTML = content;
        productsList.appendChild(productCard);
      });

      modal.classList.add('active');
      document.body.style.overflow = 'hidden';
    }

    function closeMenu() {
      const modal = document.getElementById('menuModal');
      modal.classList.remove('active');
      document.body.style.overflow = 'auto';
      currentHighlight = null;
    }

    function orderViaWhatsApp(productName) {
      const message = `Hello 👋\nI would like to order: ${productName}\n\nPlease contact me to confirm the order.`;
      const whatsappUrl = `https://wa.me/13138615555?text=${encodeURIComponent(message)}`;
      window.open(whatsappUrl, '_blank', 'noopener,noreferrer');
      
      showToast('Opening WhatsApp... 💬');
    }

    function showToast(message) {
      const toast = document.getElementById('toast');
      const toastMessage = document.getElementById('toastMessage');
      toastMessage.textContent = message;
      toast.classList.add('show');
      
      setTimeout(() => {
        toast.classList.remove('show');
      }, 3000);
    }

    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        if (target) {
          target.scrollIntoView({
            behavior: 'smooth',
            block: 'start'
          });
        }
      });
    });

    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape') {
        closeMenu();
      }
    });
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9a1443e6a739809f',t:'MTc2MzYwMzA5OC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
