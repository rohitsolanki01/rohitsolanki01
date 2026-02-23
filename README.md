<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ROHIT SOLANKI // FULL STACK ARCHITECT</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Share+Tech+Mono&family=Exo+2:wght@300;400;600;800&display=swap" rel="stylesheet">
<style>
  :root {
    --neon: #00ffe7;
    --neon2: #b400ff;
    --neon3: #ff2d78;
    --bg: #020610;
    --bg2: #060d1f;
    --grid: rgba(0,255,231,0.04);
    --text: #c8e8f0;
    --dim: rgba(0,255,231,0.4);
    --glow: 0 0 20px rgba(0,255,231,0.5), 0 0 60px rgba(0,255,231,0.2);
    --glow2: 0 0 20px rgba(180,0,255,0.5), 0 0 60px rgba(180,0,255,0.2);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'Exo 2', sans-serif;
    background: var(--bg);
    color: var(--text);
    overflow-x: hidden;
    cursor: crosshair;
  }

  /* GRID BACKGROUND */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(var(--grid) 1px, transparent 1px),
      linear-gradient(90deg, var(--grid) 1px, transparent 1px);
    background-size: 50px 50px;
    pointer-events: none;
    z-index: 0;
  }

  /* SCAN LINE */
  body::after {
    content: '';
    position: fixed;
    top: -100%;
    left: 0;
    right: 0;
    height: 200px;
    background: linear-gradient(transparent, rgba(0,255,231,0.03), transparent);
    animation: scanline 8s linear infinite;
    pointer-events: none;
    z-index: 1;
  }

  @keyframes scanline {
    to { top: 100%; }
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 24px;
    position: relative;
    z-index: 2;
  }

  /* ============ HERO ============ */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 60px 24px;
    position: relative;
    overflow: hidden;
  }

  .hero-orb {
    position: absolute;
    width: 600px;
    height: 600px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(0,255,231,0.07) 0%, transparent 70%);
    animation: pulse-orb 4s ease-in-out infinite;
    pointer-events: none;
  }
  .hero-orb-2 {
    width: 400px;
    height: 400px;
    background: radial-gradient(circle, rgba(180,0,255,0.06) 0%, transparent 70%);
    animation: pulse-orb 6s ease-in-out infinite reverse;
  }

  @keyframes pulse-orb {
    0%, 100% { transform: scale(1); opacity: 0.7; }
    50% { transform: scale(1.2); opacity: 1; }
  }

  .status-bar {
    display: flex;
    gap: 12px;
    align-items: center;
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: var(--dim);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 40px;
    animation: fadedown 1s ease both;
  }

  .status-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--neon);
    box-shadow: var(--glow);
    animation: blink 1.5s ease infinite;
  }

  @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0.2; } }

  .hero-name {
    font-family: 'Orbitron', monospace;
    font-size: clamp(48px, 8vw, 96px);
    font-weight: 900;
    line-height: 0.9;
    letter-spacing: -2px;
    background: linear-gradient(135deg, #fff 0%, var(--neon) 50%, var(--neon2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: fadedown 1s 0.2s ease both;
    position: relative;
  }

  .hero-name::after {
    content: attr(data-text);
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, #fff 0%, var(--neon) 50%, var(--neon2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    filter: blur(20px);
    opacity: 0.4;
    z-index: -1;
  }

  .hero-title {
    font-family: 'Share Tech Mono', monospace;
    font-size: clamp(12px, 2vw, 16px);
    color: var(--neon);
    letter-spacing: 6px;
    text-transform: uppercase;
    margin: 20px 0 40px;
    animation: fadedown 1s 0.4s ease both;
  }

  .hero-title span { color: var(--neon2); }

  .hero-badges {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
    justify-content: center;
    margin-bottom: 50px;
    animation: fadedown 1s 0.6s ease both;
  }

  .badge {
    padding: 8px 20px;
    border: 1px solid rgba(0,255,231,0.3);
    border-radius: 2px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    letter-spacing: 2px;
    color: var(--neon);
    background: rgba(0,255,231,0.05);
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
    text-decoration: none;
  }

  .badge::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(90deg, transparent, rgba(0,255,231,0.1), transparent);
    transform: translateX(-100%);
    transition: transform 0.5s;
  }

  .badge:hover::before { transform: translateX(100%); }
  .badge:hover {
    border-color: var(--neon);
    box-shadow: var(--glow);
    background: rgba(0,255,231,0.1);
  }

  .badge-purple {
    border-color: rgba(180,0,255,0.3);
    color: var(--neon2);
    background: rgba(180,0,255,0.05);
  }
  .badge-purple:hover { border-color: var(--neon2); box-shadow: var(--glow2); }

  .hero-stats {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
    background: rgba(0,255,231,0.1);
    border: 1px solid rgba(0,255,231,0.15);
    width: 100%;
    max-width: 700px;
    animation: fadedown 1s 0.8s ease both;
  }

  .stat-cell {
    background: var(--bg2);
    padding: 20px;
    text-align: center;
    transition: background 0.3s;
  }
  .stat-cell:hover { background: rgba(0,255,231,0.05); }

  .stat-num {
    font-family: 'Orbitron', monospace;
    font-size: 28px;
    font-weight: 700;
    color: var(--neon);
    display: block;
    text-shadow: var(--glow);
  }

  .stat-label {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    color: rgba(200,232,240,0.5);
    margin-top: 4px;
    display: block;
  }

  @keyframes fadedown {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* ============ SECTIONS ============ */
  section {
    padding: 100px 0;
    position: relative;
    z-index: 2;
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: 20px;
    margin-bottom: 60px;
  }

  .section-tag {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    letter-spacing: 4px;
    color: var(--neon);
    background: rgba(0,255,231,0.08);
    border: 1px solid rgba(0,255,231,0.2);
    padding: 6px 14px;
    text-transform: uppercase;
  }

  .section-title {
    font-family: 'Orbitron', monospace;
    font-size: clamp(24px, 4vw, 40px);
    font-weight: 900;
    color: #fff;
    letter-spacing: -1px;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, rgba(0,255,231,0.3), transparent);
  }

  /* ============ TECH GRID ============ */
  .tech-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
    gap: 2px;
    background: rgba(0,255,231,0.06);
    border: 1px solid rgba(0,255,231,0.1);
  }

  .tech-item {
    background: var(--bg2);
    padding: 20px 16px;
    text-align: center;
    transition: all 0.3s;
    cursor: default;
    position: relative;
    overflow: hidden;
  }

  .tech-item::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 2px;
    background: var(--neon);
    transform: scaleX(0);
    transition: transform 0.3s;
    transform-origin: left;
  }

  .tech-item:hover {
    background: rgba(0,255,231,0.07);
    transform: translateY(-2px);
  }

  .tech-item:hover::after { transform: scaleX(1); }

  .tech-icon {
    font-size: 24px;
    margin-bottom: 8px;
    display: block;
  }

  .tech-name {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    letter-spacing: 1px;
    color: var(--text);
  }

  .tech-category {
    font-size: 9px;
    color: var(--neon);
    opacity: 0.6;
    letter-spacing: 2px;
    margin-top: 3px;
    display: block;
  }

  /* ============ PROJECTS ============ */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(500px, 1fr));
    gap: 2px;
  }

  .project-card {
    background: var(--bg2);
    border: 1px solid rgba(0,255,231,0.1);
    padding: 40px;
    position: relative;
    overflow: hidden;
    transition: all 0.4s;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--neon), var(--neon2));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.5s;
  }

  .project-card:hover { border-color: rgba(0,255,231,0.3); }
  .project-card:hover::before { transform: scaleX(1); }

  .project-number {
    font-family: 'Orbitron', monospace;
    font-size: 60px;
    font-weight: 900;
    color: rgba(0,255,231,0.06);
    position: absolute;
    top: 20px;
    right: 30px;
    line-height: 1;
    pointer-events: none;
  }

  .project-status {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    letter-spacing: 3px;
    color: var(--neon);
    margin-bottom: 16px;
  }

  .project-name {
    font-family: 'Orbitron', monospace;
    font-size: 22px;
    font-weight: 700;
    color: #fff;
    margin-bottom: 8px;
    letter-spacing: 1px;
  }

  .project-sub {
    font-size: 12px;
    color: rgba(200,232,240,0.5);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 20px;
    font-family: 'Share Tech Mono', monospace;
  }

  .project-desc {
    font-size: 14px;
    line-height: 1.8;
    color: rgba(200,232,240,0.7);
    margin-bottom: 24px;
  }

  .project-metrics {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: rgba(0,255,231,0.08);
    margin-bottom: 24px;
  }

  .metric {
    background: var(--bg);
    padding: 12px;
    text-align: center;
  }

  .metric-val {
    font-family: 'Orbitron', monospace;
    font-size: 18px;
    font-weight: 700;
    color: var(--neon);
    display: block;
  }

  .metric-key {
    font-family: 'Share Tech Mono', monospace;
    font-size: 9px;
    color: rgba(200,232,240,0.4);
    letter-spacing: 2px;
    display: block;
    margin-top: 2px;
  }

  .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 24px;
  }

  .tag {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    padding: 4px 10px;
    border: 1px solid rgba(180,0,255,0.3);
    color: var(--neon2);
    letter-spacing: 1px;
    background: rgba(180,0,255,0.05);
  }

  .project-links {
    display: flex;
    gap: 12px;
  }

  .project-link {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    letter-spacing: 2px;
    text-decoration: none;
    padding: 10px 20px;
    border: 1px solid rgba(0,255,231,0.3);
    color: var(--neon);
    transition: all 0.3s;
    text-transform: uppercase;
  }

  .project-link:hover {
    background: rgba(0,255,231,0.1);
    box-shadow: var(--glow);
  }

  .project-link-2 {
    border-color: rgba(180,0,255,0.3);
    color: var(--neon2);
  }

  .project-link-2:hover {
    background: rgba(180,0,255,0.1);
    box-shadow: var(--glow2);
  }

  /* ============ EXPERIENCE ============ */
  .exp-card {
    background: var(--bg2);
    border: 1px solid rgba(0,255,231,0.1);
    padding: 50px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 50px;
    position: relative;
    overflow: hidden;
  }

  .exp-card::before {
    content: '';
    position: absolute;
    left: 0;
    top: 0;
    bottom: 0;
    width: 3px;
    background: linear-gradient(180deg, var(--neon), var(--neon2), var(--neon3));
  }

  .exp-role {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    letter-spacing: 4px;
    color: var(--neon);
    margin-bottom: 8px;
  }

  .exp-company {
    font-family: 'Orbitron', monospace;
    font-size: 32px;
    font-weight: 900;
    color: #fff;
    margin-bottom: 6px;
  }

  .exp-duration {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: rgba(200,232,240,0.4);
    letter-spacing: 2px;
    margin-bottom: 24px;
  }

  .exp-achievements {
    list-style: none;
  }

  .exp-achievements li {
    font-size: 13px;
    color: rgba(200,232,240,0.7);
    line-height: 1.8;
    padding: 6px 0;
    border-bottom: 1px solid rgba(0,255,231,0.05);
    padding-left: 18px;
    position: relative;
  }

  .exp-achievements li::before {
    content: '▸';
    position: absolute;
    left: 0;
    color: var(--neon);
    font-size: 12px;
  }

  .exp-stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
    align-content: start;
    background: rgba(0,255,231,0.06);
  }

  .exp-stat {
    background: var(--bg);
    padding: 24px;
    text-align: center;
  }

  .exp-stat-num {
    font-family: 'Orbitron', monospace;
    font-size: 36px;
    font-weight: 900;
    color: var(--neon);
    display: block;
    text-shadow: var(--glow);
  }

  .exp-stat-label {
    font-family: 'Share Tech Mono', monospace;
    font-size: 9px;
    letter-spacing: 2px;
    color: rgba(200,232,240,0.4);
    margin-top: 4px;
    display: block;
  }

  /* ============ SKILLS BAR ============ */
  .skills-list {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px 60px;
  }

  .skill-row {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .skill-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .skill-name {
    font-family: 'Share Tech Mono', monospace;
    font-size: 12px;
    letter-spacing: 2px;
    color: var(--text);
    text-transform: uppercase;
  }

  .skill-pct {
    font-family: 'Orbitron', monospace;
    font-size: 12px;
    font-weight: 700;
    color: var(--neon);
  }

  .skill-bar {
    height: 2px;
    background: rgba(0,255,231,0.1);
    position: relative;
    overflow: hidden;
  }

  .skill-fill {
    height: 100%;
    background: linear-gradient(90deg, var(--neon), var(--neon2));
    position: relative;
    animation: fill-bar 2s cubic-bezier(0.4, 0, 0.2, 1) both;
    transform-origin: left;
  }

  .skill-fill::after {
    content: '';
    position: absolute;
    right: 0;
    top: -3px;
    width: 6px;
    height: 8px;
    background: var(--neon);
    box-shadow: var(--glow);
  }

  @keyframes fill-bar {
    from { transform: scaleX(0); }
    to { transform: scaleX(1); }
  }

  /* ============ CONTACT ============ */
  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
    background: rgba(0,255,231,0.06);
  }

  .contact-card {
    background: var(--bg2);
    padding: 40px;
    transition: all 0.3s;
    text-decoration: none;
    display: block;
    position: relative;
    overflow: hidden;
  }

  .contact-card::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(0,255,231,0.05), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .contact-card:hover::after { opacity: 1; }

  .contact-icon {
    font-size: 32px;
    margin-bottom: 16px;
    display: block;
  }

  .contact-platform {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    letter-spacing: 4px;
    color: var(--neon);
    margin-bottom: 6px;
  }

  .contact-value {
    font-family: 'Exo 2', sans-serif;
    font-size: 16px;
    font-weight: 600;
    color: #fff;
  }

  .contact-arrow {
    position: absolute;
    bottom: 24px;
    right: 24px;
    font-size: 20px;
    color: rgba(0,255,231,0.3);
    transition: all 0.3s;
  }

  .contact-card:hover .contact-arrow {
    color: var(--neon);
    transform: translate(4px, -4px);
  }

  /* ============ FOOTER ============ */
  footer {
    border-top: 1px solid rgba(0,255,231,0.1);
    padding: 40px 0;
    position: relative;
    z-index: 2;
  }

  .footer-inner {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: gap;
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: rgba(200,232,240,0.3);
    letter-spacing: 2px;
  }

  .footer-logo {
    font-family: 'Orbitron', monospace;
    font-size: 18px;
    font-weight: 900;
    color: var(--neon);
    text-shadow: var(--glow);
  }

  /* ============ RESPONSIVE ============ */
  @media (max-width: 768px) {
    .hero-stats { grid-template-columns: repeat(2, 1fr); }
    .projects-grid { grid-template-columns: 1fr; }
    .exp-card { grid-template-columns: 1fr; }
    .skills-list { grid-template-columns: 1fr; }
    .contact-grid { grid-template-columns: 1fr; }
    .footer-inner { flex-direction: column; gap: 16px; text-align: center; }
  }

  /* ============ SCROLL REVEAL ============ */
  .reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
  }
  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* CORNER DECORATIONS */
  .corner-deco {
    position: absolute;
    width: 20px;
    height: 20px;
  }
  .corner-tl { top: 0; left: 0; border-top: 1px solid var(--neon); border-left: 1px solid var(--neon); }
  .corner-tr { top: 0; right: 0; border-top: 1px solid var(--neon); border-right: 1px solid var(--neon); }
  .corner-bl { bottom: 0; left: 0; border-bottom: 1px solid var(--neon); border-left: 1px solid var(--neon); }
  .corner-br { bottom: 0; right: 0; border-bottom: 1px solid var(--neon); border-right: 1px solid var(--neon); }
</style>
</head>
<body>

<!-- ═══════════ HERO ═══════════ -->
<section class="hero">
  <div class="hero-orb"></div>
  <div class="hero-orb hero-orb-2"></div>

  <div class="status-bar">
    <span class="status-dot"></span>
    <span>SYSTEM.ONLINE</span>
    <span style="opacity:0.3">|</span>
    <span>AHMEDABAD_IN // UTC+5:30</span>
    <span style="opacity:0.3">|</span>
    <span>BUILD v2.5.0_STABLE</span>
  </div>

  <h1 class="hero-name" data-text="ROHIT SOLANKI">ROHIT SOLANKI</h1>
  <p class="hero-title">Full Stack <span>//</span> MERN Architect <span>//</span> Code Ninja</p>

  <div class="hero-badges">
    <a href="https://idyllic-daffodil-128731.netlify.app/" class="badge">⚡ PORTFOLIO.EXE</a>
    <a href="https://www.linkedin.com/in/rohit-solanki-495860348/" class="badge">🔗 LINKEDIN.NET</a>
    <a href="mailto:rohitsolanki0473@gmail.com" class="badge">📡 CONTACT.SYS</a>
    <a href="https://github.com/rohitsolanki01" class="badge badge-purple">💾 GITHUB.REPO</a>
    <a href="https://x.com/Rohit_01_tech" class="badge badge-purple">🐦 TWITTER.API</a>
  </div>

  <div class="hero-stats">
    <div class="stat-cell">
      <span class="stat-num">500+</span>
      <span class="stat-label">USERS SERVED</span>
    </div>
    <div class="stat-cell">
      <span class="stat-num">99.5%</span>
      <span class="stat-label">UPTIME</span>
    </div>
    <div class="stat-cell">
      <span class="stat-num">40%</span>
      <span class="stat-label">PERF GAIN</span>
    </div>
    <div class="stat-cell">
      <span class="stat-num">95/100</span>
      <span class="stat-label">LIGHTHOUSE</span>
    </div>
  </div>
</section>

<!-- ═══════════ TECH STACK ═══════════ -->
<section>
  <div class="container">
    <div class="section-header reveal">
      <span class="section-tag">ls -la /skills/</span>
      <h2 class="section-title">TECH STACK</h2>
      <div class="section-line"></div>
    </div>

    <div class="tech-grid reveal">
      <div class="tech-item"><span class="tech-icon">⚛️</span><span class="tech-name">React.js</span><span class="tech-category">FRONTEND</span></div>
      <div class="tech-item"><span class="tech-icon">⚡</span><span class="tech-name">Next.js 15</span><span class="tech-category">FRONTEND</span></div>
      <div class="tech-item"><span class="tech-icon">📘</span><span class="tech-name">TypeScript</span><span class="tech-category">LANGUAGE</span></div>
      <div class="tech-item"><span class="tech-icon">🟡</span><span class="tech-name">JavaScript</span><span class="tech-category">LANGUAGE</span></div>
      <div class="tech-item"><span class="tech-icon">🎨</span><span class="tech-name">Tailwind</span><span class="tech-category">STYLING</span></div>
      <div class="tech-item"><span class="tech-icon">🔄</span><span class="tech-name">Redux</span><span class="tech-category">STATE</span></div>
      <div class="tech-item"><span class="tech-icon">🟢</span><span class="tech-name">Node.js</span><span class="tech-category">BACKEND</span></div>
      <div class="tech-item"><span class="tech-icon">🚂</span><span class="tech-name">Express.js</span><span class="tech-category">BACKEND</span></div>
      <div class="tech-item"><span class="tech-icon">🍃</span><span class="tech-name">MongoDB</span><span class="tech-category">DATABASE</span></div>
      <div class="tech-item"><span class="tech-icon">🐘</span><span class="tech-name">PostgreSQL</span><span class="tech-category">DATABASE</span></div>
      <div class="tech-item"><span class="tech-icon">⚡</span><span class="tech-name">Redis</span><span class="tech-category">CACHE</span></div>
      <div class="tech-item"><span class="tech-icon">☁️</span><span class="tech-name">AWS</span><span class="tech-category">CLOUD</span></div>
      <div class="tech-item"><span class="tech-icon">🐳</span><span class="tech-name">Docker</span><span class="tech-category">DEVOPS</span></div>
      <div class="tech-item"><span class="tech-icon">☸️</span><span class="tech-name">Kubernetes</span><span class="tech-category">DEVOPS</span></div>
      <div class="tech-item"><span class="tech-icon">🔐</span><span class="tech-name">JWT/OAuth</span><span class="tech-category">SECURITY</span></div>
      <div class="tech-item"><span class="tech-icon">📊</span><span class="tech-name">GraphQL</span><span class="tech-category">API</span></div>
    </div>
  </div>
</section>

<!-- ═══════════ SKILL BARS ═══════════ -->
<section>
  <div class="container">
    <div class="section-header reveal">
      <span class="section-tag">./run_diagnostics.sh</span>
      <h2 class="section-title">PROFICIENCY</h2>
      <div class="section-line"></div>
    </div>
    <div class="skills-list reveal">
      <div class="skill-row">
        <div class="skill-header"><span class="skill-name">React / Next.js</span><span class="skill-pct">95%</span></div>
        <div class="skill-bar"><div class="skill-fill" style="width:95%"></div></div>
      </div>
      <div class="skill-row">
        <div class="skill-header"><span class="skill-name">Node / Express</span><span class="skill-pct">90%</span></div>
        <div class="skill-bar"><div class="skill-fill" style="width:90%"></div></div>
      </div>
      <div class="skill-row">
        <div class="skill-header"><span class="skill-name">MongoDB / Mongoose</span><span class="skill-pct">92%</span></div>
        <div class="skill-bar"><div class="skill-fill" style="width:92%"></div></div>
      </div>
      <div class="skill-row">
        <div class="skill-header"><span class="skill-name">TypeScript</span><span class="skill-pct">85%</span></div>
        <div class="skill-bar"><div class="skill-fill" style="width:85%"></div></div>
      </div>
      <div class="skill-row">
        <div class="skill-header"><span class="skill-name">AWS / Cloud Infra</span><span class="skill-pct">78%</span></div>
        <div class="skill-bar"><div class="skill-fill" style="width:78%"></div></div>
      </div>
      <div class="skill-row">
        <div class="skill-header"><span class="skill-name">Docker / DevOps</span><span class="skill-pct">75%</span></div>
        <div class="skill-bar"><div class="skill-fill" style="width:75%"></div></div>
      </div>
      <div class="skill-row">
        <div class="skill-header"><span class="skill-name">PostgreSQL / Redis</span><span class="skill-pct">80%</span></div>
        <div class="skill-bar"><div class="skill-fill" style="width:80%"></div></div>
      </div>
      <div class="skill-row">
        <div class="skill-header"><span class="skill-name">System Design</span><span class="skill-pct">72%</span></div>
        <div class="skill-bar"><div class="skill-fill" style="width:72%"></div></div>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════ PROJECTS ═══════════ -->
<section>
  <div class="container">
    <div class="section-header reveal">
      <span class="section-tag">cat /projects/production/*</span>
      <h2 class="section-title">PROJECTS</h2>
      <div class="section-line"></div>
    </div>

    <div class="projects-grid">
      <!-- PROJECT 001 -->
      <div class="project-card reveal" style="position:relative">
        <span class="project-number">001</span>
        <span class="project-status"><span class="status-dot"></span>DEPLOYED // PRODUCTION</span>
        <h3 class="project-name">TRANQUVEST</h3>
        <p class="project-sub">Stock Trading & Investment Platform</p>
        <p class="project-desc">Real-time portfolio tracking platform with interactive candlestick charts, Redis-accelerated API layer, and enterprise-grade JWT authentication. Serving 100+ active traders with zero security incidents.</p>
        <div class="project-metrics">
          <div class="metric"><span class="metric-val">100+</span><span class="metric-key">TRADERS</span></div>
          <div class="metric"><span class="metric-val">35%</span><span class="metric-key">FASTER API</span></div>
          <div class="metric"><span class="metric-val">95</span><span class="metric-key">LIGHTHOUSE</span></div>
        </div>
        <div class="project-tags">
          <span class="tag">React.js</span>
          <span class="tag">Redux</span>
          <span class="tag">Node.js</span>
          <span class="tag">MongoDB</span>
          <span class="tag">Redis</span>
          <span class="tag">Chart.js</span>
          <span class="tag">JWT</span>
        </div>
        <div class="project-links">
          <a href="https://treding-app-tranquvest.vercel.app/" class="project-link">⚡ LIVE DEMO</a>
          <a href="https://github.com/rohitsolanki01/Treding---app---Tranquvest" class="project-link project-link-2">💾 SOURCE</a>
        </div>
      </div>

      <!-- PROJECT 002 -->
      <div class="project-card reveal" style="position:relative">
        <span class="project-number">002</span>
        <span class="project-status"><span class="status-dot"></span>PRODUCTION // LIVE</span>
        <h3 class="project-name">NESTIGO</h3>
        <p class="project-sub">Property Rental Marketplace</p>
        <p class="project-desc">Full-featured rental marketplace with advanced geospatial search via Geoapify, Cloudinary CDN, role-based access for landlords/tenants, and real-time review system. Handles 1000+ concurrent users.</p>
        <div class="project-metrics">
          <div class="metric"><span class="metric-val">200+</span><span class="metric-key">LISTINGS</span></div>
          <div class="metric"><span class="metric-val">50%</span><span class="metric-key">FASTER LOADS</span></div>
          <div class="metric"><span class="metric-val">99.5%</span><span class="metric-key">UPTIME</span></div>
        </div>
        <div class="project-tags">
          <span class="tag">Node.js</span>
          <span class="tag">Express</span>
          <span class="tag">MongoDB</span>
          <span class="tag">Cloudinary</span>
          <span class="tag">Passport.js</span>
          <span class="tag">Geoapify</span>
        </div>
        <div class="project-links">
          <a href="https://nestigo-elhe.onrender.com/" class="project-link">⚡ LIVE DEMO</a>
          <a href="https://github.com/rohitsolanki01/Nestigo" class="project-link project-link-2">💾 SOURCE</a>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════ EXPERIENCE ═══════════ -->
<section>
  <div class="container">
    <div class="section-header reveal">
      <span class="section-tag">ps aux | grep EXPERIENCE</span>
      <h2 class="section-title">EXPERIENCE</h2>
      <div class="section-line"></div>
    </div>

    <div class="exp-card reveal">
      <div class="corner-deco corner-tl"></div>
      <div class="corner-deco corner-tr"></div>
      <div class="corner-deco corner-bl"></div>
      <div class="corner-deco corner-br"></div>
      <div>
        <p class="exp-role">▸ FULLSTACK DEVELOPER INTERN</p>
        <h3 class="exp-company">CODEC TECH</h3>
        <p class="exp-duration">DEC 2024 → FEB 2025 // REMOTE</p>
        <ul class="exp-achievements">
          <li>Architected 3 production MERN apps serving 500+ users with 99.5% uptime</li>
          <li>Implemented OWASP security standards — zero breaches across all deployments</li>
          <li>Optimized DB queries with aggregation pipelines achieving +40% performance gain</li>
          <li>Integrated payment gateways (Stripe, Razorpay) & map APIs</li>
          <li>Built responsive React components scoring 95+ on Lighthouse</li>
          <li>Configured CI/CD pipelines; deployed to AWS EC2, Vercel, Render</li>
          <li>Maintained 87%+ code coverage with Jest; documented APIs via Swagger</li>
        </ul>
      </div>
      <div class="exp-stats-grid">
        <div class="exp-stat">
          <span class="exp-stat-num">3</span>
          <span class="exp-stat-label">APPS BUILT</span>
        </div>
        <div class="exp-stat">
          <span class="exp-stat-num">0</span>
          <span class="exp-stat-label">INCIDENTS</span>
        </div>
        <div class="exp-stat">
          <span class="exp-stat-num">+40%</span>
          <span class="exp-stat-label">PERF BOOST</span>
        </div>
        <div class="exp-stat">
          <span class="exp-stat-num">87%</span>
          <span class="exp-stat-label">CODE COVERAGE</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════ CONTACT ═══════════ -->
<section>
  <div class="container">
    <div class="section-header reveal">
      <span class="section-tag">netstat -an | grep CONTACT</span>
      <h2 class="section-title">CONNECT</h2>
      <div class="section-line"></div>
    </div>

    <div class="contact-grid reveal">
      <a href="mailto:rohitsolanki0473@gmail.com" class="contact-card">
        <span class="contact-icon">📡</span>
        <p class="contact-platform">EMAIL.SYS</p>
        <p class="contact-value">rohitsolanki0473@gmail.com</p>
        <span class="contact-arrow">↗</span>
      </a>
      <a href="https://www.linkedin.com/in/rohit-solanki-495860348/" class="contact-card">
        <span class="contact-icon">🔗</span>
        <p class="contact-platform">LINKEDIN.NET</p>
        <p class="contact-value">rohit-solanki-495860348</p>
        <span class="contact-arrow">↗</span>
      </a>
      <a href="https://github.com/rohitsolanki01" class="contact-card">
        <span class="contact-icon">💾</span>
        <p class="contact-platform">GITHUB.REPO</p>
        <p class="contact-value">github.com/rohitsolanki01</p>
        <span class="contact-arrow">↗</span>
      </a>
      <a href="https://idyllic-daffodil-128731.netlify.app/" class="contact-card">
        <span class="contact-icon">🌐</span>
        <p class="contact-platform">PORTFOLIO.APP</p>
        <p class="contact-value">idyllic-daffodil-128731.netlify.app</p>
        <span class="contact-arrow">↗</span>
      </a>
    </div>

    <div style="text-align:center; margin-top:60px; padding:40px; border:1px solid rgba(0,255,231,0.1); background:var(--bg2); position:relative;" class="reveal">
      <div class="corner-deco corner-tl"></div>
      <div class="corner-deco corner-tr"></div>
      <div class="corner-deco corner-bl"></div>
      <div class="corner-deco corner-br"></div>
      <p style="font-family:'Share Tech Mono',monospace;font-size:10px;letter-spacing:4px;color:var(--neon);margin-bottom:16px;">AVAILABILITY STATUS</p>
      <p style="font-family:'Orbitron',monospace;font-size:28px;font-weight:900;color:#fff;margin-bottom:20px;">OPEN TO WORK</p>
      <div style="display:flex;gap:12px;justify-content:center;flex-wrap:wrap;">
        <span class="badge">FULL-TIME</span>
        <span class="badge">FREELANCE</span>
        <span class="badge">CONTRACT</span>
        <span class="badge badge-purple">REMOTE_READY</span>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════ FOOTER ═══════════ -->
<footer>
  <div class="container">
    <div class="footer-inner">
      <span class="footer-logo">RS.DEV</span>
      <span>BUILD_WITH_PURPOSE_SCALE_WITH_STRATEGY</span>
      <span>© 2025 ROHIT_SOLANKI // v2.5.0</span>
    </div>
  </div>
</footer>

<script>
  // Scroll reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
  }, { threshold: 0.1 });

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

  // Stagger delays for tech grid
  document.querySelectorAll('.tech-item').forEach((el, i) => {
    el.style.animationDelay = `${i * 0.05}s`;
  });

  // Custom cursor glow
  const cursor = document.createElement('div');
  cursor.style.cssText = `
    width:20px;height:20px;border:1px solid rgba(0,255,231,0.6);
    border-radius:50%;position:fixed;pointer-events:none;z-index:9999;
    transition:transform 0.1s;mix-blend-mode:screen;
  `;
  document.body.appendChild(cursor);
  document.addEventListener('mousemove', e => {
    cursor.style.left = e.clientX - 10 + 'px';
    cursor.style.top = e.clientY - 10 + 'px';
  });
  document.addEventListener('mousedown', () => cursor.style.transform = 'scale(2)');
  document.addEventListener('mouseup', () => cursor.style.transform = 'scale(1)');
</script>
</body>
</html>
