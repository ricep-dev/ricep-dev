<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ricep Ardiansyah — Fullstack Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:ital,wght@0,300;0,400;1,300&family=Cabinet+Grotesk:wght@400;500;700;900&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #060912;
    --surface: #0d1425;
    --surface2: #111827;
    --border: rgba(99,179,237,0.12);
    --accent: #38bdf8;
    --accent2: #818cf8;
    --accent3: #34d399;
    --gold: #fbbf24;
    --text: #e2e8f0;
    --muted: #64748b;
    --glow: 0 0 40px rgba(56,189,248,0.15);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── GRID NOISE BACKGROUND ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(99,179,237,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(99,179,237,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(100px);
    pointer-events: none;
    z-index: 0;
    animation: orbFloat 8s ease-in-out infinite;
  }
  .orb-1 { width: 500px; height: 500px; background: rgba(56,189,248,0.06); top: -150px; left: -150px; }
  .orb-2 { width: 400px; height: 400px; background: rgba(129,140,248,0.07); bottom: 10%; right: -100px; animation-delay: -3s; }
  .orb-3 { width: 300px; height: 300px; background: rgba(52,211,153,0.05); top: 40%; left: 40%; animation-delay: -5s; }

  @keyframes orbFloat {
    0%,100% { transform: translateY(0) scale(1); }
    50% { transform: translateY(-30px) scale(1.05); }
  }

  .container {
    position: relative;
    z-index: 1;
    max-width: 900px;
    margin: 0 auto;
    padding: 60px 24px;
  }

  /* ── HERO ── */
  .hero {
    display: grid;
    grid-template-columns: 1fr auto;
    align-items: start;
    gap: 40px;
    margin-bottom: 60px;
    animation: fadeUp 0.8s ease both;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero-tag {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--accent);
    background: rgba(56,189,248,0.08);
    border: 1px solid rgba(56,189,248,0.2);
    padding: 6px 14px;
    border-radius: 100px;
    margin-bottom: 20px;
  }
  .hero-tag::before { content: ''; width: 6px; height: 6px; border-radius: 50%; background: var(--accent); animation: pulse 2s infinite; }

  @keyframes pulse {
    0%,100% { opacity: 1; }
    50% { opacity: 0.3; }
  }

  .hero h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.2rem, 5vw, 3.8rem);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.03em;
    margin-bottom: 8px;
  }

  .hero h1 span {
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-sub {
    font-family: 'DM Mono', monospace;
    font-size: 13px;
    color: var(--muted);
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .hero-sub::before { content: '~/'; color: var(--accent3); }

  .hero-desc {
    font-size: 14px;
    line-height: 1.8;
    color: #94a3b8;
    max-width: 500px;
  }

  .avatar-wrap {
    position: relative;
    flex-shrink: 0;
  }

  .avatar {
    width: 120px;
    height: 120px;
    border-radius: 20px;
    background: linear-gradient(135deg, var(--surface2), var(--surface));
    border: 2px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 48px;
    position: relative;
    overflow: hidden;
  }

  .avatar::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(56,189,248,0.1), transparent 60%);
  }

  .status-dot {
    position: absolute;
    bottom: -4px; right: -4px;
    width: 20px; height: 20px;
    background: var(--accent3);
    border-radius: 50%;
    border: 3px solid var(--bg);
    animation: pulse 2s infinite;
  }

  /* ── SECTION ── */
  section {
    margin-bottom: 48px;
    animation: fadeUp 0.8s ease both;
  }
  section:nth-child(2) { animation-delay: 0.1s; }
  section:nth-child(3) { animation-delay: 0.2s; }
  section:nth-child(4) { animation-delay: 0.3s; }
  section:nth-child(5) { animation-delay: 0.4s; }

  .section-label {
    display: flex;
    align-items: center;
    gap: 12px;
    font-size: 11px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 20px;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── ABOUT CARDS ── */
  .about-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 12px;
  }

  .about-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 16px;
    transition: all 0.25s ease;
    cursor: default;
  }
  .about-card:hover {
    border-color: rgba(56,189,248,0.3);
    transform: translateY(-2px);
    box-shadow: var(--glow);
  }
  .about-card .icon { font-size: 20px; margin-bottom: 10px; }
  .about-card .label { font-size: 10px; letter-spacing: 0.1em; text-transform: uppercase; color: var(--muted); margin-bottom: 4px; }
  .about-card .value { font-size: 13px; color: var(--text); font-family: 'DM Mono', monospace; }

  /* ── TECH STACK ── */
  .stack-group {
    margin-bottom: 20px;
  }
  .stack-title {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    color: var(--accent2);
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .stack-title::before {
    content: '';
    width: 3px; height: 14px;
    background: var(--accent2);
    border-radius: 2px;
  }
  .tech-chips {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  .chip {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 7px 14px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    font-size: 12px;
    color: var(--text);
    transition: all 0.2s ease;
    cursor: default;
  }
  .chip:hover {
    border-color: var(--accent);
    color: var(--accent);
    box-shadow: 0 0 16px rgba(56,189,248,0.1);
    transform: translateY(-1px);
  }
  .chip .dot { width: 6px; height: 6px; border-radius: 50%; }
  .c-react .dot { background: #61dafb; }
  .c-next .dot { background: #fff; }
  .c-flutter .dot { background: #54c5f8; }
  .c-go .dot { background: #00acd7; }
  .c-node .dot { background: #68a063; }
  .c-flask .dot { background: #fff; }
  .c-pg .dot { background: #336791; }
  .c-mysql .dot { background: #f29111; }
  .c-firebase .dot { background: #ffca28; }
  .c-git .dot { background: #f05032; }
  .c-figma .dot { background: #a259ff; }
  .c-pbi .dot { background: #f2c811; }

  /* ── DASHBOARD ── */
  .dashboard {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 20px;
    padding: 28px;
    overflow: hidden;
    position: relative;
  }
  .dashboard::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2), var(--accent3));
  }

  .dash-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 28px;
  }

  .dash-title {
    font-family: 'Syne', sans-serif;
    font-size: 16px;
    font-weight: 700;
    color: var(--text);
  }

  .dash-badge {
    font-size: 11px;
    padding: 4px 10px;
    background: rgba(52,211,153,0.1);
    border: 1px solid rgba(52,211,153,0.2);
    border-radius: 100px;
    color: var(--accent3);
  }

  /* Stats row */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    margin-bottom: 28px;
  }

  .stat-card {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 18px 16px;
    position: relative;
    overflow: hidden;
    transition: all 0.25s ease;
    cursor: default;
  }
  .stat-card:hover { transform: translateY(-2px); border-color: rgba(56,189,248,0.25); }
  .stat-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    border-radius: 2px;
  }
  .stat-card.s1::after { background: var(--accent); }
  .stat-card.s2::after { background: var(--accent2); }
  .stat-card.s3::after { background: var(--accent3); }
  .stat-card.s4::after { background: var(--gold); }

  .stat-icon { font-size: 18px; margin-bottom: 10px; }
  .stat-val {
    font-family: 'Syne', sans-serif;
    font-size: 28px;
    font-weight: 800;
    line-height: 1;
    margin-bottom: 4px;
  }
  .stat-card.s1 .stat-val { color: var(--accent); }
  .stat-card.s2 .stat-val { color: var(--accent2); }
  .stat-card.s3 .stat-val { color: var(--accent3); }
  .stat-card.s4 .stat-val { color: var(--gold); }
  .stat-lbl { font-size: 10px; text-transform: uppercase; letter-spacing: 0.1em; color: var(--muted); }

  /* Language bars */
  .lang-section { margin-bottom: 28px; }
  .lang-section-title {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    color: var(--muted);
    margin-bottom: 16px;
  }

  .lang-row {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .lang-item { display: flex; flex-direction: column; gap: 6px; }
  .lang-meta { display: flex; justify-content: space-between; font-size: 12px; }
  .lang-name { color: var(--text); }
  .lang-pct { color: var(--muted); }

  .bar-track {
    height: 6px;
    background: var(--surface2);
    border-radius: 100px;
    overflow: hidden;
  }
  .bar-fill {
    height: 100%;
    border-radius: 100px;
    transform-origin: left;
    transform: scaleX(0);
    animation: barIn 1s cubic-bezier(.4,0,.2,1) both;
  }
  @keyframes barIn {
    from { transform: scaleX(0); }
    to { transform: scaleX(1); }
  }
  .lang-item:nth-child(1) .bar-fill { animation-delay: 0.3s; }
  .lang-item:nth-child(2) .bar-fill { animation-delay: 0.45s; }
  .lang-item:nth-child(3) .bar-fill { animation-delay: 0.6s; }
  .lang-item:nth-child(4) .bar-fill { animation-delay: 0.75s; }
  .lang-item:nth-child(5) .bar-fill { animation-delay: 0.9s; }
  .lang-item:nth-child(6) .bar-fill { animation-delay: 1.05s; }

  /* Activity graph */
  .activity-section { }
  .activity-title {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    color: var(--muted);
    margin-bottom: 14px;
  }

  .activity-graph {
    display: grid;
    grid-template-columns: repeat(53, 1fr);
    grid-template-rows: repeat(7, 1fr);
    gap: 3px;
    width: 100%;
  }

  .cell {
    aspect-ratio: 1;
    border-radius: 2px;
    background: var(--surface2);
    transition: all 0.2s;
    cursor: default;
  }
  .cell:hover { transform: scale(1.4); z-index: 10; }
  .cell.l1 { background: rgba(56,189,248,0.15); }
  .cell.l2 { background: rgba(56,189,248,0.35); }
  .cell.l3 { background: rgba(56,189,248,0.6); }
  .cell.l4 { background: rgba(56,189,248,0.9); }

  .activity-legend {
    display: flex;
    align-items: center;
    gap: 6px;
    margin-top: 10px;
    justify-content: flex-end;
    font-size: 10px;
    color: var(--muted);
  }
  .legend-cell { width: 10px; height: 10px; border-radius: 2px; }

  /* ── CONNECT ── */
  .connect-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
    gap: 10px;
  }
  .connect-card {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 14px 16px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    text-decoration: none;
    color: var(--text);
    font-size: 13px;
    transition: all 0.2s ease;
  }
  .connect-card:hover {
    transform: translateY(-2px);
    border-color: rgba(56,189,248,0.35);
    box-shadow: 0 8px 24px rgba(0,0,0,0.3);
    color: var(--accent);
  }
  .connect-icon { font-size: 18px; }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    font-size: 11px;
    color: var(--muted);
    padding-top: 40px;
    border-top: 1px solid var(--border);
    letter-spacing: 0.08em;
  }
  .footer span { color: var(--accent); }

  /* ── COUNTER ANIMATION ── */
  .stat-val { transition: all 0.5s ease; }

  /* Responsive */
  @media (max-width: 640px) {
    .hero { grid-template-columns: 1fr; }
    .avatar-wrap { display: none; }
    .stats-row { grid-template-columns: repeat(2, 1fr); }
    .activity-graph { grid-template-columns: repeat(26, 1fr); }
  }
</style>
</head>
<body>

<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>

<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div>
      <div class="hero-tag">Available for work</div>
      <h1>Ricep<br><span>Ardiansyah</span></h1>
      <p class="hero-sub">Fullstack Web &amp; Mobile Developer 🚀</p>
      <p class="hero-desc">Building scalable web &amp; mobile applications with clean architecture. Currently exploring AI Recommendation Systems &amp; System Design from <strong style="color:var(--accent)">Yogyakarta, Indonesia</strong> 🇮🇩</p>
    </div>
    <div class="avatar-wrap">
      <div class="avatar">👨‍💻</div>
      <div class="status-dot"></div>
    </div>
  </div>

  <!-- ABOUT -->
  <section>
    <div class="section-label">About Me</div>
    <div class="about-grid">
      <div class="about-card">
        <div class="icon">🔭</div>
        <div class="label">Currently</div>
        <div class="value">Building Mobile &amp; Web Apps</div>
      </div>
      <div class="about-card">
        <div class="icon">🌱</div>
        <div class="label">Learning</div>
        <div class="value">System Design &amp; Scalable Backend</div>
      </div>
      <div class="about-card">
        <div class="icon">🤖</div>
        <div class="label">Interested In</div>
        <div class="value">AI Recommendation Systems</div>
      </div>
      <div class="about-card">
        <div class="icon">📍</div>
        <div class="label">Location</div>
        <div class="value">Yogyakarta, Indonesia</div>
      </div>
    </div>
  </section>

  <!-- TECH STACK -->
  <section>
    <div class="section-label">Core Tech Stack</div>

    <div class="stack-group">
      <div class="stack-title">Frontend</div>
      <div class="tech-chips">
        <div class="chip c-react"><span class="dot"></span>React</div>
        <div class="chip c-next"><span class="dot"></span>Next.js</div>
        <div class="chip c-flutter"><span class="dot"></span>Flutter</div>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-title">Backend</div>
      <div class="tech-chips">
        <div class="chip c-go"><span class="dot"></span>Golang</div>
        <div class="chip c-node"><span class="dot"></span>Node.js</div>
        <div class="chip c-flask"><span class="dot"></span>Flask</div>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-title">Database</div>
      <div class="tech-chips">
        <div class="chip c-pg"><span class="dot"></span>PostgreSQL</div>
        <div class="chip c-mysql"><span class="dot"></span>MySQL</div>
        <div class="chip c-firebase"><span class="dot"></span>Firebase</div>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-title">Tools</div>
      <div class="tech-chips">
        <div class="chip c-git"><span class="dot"></span>Git</div>
        <div class="chip c-figma"><span class="dot"></span>Figma</div>
        <div class="chip c-pbi"><span class="dot"></span>Power BI</div>
      </div>
    </div>
  </section>

  <!-- DASHBOARD -->
  <section>
    <div class="section-label">GitHub Dashboard</div>
    <div class="dashboard">
      <div class="dash-header">
        <div class="dash-title">ricepaja29 · GitHub Stats</div>
        <div class="dash-badge">● Active</div>
      </div>

      <!-- Stats Cards -->
      <div class="stats-row">
        <div class="stat-card s1">
          <div class="stat-icon">⭐</div>
          <div class="stat-val" id="s-stars">0</div>
          <div class="stat-lbl">Total Stars</div>
        </div>
        <div class="stat-card s2">
          <div class="stat-icon">🔀</div>
          <div class="stat-val" id="s-commits">0</div>
          <div class="stat-lbl">Commits</div>
        </div>
        <div class="stat-card s3">
          <div class="stat-icon">🔃</div>
          <div class="stat-val" id="s-prs">0</div>
          <div class="stat-lbl">Pull Requests</div>
        </div>
        <div class="stat-card s4">
          <div class="stat-icon">📦</div>
          <div class="stat-val" id="s-repos">0</div>
          <div class="stat-lbl">Repositories</div>
        </div>
      </div>

      <!-- Language Bars -->
      <div class="lang-section">
        <div class="lang-section-title">Top Languages</div>
        <div class="lang-row">
          <div class="lang-item">
            <div class="lang-meta"><span class="lang-name">Dart / Flutter</span><span class="lang-pct">38%</span></div>
            <div class="bar-track"><div class="bar-fill" style="width:38%;background:linear-gradient(90deg,#54c5f8,#0070f3)"></div></div>
          </div>
          <div class="lang-item">
            <div class="lang-meta"><span class="lang-name">JavaScript / TypeScript</span><span class="lang-pct">27%</span></div>
            <div class="bar-track"><div class="bar-fill" style="width:27%;background:linear-gradient(90deg,#f7df1e,#3178c6)"></div></div>
          </div>
          <div class="lang-item">
            <div class="lang-meta"><span class="lang-name">Go</span><span class="lang-pct">18%</span></div>
            <div class="bar-track"><div class="bar-fill" style="width:18%;background:linear-gradient(90deg,#00acd7,#007d9c)"></div></div>
          </div>
          <div class="lang-item">
            <div class="lang-meta"><span class="lang-name">Python</span><span class="lang-pct">10%</span></div>
            <div class="bar-track"><div class="bar-fill" style="width:10%;background:linear-gradient(90deg,#3776ab,#ffdc52)"></div></div>
          </div>
          <div class="lang-item">
            <div class="lang-meta"><span class="lang-name">Other</span><span class="lang-pct">7%</span></div>
            <div class="bar-track"><div class="bar-fill" style="width:7%;background:linear-gradient(90deg,#64748b,#94a3b8)"></div></div>
          </div>
        </div>
      </div>

      <!-- Activity Graph -->
      <div class="activity-section">
        <div class="activity-title">Contribution Activity — 2024</div>
        <div class="activity-graph" id="activityGraph"></div>
        <div class="activity-legend">
          Less
          <div class="legend-cell" style="background:var(--surface2)"></div>
          <div class="legend-cell" style="background:rgba(56,189,248,0.15)"></div>
          <div class="legend-cell" style="background:rgba(56,189,248,0.35)"></div>
          <div class="legend-cell" style="background:rgba(56,189,248,0.6)"></div>
          <div class="legend-cell" style="background:rgba(56,189,248,0.9)"></div>
          More
        </div>
      </div>
    </div>
  </section>

  <!-- CONNECT -->
  <section>
    <div class="section-label">Connect With Me</div>
    <div class="connect-grid">
      <a href="https://github.com/ricepaja29" target="_blank" class="connect-card">
        <span class="connect-icon">🐙</span>GitHub
      </a>
      <a href="#" class="connect-card">
        <span class="connect-icon">💼</span>LinkedIn
      </a>
      <a href="#" class="connect-card">
        <span class="connect-icon">✉️</span>Email
      </a>
      <a href="#" class="connect-card">
        <span class="connect-icon">🌐</span>Portfolio
      </a>
    </div>
  </section>

  <!-- FOOTER -->
  <div class="footer">
    ⭐ From <span>Ricep Ardiansyah</span> · Built with ❤️ in Yogyakarta
  </div>

</div>

<script>
  // ── Counter animation ──
  function countUp(el, target, duration = 1500, suffix = '') {
    let start = 0;
    const step = target / (duration / 16);
    const timer = setInterval(() => {
      start += step;
      if (start >= target) { start = target; clearInterval(timer); }
      el.textContent = Math.floor(start) + suffix;
    }, 16);
  }

  // Trigger counters when visible
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        countUp(document.getElementById('s-stars'), 42);
        countUp(document.getElementById('s-commits'), 387);
        countUp(document.getElementById('s-prs'), 28);
        countUp(document.getElementById('s-repos'), 15);
        observer.disconnect();
      }
    });
  }, { threshold: 0.3 });

  observer.observe(document.querySelector('.dashboard'));

  // ── Activity Graph ──
  const graph = document.getElementById('activityGraph');
  const levels = [0, 1, 2, 3, 4];
  const weights = [0.45, 0.25, 0.15, 0.1, 0.05];

  function weightedRandom() {
    const r = Math.random();
    let sum = 0;
    for (let i = 0; i < weights.length; i++) {
      sum += weights[i];
      if (r < sum) return levels[i];
    }
    return 0;
  }

  // 53 weeks × 7 days
  for (let w = 0; w < 53; w++) {
    for (let d = 0; d < 7; d++) {
      const cell = document.createElement('div');
      const lvl = weightedRandom();
      cell.className = 'cell' + (lvl > 0 ? ` l${lvl}` : '');
      cell.style.animationDelay = `${(w * 7 + d) * 4}ms`;
      graph.appendChild(cell);
    }
  }

  // ── Hover sparkle on chips ──
  document.querySelectorAll('.chip').forEach(chip => {
    chip.addEventListener('mouseenter', () => {
      chip.style.transition = 'all 0.15s cubic-bezier(.4,0,.2,1)';
    });
  });
</script>
</body>
</html>
