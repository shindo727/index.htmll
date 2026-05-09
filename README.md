<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shekss - Finding the best deals in Egypt</title>
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&family=Sora:wght@400;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --blue: #2563EB;
    --blue-dark: #1d4ed8;
    --blue-light: #3b82f6;
    --orange: #f97316;
    --orange-dark: #ea6c09;
    --gray-50: #f8fafc;
    --gray-100: #f1f5f9;
    --gray-200: #e2e8f0;
    --gray-400: #94a3b8;
    --gray-600: #475569;
    --gray-800: #1e293b;
    --white: #ffffff;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Plus Jakarta Sans', sans-serif;
    color: var(--gray-800);
    background: var(--white);
  }

  /* NAV */
  nav {
    position: sticky; top: 0; z-index: 100;
    background: white;
    border-bottom: 1px solid var(--gray-200);
    padding: 0 40px;
    display: flex; align-items: center; justify-content: space-between;
    height: 64px;
    box-shadow: 0 1px 4px rgba(0,0,0,0.06);
  }
  .nav-logo {
    display: flex; align-items: center; gap: 8px;
    font-family: 'Sora', sans-serif;
    font-weight: 700; font-size: 20px; color: var(--blue);
    text-decoration: none;
  }
  .nav-logo svg { width: 28px; height: 28px; }
  .nav-links { display: flex; align-items: center; gap: 4px; }
  .nav-links a {
    padding: 6px 14px; border-radius: 6px;
    text-decoration: none; font-size: 14px; font-weight: 500;
    color: var(--gray-600); transition: all 0.2s;
  }
  .nav-links a:hover, .nav-links a.active { color: var(--blue); background: #eff6ff; }
  .btn-explore {
    background: var(--orange); color: white;
    border: none; padding: 9px 18px; border-radius: 8px;
    font-size: 14px; font-weight: 600; cursor: pointer;
    transition: background 0.2s; text-decoration: none;
  }
  .btn-explore:hover { background: var(--orange-dark); }

  /* PAGES */
  .page { display: none; }
  .page.active { display: block; }

  /* HERO */
  .hero {
    background: linear-gradient(135deg, #1d4ed8 0%, #2563eb 40%, #7c3aed 100%);
    min-height: 520px;
    display: flex; align-items: center; justify-content: center;
    position: relative; overflow: hidden;
    padding: 60px 40px;
  }
  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="20" cy="20" r="40" fill="rgba(255,255,255,0.03)"/><circle cx="80" cy="80" r="50" fill="rgba(255,255,255,0.03)"/></svg>');
    background-size: cover;
  }
  .hero-overlay {
    position: absolute; inset: 0;
    background: linear-gradient(to right, rgba(29,78,216,0.85) 50%, transparent);
  }
  .hero-bg {
    position: absolute; right: 0; top: 0; bottom: 0; width: 50%;
    background: url('https://images.unsplash.com/photo-1555396273-367ea4eb4db5?w=800') center/cover;
    opacity: 0.3;
  }
  .hero-content { position: relative; z-index: 2; max-width: 650px; }
  .hero-badge {
    display: inline-flex; align-items: center; gap: 6px;
    background: rgba(255,255,255,0.15); color: white;
    padding: 6px 14px; border-radius: 20px; font-size: 13px; font-weight: 500;
    margin-bottom: 20px; backdrop-filter: blur(4px);
  }
  .hero-badge::before { content: '✦'; font-size: 10px; }
  .hero h1 {
    font-family: 'Sora', sans-serif;
    font-size: 52px; font-weight: 700; color: white; line-height: 1.1;
    margin-bottom: 18px;
  }
  .hero p {
    font-size: 18px; color: rgba(255,255,255,0.85); line-height: 1.6;
    margin-bottom: 32px; max-width: 500px;
  }
  .hero-btns { display: flex; gap: 12px; flex-wrap: wrap; }
  .btn-primary {
    background: var(--orange); color: white;
    border: none; padding: 12px 24px; border-radius: 8px;
    font-size: 15px; font-weight: 600; cursor: pointer;
    display: inline-flex; align-items: center; gap: 6px;
    text-decoration: none; transition: all 0.2s;
  }
  .btn-primary:hover { background: var(--orange-dark); transform: translateY(-1px); }
  .btn-secondary {
    background: rgba(255,255,255,0.15); color: white;
    border: 1px solid rgba(255,255,255,0.3);
    padding: 12px 24px; border-radius: 8px;
    font-size: 15px; font-weight: 600; cursor: pointer;
    text-decoration: none; backdrop-filter: blur(4px);
    transition: all 0.2s;
  }
  .btn-secondary:hover { background: rgba(255,255,255,0.25); }

  /* SECTIONS */
  section { padding: 60px 40px; max-width: 1200px; margin: 0 auto; }
  .section-label {
    display: inline-block; font-size: 12px; font-weight: 600;
    text-transform: uppercase; letter-spacing: 1px;
    color: var(--blue); background: #eff6ff; padding: 4px 12px; border-radius: 20px;
    margin-bottom: 14px;
  }
  h2.section-title {
    font-family: 'Sora', sans-serif; font-size: 36px; font-weight: 700;
    color: var(--gray-800); margin-bottom: 10px;
  }
  p.section-sub { font-size: 16px; color: var(--gray-600); margin-bottom: 40px; }

  /* DEALS GRID */
  .deals-filters {
    display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 28px;
  }
  .filter-btn {
    padding: 7px 18px; border-radius: 20px; border: 1px solid var(--gray-200);
    font-size: 13px; font-weight: 500; cursor: pointer; background: white;
    color: var(--gray-600); transition: all 0.2s;
  }
  .filter-btn.active, .filter-btn:hover {
    background: var(--blue); color: white; border-color: var(--blue);
  }
  .deals-grid {
    display: grid; grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 20px;
  }
  .deal-card {
    border: 1px solid var(--gray-200); border-radius: 14px; overflow: hidden;
    background: white; transition: all 0.3s; position: relative;
  }
  .deal-card:hover { transform: translateY(-4px); box-shadow: 0 12px 32px rgba(0,0,0,0.1); }
  .deal-img {
    height: 160px; background: var(--gray-100);
    display: flex; align-items: center; justify-content: center;
    position: relative; overflow: hidden;
  }
  .deal-img img { width: 100%; height: 100%; object-fit: cover; }
  .hot-badge {
    position: absolute; top: 10px; left: 10px;
    background: #ef4444; color: white; font-size: 11px; font-weight: 700;
    padding: 3px 10px; border-radius: 4px; text-transform: uppercase;
  }
  .discount-badge {
    position: absolute; top: 10px; right: 10px;
    background: var(--blue); color: white; font-size: 18px; font-weight: 700;
    padding: 4px 10px; border-radius: 6px;
  }
  .deal-body { padding: 16px; }
  .deal-name { font-weight: 700; font-size: 16px; margin-bottom: 6px; }
  .deal-desc { font-size: 13px; color: var(--gray-600); margin-bottom: 10px; line-height: 1.4; }
  .deal-cat {
    font-size: 11px; font-weight: 600; text-transform: uppercase;
    color: var(--blue); letter-spacing: 0.5px; margin-bottom: 10px;
  }
  .deal-timer {
    font-size: 12px; color: var(--gray-600); margin-bottom: 12px;
    display: flex; align-items: center; gap: 4px;
  }
  .btn-claim {
    width: 100%; background: var(--blue); color: white;
    border: none; padding: 10px; border-radius: 8px;
    font-size: 14px; font-weight: 600; cursor: pointer;
    display: flex; align-items: center; justify-content: center; gap: 6px;
    transition: background 0.2s;
  }
  .btn-claim:hover { background: var(--blue-dark); }

  /* BLOG */
  .blog-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); gap: 24px; }
  .blog-card {
    border-radius: 14px; overflow: hidden; border: 1px solid var(--gray-200);
    background: white; transition: all 0.3s;
  }
  .blog-card:hover { transform: translateY(-3px); box-shadow: 0 8px 24px rgba(0,0,0,0.08); }
  .blog-img { height: 180px; background: var(--gray-200); position: relative; overflow: hidden; }
  .blog-img img { width: 100%; height: 100%; object-fit: cover; }
  .blog-tag {
    position: absolute; bottom: 10px; left: 10px;
    background: rgba(0,0,0,0.6); color: white; font-size: 11px; font-weight: 600;
    padding: 3px 10px; border-radius: 4px; text-transform: uppercase;
    backdrop-filter: blur(4px);
  }
  .blog-body { padding: 18px; }
  .blog-body h3 { font-size: 16px; font-weight: 700; margin-bottom: 8px; line-height: 1.4; }
  .blog-body p { font-size: 13px; color: var(--gray-600); line-height: 1.5; margin-bottom: 14px; }
  .read-more { color: var(--blue); font-size: 13px; font-weight: 600; text-decoration: none; display: inline-flex; align-items: center; gap: 4px; }
  .read-more:hover { gap: 8px; }

  /* CTA SECTION */
  .cta-section {
    background: linear-gradient(135deg, var(--blue) 0%, #7c3aed 100%);
    border-radius: 20px; padding: 60px; text-align: center;
    margin: 0 40px 60px; color: white;
  }
  .cta-section h2 { font-family: 'Sora', sans-serif; font-size: 36px; font-weight: 700; margin-bottom: 14px; }
  .cta-section p { font-size: 17px; opacity: 0.85; margin-bottom: 28px; }
  .btn-white {
    background: white; color: var(--blue);
    border: none; padding: 12px 28px; border-radius: 8px;
    font-size: 15px; font-weight: 700; cursor: pointer;
    text-decoration: none; display: inline-block; transition: all 0.2s;
  }
  .btn-white:hover { transform: translateY(-2px); box-shadow: 0 6px 20px rgba(0,0,0,0.15); }

  /* PARTNERS PAGE */
  .partners-hero {
    background: linear-gradient(135deg, var(--blue) 0%, #7c3aed 100%);
    padding: 80px 40px; text-align: center; color: white;
  }
  .partners-hero h1 { font-family: 'Sora', sans-serif; font-size: 48px; font-weight: 700; margin-bottom: 16px; }
  .partners-hero p { font-size: 18px; opacity: 0.85; margin-bottom: 8px; }
  .features-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 40px; }
  .feature-card {
    background: white; border: 1px solid var(--gray-200); border-radius: 14px;
    padding: 24px; display: flex; gap: 16px; align-items: flex-start;
  }
  .feature-icon {
    width: 44px; height: 44px; border-radius: 10px;
    background: #eff6ff; display: flex; align-items: center; justify-content: center;
    font-size: 20px; flex-shrink: 0;
  }
  .feature-card h3 { font-size: 15px; font-weight: 700; margin-bottom: 6px; }
  .feature-card p { font-size: 13px; color: var(--gray-600); line-height: 1.5; }

  /* FORM */
  .form-section { max-width: 700px; margin: 0 auto; padding: 60px 40px; }
  .form-section h2 { font-family: 'Sora', sans-serif; font-size: 32px; font-weight: 700; margin-bottom: 8px; text-align: center; }
  .form-section p.sub { text-align: center; color: var(--gray-600); margin-bottom: 36px; }
  .form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  .form-group { display: flex; flex-direction: column; gap: 6px; }
  .form-group.full { grid-column: 1 / -1; }
  .form-group label { font-size: 13px; font-weight: 600; color: var(--gray-800); }
  .form-group input, .form-group select, .form-group textarea {
    border: 1px solid var(--gray-200); border-radius: 8px; padding: 10px 14px;
    font-size: 14px; font-family: inherit; outline: none; transition: border 0.2s;
    background: var(--gray-50);
  }
  .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
    border-color: var(--blue); background: white;
  }
  .form-group textarea { min-height: 120px; resize: vertical; }
  .btn-submit {
    width: 100%; background: var(--blue); color: white;
    border: none; padding: 13px; border-radius: 8px;
    font-size: 15px; font-weight: 700; cursor: pointer; margin-top: 16px;
    transition: background 0.2s;
  }
  .btn-submit:hover { background: var(--blue-dark); }

  /* CONTACT PAGE */
  .contact-hero {
    background: linear-gradient(135deg, #ea580c 0%, #dc2626 40%, var(--blue-dark) 100%);
    padding: 70px 40px; text-align: center; color: white;
  }
  .contact-hero h1 { font-family: 'Sora', sans-serif; font-size: 44px; font-weight: 700; margin-bottom: 14px; }
  .contact-hero p { font-size: 17px; opacity: 0.85; }
  .contact-cards { display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px; max-width: 900px; margin: -30px auto 0; padding: 0 40px; }
  .contact-card {
    background: white; border-radius: 14px; padding: 28px 20px; text-align: center;
    box-shadow: 0 4px 20px rgba(0,0,0,0.1);
  }
  .contact-card-icon { font-size: 28px; margin-bottom: 10px; }
  .contact-card-label { font-size: 11px; font-weight: 600; text-transform: uppercase; color: var(--gray-400); letter-spacing: 1px; margin-bottom: 6px; }
  .contact-card-value { font-size: 15px; font-weight: 700; color: var(--gray-800); }
  .contact-content { display: grid; grid-template-columns: 1fr 1fr; gap: 40px; max-width: 1000px; margin: 60px auto; padding: 0 40px; }
  .contact-info h3 { font-size: 20px; font-weight: 700; margin-bottom: 8px; }
  .contact-info p { font-size: 14px; color: var(--gray-600); line-height: 1.6; margin-bottom: 20px; }
  .contact-info h4 { font-size: 15px; font-weight: 700; margin-bottom: 10px; }
  .social-links { display: flex; gap: 10px; }
  .social-btn {
    width: 38px; height: 38px; border-radius: 8px; border: 1px solid var(--gray-200);
    display: flex; align-items: center; justify-content: center; font-size: 16px;
    cursor: pointer; text-decoration: none; transition: all 0.2s; color: var(--gray-600);
  }
  .social-btn:hover { background: var(--blue); color: white; border-color: var(--blue); }
  .hours-box {
    background: var(--gray-50); border-radius: 10px; padding: 16px; margin-top: 20px;
    border: 1px solid var(--gray-200);
  }
  .hours-box h4 { font-size: 14px; font-weight: 700; margin-bottom: 8px; }
  .hours-box p { font-size: 13px; color: var(--gray-600); line-height: 1.6; }

  /* FOOTER */
  footer {
    background: var(--gray-50); border-top: 1px solid var(--gray-200);
    padding: 48px 40px 24px;
  }
  .footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr 1fr; gap: 40px; max-width: 1200px; margin: 0 auto 40px; }
  .footer-brand p { font-size: 13px; color: var(--gray-600); line-height: 1.6; margin-top: 10px; }
  .footer-col h4 { font-size: 13px; font-weight: 700; text-transform: uppercase; letter-spacing: 0.5px; color: var(--gray-800); margin-bottom: 14px; }
  .footer-col a { display: block; font-size: 13px; color: var(--gray-600); text-decoration: none; margin-bottom: 8px; transition: color 0.2s; }
  .footer-col a:hover { color: var(--blue); }
  .footer-contact p { font-size: 13px; color: var(--gray-600); margin-bottom: 6px; display: flex; align-items: center; gap: 6px; }
  .footer-bottom { max-width: 1200px; margin: 0 auto; padding-top: 20px; border-top: 1px solid var(--gray-200); display: flex; justify-content: space-between; align-items: center; }
  .footer-bottom p { font-size: 12px; color: var(--gray-400); }
  .footer-bottom-links { display: flex; gap: 16px; }
  .footer-bottom-links a { font-size: 12px; color: var(--gray-400); text-decoration: none; }
  .footer-bottom-links a:hover { color: var(--blue); }

  /* VIEW ALL */
  .view-all-wrap { text-align: center; margin-top: 40px; }
  .btn-outline {
    border: 1px solid var(--blue); color: var(--blue); background: white;
    padding: 10px 24px; border-radius: 8px; font-size: 14px; font-weight: 600;
    cursor: pointer; text-decoration: none; display: inline-flex; align-items: center; gap: 6px;
    transition: all 0.2s;
  }
  .btn-outline:hover { background: var(--blue); color: white; }

  /* BLOG SEARCH */
  .blog-search {
    position: relative; max-width: 400px; margin-bottom: 24px;
  }
  .blog-search input {
    width: 100%; padding: 10px 16px 10px 40px; border: 1px solid var(--gray-200);
    border-radius: 8px; font-size: 14px; font-family: inherit; outline: none;
    transition: border 0.2s;
  }
  .blog-search input:focus { border-color: var(--blue); }
  .blog-search svg { position: absolute; left: 12px; top: 50%; transform: translateY(-50%); }

  @media (max-width: 768px) {
    nav { padding: 0 16px; }
    .nav-links { display: none; }
    .hero { padding: 40px 20px; }
    .hero h1 { font-size: 32px; }
    section { padding: 40px 20px; }
    .features-grid, .form-grid, .contact-content, .contact-cards { grid-template-columns: 1fr; }
    .footer-grid { grid-template-columns: 1fr 1fr; }
    .cta-section { margin: 0 20px 40px; padding: 40px 24px; }
    .contact-cards { padding: 0 20px; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#" onclick="showPage('home')">
    <svg viewBox="0 0 32 32" fill="none" xmlns="http://www.w3.org/2000/svg">
      <rect width="32" height="32" rx="8" fill="#2563EB"/>
      <path d="M8 12h16M8 16h10M8 20h12" stroke="white" stroke-width="2.5" stroke-linecap="round"/>
      <circle cx="22" cy="20" r="3" fill="#f97316"/>
    </svg>
    Shekss
  </a>
  <div class="nav-links">
    <a href="#" class="active" id="nav-home" onclick="showPage('home')">Home</a>
    <a href="#" id="nav-deals" onclick="showPage('deals')">Deals</a>
    <a href="#" id="nav-blog" onclick="showPage('blog')">Blog</a>
    <a href="#" id="nav-partners" onclick="showPage('partners')">Partners</a>
    <a href="#" id="nav-contact" onclick="showPage('contact')">Contact</a>
  </div>
  <a href="#" class="btn-explore" onclick="showPage('deals')">Explore Deals</a>
</nav>

<!-- ========== HOME PAGE ========== -->
<div id="page-home" class="page active">

  <!-- Hero -->
  <div class="hero">
    <div class="hero-bg"></div>
    <div class="hero-overlay"></div>
    <div class="hero-content">
      <div class="hero-badge">Your trusted deals platform</div>
      <h1>Finding the best deals in Egypt with Shekss</h1>
      <p>Discover exclusive discounts from top Egyptian merchants and stay updated with the latest lifestyle content</p>
      <div class="hero-btns">
        <a href="#" class="btn-primary" onclick="showPage('deals')">Explore Deals Now →</a>
        <a href="#" class="btn-secondary" onclick="showPage('blog')">Browse Content</a>
      </div>
    </div>
  </div>

  <!-- Featured Deals -->
  <section>
    <div class="section-label">HOT DEALS</div>
    <h2 class="section-title">Today's best offers</h2>
    <p class="section-sub">Exclusive discounts from Egypt's top merchants</p>
    <div class="deals-grid">
      <div class="deal-card">
        <div class="deal-img">
          <img src="https://images.unsplash.com/photo-1441986300917-64674bd600d8?w=400" alt="Carrefour">
          <span class="hot-badge">HOT DEAL</span>
          <span class="discount-badge">35%</span>
        </div>
        <div class="deal-body">
          <div class="deal-cat">FOOD</div>
          <div class="deal-name">Carrefour Egypt</div>
          <div class="deal-desc">Save big on groceries and household essentials this week</div>
          <div class="deal-timer">⏱ 0h 59m 56s</div>
          <button class="btn-claim">Claim Deal →</button>
        </div>
      </div>
      <div class="deal-card">
        <div class="deal-img">
          <img src="https://images.unsplash.com/photo-1498049794561-7780e7231661?w=400" alt="Jumia">
          <span class="hot-badge">HOT DEAL</span>
          <span class="discount-badge">47%</span>
        </div>
        <div class="deal-body">
          <div class="deal-cat">TECH</div>
          <div class="deal-name">Jumia Egypt</div>
          <div class="deal-desc">Electronics flash sale – smartphones, laptops and accessories</div>
          <div class="deal-timer">⏱ 04h 59m 56s</div>
          <button class="btn-claim">Claim Deal →</button>
        </div>
      </div>
      <div class="deal-card">
        <div class="deal-img">
          <img src="https://images.unsplash.com/photo-1543087903-1ac2364bdc3b?w=400" alt="Cottonil">
          <span class="discount-badge">23%</span>
        </div>
        <div class="deal-body">
          <div class="deal-cat">FASHION</div>
          <div class="deal-name">Cottonil</div>
          <div class="deal-desc">Premium cotton clothing for the whole family</div>
          <div class="deal-timer">⏱ 23h 59m 56s</div>
          <button class="btn-claim">Claim Deal →</button>
        </div>
      </
