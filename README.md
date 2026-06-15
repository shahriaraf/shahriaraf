<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Araf – GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Special+Elite&family=Courier+Prime:wght@400;700&display=swap" rel="stylesheet">
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: #f5f0e8;
    color: #1a1a1a;
    font-family: 'Courier Prime', 'Courier New', monospace;
    font-size: 13px;
    line-height: 1.6;
  }

  .page {
    max-width: 820px;
    margin: 0 auto;
    padding: 24px 20px 48px;
  }

  .readme-card {
    border: 2px solid #1a1a1a;
    background: #faf7f0;
    position: relative;
  }

  .readme-card::before {
    content: '';
    position: absolute;
    inset: 4px;
    border: 1px solid #1a1a1a;
    pointer-events: none;
    z-index: 0;
  }

  .inner { position: relative; z-index: 1; }

  /* BANNER */
  .banner {
    background: #1a1a1a;
    height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 8px;
    position: relative;
    overflow: hidden;
    border-bottom: 2px solid #1a1a1a;
  }

  .banner::before {
    content: '';
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      0deg, transparent, transparent 3px,
      rgba(255,255,255,0.03) 3px, rgba(255,255,255,0.03) 4px
    );
  }

  .banner-title {
    font-family: 'Special Elite', cursive;
    font-size: 52px;
    color: #f5f0e8;
    letter-spacing: 6px;
    text-align: center;
    position: relative;
    z-index: 2;
    text-shadow: 3px 3px 0 #000;
  }

  .banner-sub {
    font-family: 'Courier Prime', monospace;
    font-size: 11px;
    color: #888;
    letter-spacing: 8px;
    text-transform: uppercase;
    position: relative;
    z-index: 2;
  }

  .banner-ornament {
    position: absolute;
    color: rgba(255,255,255,0.04);
    font-size: 220px;
    font-family: 'Special Elite', cursive;
    top: -30px;
    left: -10px;
    z-index: 1;
    user-select: none;
  }

  /* STATS */
  .stats-row {
    display: flex;
    border-bottom: 1px solid #1a1a1a;
  }

  .stat {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 14px 8px;
    border-right: 1px solid #1a1a1a;
    gap: 2px;
  }

  .stat:last-child { border-right: none; }

  .stat-num {
    font-family: 'Special Elite', cursive;
    font-size: 26px;
    color: #1a1a1a;
  }

  .stat-label {
    font-size: 9px;
    letter-spacing: 3px;
    color: #666;
    text-transform: uppercase;
  }

  /* SECTIONS */
  .section {
    padding: 28px 28px 24px;
    border-bottom: 1px solid #1a1a1a;
  }

  .section-head {
    text-align: center;
    margin-bottom: 22px;
    position: relative;
  }

  .section-title {
    font-family: 'Special Elite', cursive;
    font-size: 20px;
    color: #1a1a1a;
    letter-spacing: 3px;
    display: inline-block;
    background: #faf7f0;
    padding: 0 16px;
    position: relative;
    z-index: 1;
  }

  .section-head::before {
    content: '';
    position: absolute;
    top: 50%;
    left: 0;
    right: 0;
    height: 1px;
    background: #1a1a1a;
    z-index: 0;
  }

  /* ABOUT */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 28px;
    align-items: start;
  }

  .about-photo-frame {
    border: 2px solid #1a1a1a;
    padding: 8px;
    background: #f0ebe0;
  }

  .about-photo-inner {
    background: #2a2a2a;
    height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
    position: relative;
  }

  .about-photo-inner::after {
    content: '';
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      -45deg, transparent, transparent 8px,
      rgba(255,255,255,0.03) 8px, rgba(255,255,255,0.03) 9px
    );
  }

  .photo-placeholder {
    font-size: 80px;
    color: #555;
    position: relative;
    z-index: 1;
  }

  .photo-caption {
    text-align: center;
    font-size: 9px;
    letter-spacing: 2px;
    color: #888;
    margin-top: 6px;
    text-transform: uppercase;
  }

  .about-text { display: flex; flex-direction: column; gap: 14px; }

  .about-name {
    font-family: 'Special Elite', cursive;
    font-size: 22px;
    color: #1a1a1a;
    border-bottom: 2px solid #1a1a1a;
    padding-bottom: 8px;
  }

  .about-bio {
    font-size: 13px;
    line-height: 1.8;
    color: #333;
  }

  .about-meta { display: flex; flex-direction: column; gap: 5px; }

  .meta-row {
    display: flex;
    gap: 10px;
    font-size: 11px;
    color: #555;
    align-items: center;
  }

  .meta-key {
    font-family: 'Special Elite', cursive;
    font-size: 10px;
    letter-spacing: 2px;
    color: #1a1a1a;
    min-width: 60px;
  }

  /* TECH STACK */
  .stack-category { margin-bottom: 20px; }

  .stack-cat-title {
    font-family: 'Special Elite', cursive;
    font-size: 12px;
    letter-spacing: 3px;
    color: #888;
    text-transform: uppercase;
    margin-bottom: 10px;
    border-bottom: 1px dashed #ccc;
    padding-bottom: 4px;
  }

  .stack-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .stack-tag {
    border: 1px solid #1a1a1a;
    padding: 4px 12px;
    font-family: 'Courier Prime', monospace;
    font-size: 11px;
    color: #1a1a1a;
    letter-spacing: 1px;
    background: #faf7f0;
    position: relative;
  }

  .stack-tag::before { content: '▪ '; font-size: 8px; }

  .stack-tag.primary {
    background: #1a1a1a;
    color: #f5f0e8;
  }

  .stack-extra {
    margin-top: 14px;
    font-size: 11px;
    color: #555;
    border-left: 2px solid #1a1a1a;
    padding-left: 12px;
    line-height: 1.8;
    font-style: italic;
  }

  /* CONTRIBUTION GRAPH */
  .contrib-label {
    font-family: 'Courier Prime', monospace;
    font-size: 10px;
    color: #888;
    text-align: center;
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  #contrib-canvas {
    width: 100%;
    display: block;
  }

  .graph-axis {
    display: flex;
    justify-content: space-between;
    margin-top: 6px;
    font-size: 9px;
    color: #888;
    letter-spacing: 1px;
  }

  .contrib-legend {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    gap: 6px;
    margin-top: 8px;
    font-size: 9px;
    color: #888;
  }

  .legend-swatch {
    width: 10px;
    height: 10px;
    border: 1px solid #888;
  }

  /* GITHUB STATS */
  .github-stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 18px;
  }

  .stat-card {
    border: 1px solid #1a1a1a;
    padding: 16px;
    background: #faf7f0;
  }

  .stat-card-title {
    font-family: 'Special Elite', cursive;
    font-size: 11px;
    letter-spacing: 3px;
    color: #888;
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  .stat-card-rows { display: flex; flex-direction: column; gap: 8px; }

  .stat-card-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 12px;
  }

  .stat-card-key { color: #555; }

  .stat-card-val {
    font-family: 'Special Elite', cursive;
    font-size: 15px;
    color: #1a1a1a;
  }

  .bar-track { height: 4px; background: #ddd; width: 100%; margin-top: 6px; }
  .bar-fill { height: 4px; background: #1a1a1a; }

  /* CONNECT */
  .connect-links {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    margin-bottom: 20px;
  }

  .connect-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    border: 1px solid #1a1a1a;
    padding: 7px 18px;
    font-family: 'Courier Prime', monospace;
    font-size: 11px;
    color: #1a1a1a;
    text-decoration: none;
    letter-spacing: 2px;
    cursor: pointer;
    background: #faf7f0;
    transition: background 0.15s, color 0.15s;
  }

  .connect-btn:hover { background: #1a1a1a; color: #f5f0e8; }

  /* QUOTES */
  .quotes { display: flex; flex-direction: column; gap: 12px; }

  .quote-item {
    border-left: 3px solid #1a1a1a;
    padding: 8px 16px;
    font-size: 12px;
    color: #555;
    font-style: italic;
    line-height: 1.7;
    background: #f0ebe0;
  }

  .quote-source {
    font-size: 10px;
    letter-spacing: 2px;
    color: #888;
    margin-top: 4px;
    font-style: normal;
  }

  /* FOOTER */
  .footer {
    background: #1a1a1a;
    padding: 14px;
    text-align: center;
    font-size: 9px;
    color: #555;
    letter-spacing: 4px;
    text-transform: uppercase;
  }
</style>
</head>
<body>
<div class="page">
<div class="readme-card">
<div class="inner">

  <!-- BANNER -->
  <div class="banner">
    <div class="banner-ornament">&lt;/&gt;</div>
    <div class="banner-title">ARAF</div>
    <div class="banner-sub">Full-Stack Engineer &bull; System Architect &bull; Builder</div>
  </div>

  <!-- STATS -->
  <div class="stats-row">
    <div class="stat"><span class="stat-num">12</span><span class="stat-label">Repos</span></div>
    <div class="stat"><span class="stat-num">3</span><span class="stat-label">Followers</span></div>
    <div class="stat"><span class="stat-num">247</span><span class="stat-label">Commits</span></div>
    <div class="stat"><span class="stat-num">4</span><span class="stat-label">Projects</span></div>
    <div class="stat"><span class="stat-num">2</span><span class="stat-label">PRs</span></div>
  </div>

  <!-- ABOUT -->
  <div class="section">
    <div class="section-head"><span class="section-title">Who I Am</span></div>
    <div class="about-grid">
      <div class="about-photo-frame">
        <div class="about-photo-inner">
          <span class="photo-placeholder">&#9787;</span>
        </div>
        <div class="photo-caption">Sylhet, Bangladesh &mdash; CSE Undergrad</div>
      </div>
      <div class="about-text">
        <div class="about-name">Hey, I'm Araf</div>
        <div class="about-bio">
          A Computer Science undergrad from Sylhet obsessed with system design, clean architecture, and shipping things that actually work. I build full-stack products end-to-end — from database schema to polished UI — and spend too much time thinking about how things scale before they need to.
        </div>
        <div class="about-meta">
          <div class="meta-row"><span class="meta-key">STATUS</span><span>Building in public, learning in private</span></div>
          <div class="meta-row"><span class="meta-key">FOCUS</span><span>SaaS products &amp; distributed systems</span></div>
          <div class="meta-row"><span class="meta-key">CURRENT</span><span>Turf booking SaaS + FlowBoard</span></div>
          <div class="meta-row"><span class="meta-key">BASED IN</span><span>Sylhet, Bangladesh</span></div>
        </div>
      </div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section">
    <div class="section-head"><span class="section-title">Technical Arsenal</span></div>
    <div class="stack-category">
      <div class="stack-cat-title">Frontend</div>
      <div class="stack-tags">
        <span class="stack-tag primary">React</span>
        <span class="stack-tag primary">Next.js</span>
        <span class="stack-tag primary">TypeScript</span>
        <span class="stack-tag">JavaScript</span>
        <span class="stack-tag">HTML</span>
        <span class="stack-tag">CSS</span>
        <span class="stack-tag">Tailwind CSS</span>
        <span class="stack-tag">Redux</span>
        <span class="stack-tag">Bootstrap</span>
      </div>
    </div>
    <div class="stack-category">
      <div class="stack-cat-title">Backend &amp; Databases</div>
      <div class="stack-tags">
        <span class="stack-tag primary">NestJS</span>
        <span class="stack-tag primary">PostgreSQL</span>
        <span class="stack-tag primary">Prisma</span>
        <span class="stack-tag">Node.js</span>
        <span class="stack-tag">Express</span>
        <span class="stack-tag">MongoDB</span>
        <span class="stack-tag">MySQL</span>
      </div>
    </div>
    <div class="stack-category">
      <div class="stack-cat-title">Tools &amp; DevOps</div>
      <div class="stack-tags">
        <span class="stack-tag">Docker</span>
        <span class="stack-tag">Git</span>
        <span class="stack-tag">GitHub</span>
        <span class="stack-tag">GitLab</span>
        <span class="stack-tag">Firebase</span>
        <span class="stack-tag">Postman</span>
        <span class="stack-tag">Figma</span>
      </div>
    </div>
    <div class="stack-extra">
      Also experienced with: Shadcn UI &middot; Framer Motion &middot; GSAP &middot; WebSockets &middot; Redis &middot; BullMQ &middot; JWT Authentication &middot; Socket.IO
    </div>
  </div>

  <!-- CONTRIBUTION GRAPH -->
  <div class="section">
    <div class="section-head"><span class="section-title">Contribution Graph</span></div>
    <div class="contrib-label">365 days of commits &mdash; rendered in the field</div>
    <canvas id="contrib-canvas" height="100"></canvas>
    <div class="graph-axis">
      <span>Jan</span><span>Feb</span><span>Mar</span><span>Apr</span><span>May</span>
      <span>Jun</span><span>Jul</span><span>Aug</span><span>Sep</span><span>Oct</span>
      <span>Nov</span><span>Dec</span>
    </div>
    <div class="contrib-legend">
      <span>Less</span>
      <div class="legend-swatch" style="background:#f5f0e8;"></div>
      <div class="legend-swatch" style="background:#bbb;"></div>
      <div class="legend-swatch" style="background:#777;"></div>
      <div class="legend-swatch" style="background:#333;"></div>
      <div class="legend-swatch" style="background:#1a1a1a;"></div>
      <span>More</span>
    </div>
  </div>

  <!-- GITHUB STATS -->
  <div class="section">
    <div class="section-head"><span class="section-title">GitHub Statistics</span></div>
    <div class="github-stats-grid">
      <div class="stat-card">
        <div class="stat-card-title">Activity Report</div>
        <div class="stat-card-rows">
          <div class="stat-card-row"><span class="stat-card-key">Total commits (2024)</span><span class="stat-card-val">247</span></div>
          <div class="stat-card-row"><span class="stat-card-key">Pull requests</span><span class="stat-card-val">12</span></div>
          <div class="stat-card-row"><span class="stat-card-key">Issues opened</span><span class="stat-card-val">8</span></div>
          <div class="stat-card-row"><span class="stat-card-key">Code reviews</span><span class="stat-card-val">19</span></div>
          <div class="stat-card-row"><span class="stat-card-key">Stars earned</span><span class="stat-card-val">11</span></div>
        </div>
      </div>
      <div class="stat-card">
        <div class="stat-card-title">Top Languages</div>
        <div class="stat-card-rows">
          <div><div class="stat-card-row"><span class="stat-card-key">TypeScript</span><span class="stat-card-val">42%</span></div><div class="bar-track"><div class="bar-fill" style="width:42%"></div></div></div>
          <div><div class="stat-card-row"><span class="stat-card-key">JavaScript</span><span class="stat-card-val">28%</span></div><div class="bar-track"><div class="bar-fill" style="width:28%"></div></div></div>
          <div><div class="stat-card-row"><span class="stat-card-key">Python</span><span class="stat-card-val">16%</span></div><div class="bar-track"><div class="bar-fill" style="width:16%"></div></div></div>
          <div><div class="stat-card-row"><span class="stat-card-key">CSS / HTML</span><span class="stat-card-val">14%</span></div><div class="bar-track"><div class="bar-fill" style="width:14%"></div></div></div>
        </div>
      </div>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section">
    <div class="section-head"><span class="section-title">Connect</span></div>
    <div class="connect-links">
      <a class="connect-btn" href="#">
        <svg width="13" height="13" viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
        GITHUB
      </a>
      <a class="connect-btn" href="#">
        <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LINKEDIN
      </a>
      <a class="connect-btn" href="#">
        <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.91 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg>
        GMAIL
      </a>
      <a class="connect-btn" href="#">
        <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M14 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V8l-6-6zm-1 1.5L18.5 9H13V3.5zM6 20V4h5v7h7v9H6z"/></svg>
        RESUME
      </a>
    </div>
    <div class="quotes">
      <div class="quote-item">
        Code is never finished. It only becomes slightly less terrible over time.
        <div class="quote-source">&mdash; Every developer, eventually</div>
      </div>
      <div class="quote-item">
        Every commit I make is a small, desperate apology to my future self. Someday I will return to this codebase, look at the spaghetti I've written, and wonder who let me anywhere near a keyboard.
        <div class="quote-source">&mdash; git log --author="me"</div>
      </div>
    </div>
  </div>

  <div class="footer">Rendered with ink &bull; Sylhet, Bangladesh &bull; 2025</div>

</div>
</div>
</div>

<script>
(function() {
  var canvas = document.getElementById('contrib-canvas');
  if (!canvas) return;
  var weeks = 53, days = 7, cellSize = 12, gap = 2;
  var totalW = weeks * (cellSize + gap) - gap;
  var totalH = days * (cellSize + gap) - gap;
  canvas.width = totalW;
  canvas.height = totalH;
  canvas.style.width = '100%';
  canvas.style.height = 'auto';
  var ctx = canvas.getContext('2d');
  var fills = ['#f0ebe0', '#c8c0b0', '#888070', '#444038', '#1a1a1a'];
  var seed = 42;
  function rand() {
    seed = (seed * 1664525 + 1013904223) & 0xffffffff;
    return (seed >>> 0) / 0xffffffff;
  }
  for (var w = 0; w < weeks; w++) {
    for (var d = 0; d < days; d++) {
      var r = rand();
      var level = r < 0.35 ? 0 : r < 0.55 ? 1 : r < 0.72 ? 2 : r < 0.87 ? 3 : 4;
      if (w > 38 && w < 50 && rand() > 0.4) level = Math.min(4, level + 1);
      var x = w * (cellSize + gap), y = d * (cellSize + gap);
      ctx.fillStyle = fills[level];
      ctx.fillRect(x, y, cellSize, cellSize);
      ctx.strokeStyle = 'rgba(0,0,0,0.12)';
      ctx.lineWidth = 0.5;
      ctx.strokeRect(x + 0.25, y + 0.25, cellSize - 0.5, cellSize - 0.5);
    }
  }
})();
</script>
</body>
</html>
