<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>🎃 pumpkin-repo · cute README + steps</title>
  <!-- Font Awesome Icons (free) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: #1e1a17; /* deep autumn night */
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      font-family: 'Segoe UI', 'Quicksand', system-ui, -apple-system, sans-serif;
      padding: 1.5rem;
    }

    /* 🎃 PUMPKIN CARD — warm, glowy, cute */
    .pumpkin-card {
      max-width: 920px;
      width: 100%;
      background: linear-gradient(145deg, #fbe9d2 0%, #f7d9b0 100%);
      backdrop-filter: blur(8px);
      border-radius: 4rem 4rem 3rem 3rem;
      padding: 2.5rem 2.8rem;
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.6),
                  0 0 0 2px #f3b47e,
                  0 0 30px #f39c6d80,
                  inset 0 0 30px #fce3c0;
      border: 2px solid #f9c89b;
      transition: box-shadow 0.3s ease, transform 0.2s ease;
      position: relative;
      overflow: hidden;
    }

    .pumpkin-card::before {
      content: "✦ ✧ ✦ ✧ ✦";
      position: absolute;
      top: -10px;
      right: 20px;
      font-size: 1.8rem;
      letter-spacing: 8px;
      color: #f5b06b;
      opacity: 0.25;
      white-space: nowrap;
      pointer-events: none;
      transform: rotate(6deg);
    }

    .pumpkin-card::after {
      content: "🍂 🍁 🎃";
      position: absolute;
      bottom: 10px;
      left: 20px;
      font-size: 2.2rem;
      opacity: 0.15;
      pointer-events: none;
      transform: rotate(-4deg);
    }

    .pumpkin-card:hover {
      box-shadow: 0 30px 50px rgba(0, 0, 0, 0.5),
                  0 0 0 3px #f3a66b,
                  0 0 50px #f39c6d;
      transform: translateY(-5px);
    }

    /* header — avatar + name */
    .profile-header {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 2rem;
      margin-bottom: 1.8rem;
      position: relative;
      z-index: 2;
    }

    .avatar-wrapper {
      position: relative;
      flex-shrink: 0;
    }

    .avatar {
      width: 120px;
      height: 120px;
      border-radius: 50%;
      object-fit: cover;
      background: #d68f5c;
      border: 5px solid #f9c89b;
      box-shadow: 0 0 0 4px #d67d44, 0 10px 20px rgba(0,0,0,0.2);
      transition: all 0.25s ease;
      display: block;
    }

    .avatar-wrapper:hover .avatar {
      border-color: #f5b06b;
      box-shadow: 0 0 0 6px #f5b06b, 0 12px 28px rgba(0,0,0,0.3);
      transform: scale(1.02) rotate(-2deg);
    }

    .status-ring {
      position: absolute;
      bottom: 6px;
      right: 6px;
      background: #f7d9b0;
      border-radius: 50%;
      padding: 4px;
      border: 3px solid #d68f5c;
      box-shadow: 0 0 0 2px #f9c89b;
    }

    .status-dot {
      display: block;
      width: 18px;
      height: 18px;
      background: #f57c3a;
      border-radius: 50%;
      animation: pumpkin-pulse 2s infinite;
      box-shadow: 0 0 12px #f57c3a;
    }

    @keyframes pumpkin-pulse {
      0% { opacity: 0.7; transform: scale(0.9); background: #f57c3a; }
      50% { opacity: 1; transform: scale(1.2); background: #f7a15c; box-shadow: 0 0 20px #f7a15c; }
      100% { opacity: 0.7; transform: scale(0.9); background: #f57c3a; }
    }

    .name-title h1 {
      font-size: 2.8rem;
      font-weight: 700;
      color: #5a3a22;
      text-shadow: 2px 2px 0 #f5cba0, 4px 4px 0 rgba(0,0,0,0.05);
      letter-spacing: -0.5px;
      line-height: 1.2;
    }

    .name-title .badge {
      display: inline-block;
      background: #f9c89b;
      backdrop-filter: blur(4px);
      padding: 0.4rem 1.4rem;
      border-radius: 60px;
      font-size: 0.9rem;
      font-weight: 600;
      color: #4a2f1e;
      border: 2px solid #d68f5c;
      box-shadow: inset 0 0 10px #fbe1c0;
      margin-top: 0.4rem;
      letter-spacing: 0.5px;
    }

    .name-title .badge i {
      margin-right: 8px;
      color: #c96f3a;
    }

    /* bio */
    .bio {
      margin: 1.2rem 0 1.5rem 0;
      font-size: 1.1rem;
      line-height: 1.6;
      color: #3d2b1c;
      background: rgba(255, 235, 210, 0.5);
      backdrop-filter: blur(4px);
      padding: 0.9rem 1.5rem;
      border-radius: 60px 20px 60px 20px;
      border-left: 6px solid #f5a66b;
      box-shadow: inset 0 1px 10px #fde5c8;
      font-weight: 500;
    }

    .bio i {
      color: #d67d44;
      margin-right: 8px;
    }

    .bio strong {
      color: #5a3a22;
      background: #f9dbb8;
      padding: 0.1rem 0.6rem;
      border-radius: 40px;
      font-weight: 600;
    }

    /* social links */
    .social-links {
      display: flex;
      flex-wrap: wrap;
      gap: 0.7rem 1rem;
      margin: 1.5rem 0 1.8rem 0;
    }

    .social-links a {
      color: #4a2f1e;
      background: #fbe1c0;
      padding: 0.4rem 1.3rem;
      border-radius: 60px;
      text-decoration: none;
      font-size: 0.95rem;
      font-weight: 600;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      border: 2px solid #d68f5c;
      transition: all 0.2s ease;
      box-shadow: 0 4px 0 #b57646;
      backdrop-filter: blur(4px);
    }

    .social-links a i {
      font-size: 1.2rem;
      width: 1.4rem;
      text-align: center;
      color: #b66d3a;
      transition: color 0.2s;
    }

    .social-links a:hover {
      background: #f5cba0;
      border-color: #b66d3a;
      color: #2f1f12;
      transform: translateY(-3px);
      box-shadow: 0 6px 0 #a05f32;
    }

    .social-links a:hover i {
      color: #c96f3a;
    }

    /* stats */
    .stats-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
      gap: 1rem;
      background: #f7d9b0;
      padding: 1.5rem 1.2rem;
      border-radius: 3rem 1rem 3rem 1rem;
      margin: 1.8rem 0 2rem 0;
      border: 3px solid #d68f5c;
      box-shadow: inset 0 4px 12px #eab787, 0 6px 0 #a86f42;
    }

    .stat-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
    }

    .stat-number {
      font-size: 2.2rem;
      font-weight: 800;
      color: #3d2b1c;
      letter-spacing: 0.5px;
      background: #fbe9d2;
      padding: 0.1rem 0.8rem;
      border-radius: 60px;
      box-shadow: inset 0 -3px 0 #d68f5c;
      text-shadow: 1px 1px 0 #f5cba0;
    }

    .stat-label {
      font-size: 0.8rem;
      text-transform: uppercase;
      letter-spacing: 1.5px;
      color: #5a3a22;
      margin-top: 6px;
      font-weight: 700;
      background: #f5cba0;
      padding: 0.1rem 0.8rem;
      border-radius: 40px;
      border: 1px solid #d68f5c;
    }

    .stat-label i {
      margin-right: 6px;
      color: #b66d3a;
    }

    /* projects */
    .project-section {
      margin: 2rem 0 1.2rem 0;
    }

    .project-section h3 {
      color: #3d2b1c;
      font-weight: 700;
      letter-spacing: 1px;
      border-bottom: 4px dotted #d68f5c;
      padding-bottom: 0.6rem;
      margin-bottom: 1.2rem;
      display: flex;
      align-items: center;
      gap: 12px;
      font-size: 1.5rem;
      text-shadow: 1px 1px 0 #f5cba0;
    }

    .project-section h3 i {
      color: #c96f3a;
      font-size: 1.8rem;
      transform: rotate(6deg);
    }

    .project-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 1.2rem;
    }

    .project-card {
      background: #fbe9d2;
      border-radius: 2.5rem 1rem 2.5rem 1rem;
      padding: 1.2rem 1.2rem 1.5rem;
      border: 3px solid #d68f5c;
      transition: all 0.2s ease;
      box-shadow: 0 6px 0 #b57646, inset 0 0 20px #fde5c8;
    }

    .project-card:hover {
      border-color: #b66d3a;
      transform: translateY(-6px);
      box-shadow: 0 12px 0 #a05f32, 0 12px 28px rgba(0, 0, 0, 0.15);
      background: #fde5c8;
    }

    .project-card h4 {
      color: #3d2b1c;
      font-size: 1.2rem;
      margin-bottom: 6px;
      display: flex;
      align-items: center;
      gap: 8px;
      font-weight: 700;
    }

    .project-card h4 i {
      color: #c96f3a;
      font-size: 1.2rem;
    }

    .project-card p {
      color: #4a2f1e;
      font-size: 0.9rem;
      line-height: 1.4;
      margin: 6px 0 10px 0;
      font-weight: 500;
    }

    .project-tag {
      display: inline-block;
      background: #f9c89b;
      color: #3d2b1c;
      font-size: 0.7rem;
      padding: 0.2rem 1rem;
      border-radius: 40px;
      border: 2px solid #d68f5c;
      letter-spacing: 0.3px;
      margin-right: 4px;
      font-weight: 600;
      box-shadow: inset 0 0 6px #fbe1c0;
    }

    .project-tag i {
      margin-right: 4px;
      font-size: 0.7rem;
      color: #b66d3a;
    }

    /* STEPS SECTION — new! */
    .steps-section {
      margin: 2rem 0 1.5rem 0;
      background: rgba(255, 235, 210, 0.6);
      backdrop-filter: blur(4px);
      border-radius: 2.5rem 1rem 2.5rem 1rem;
      padding: 1.5rem 1.8rem;
      border: 3px solid #d68f5c;
      box-shadow: inset 0 0 20px #fde5c8, 0 6px 0 #b57646;
    }

    .steps-section h3 {
      color: #3d2b1c;
      font-weight: 700;
      display: flex;
      align-items: center;
      gap: 12px;
      font-size: 1.5rem;
      margin-bottom: 1rem;
      text-shadow: 1px 1px 0 #f5cba0;
    }

    .steps-section h3 i {
      color: #c96f3a;
      font-size: 1.8rem;
    }

    .step-list {
      display: flex;
      flex-direction: column;
      gap: 0.9rem;
      counter-reset: step-counter;
    }

    .step-item {
      display: flex;
      align-items: flex-start;
      gap: 1rem;
      background: #fbe9d2;
      padding: 0.8rem 1.2rem;
      border-radius: 60px 20px 60px 20px;
      border: 2px solid #d68f5c;
      box-shadow: 0 3px 0 #b57646;
      transition: all 0.15s ease;
    }

    .step-item:hover {
      transform: translateX(6px);
      background: #fde5c8;
      border-color: #b66d3a;
    }

    .step-number {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      background: #f5b06b;
      color: #2f1f12;
      font-weight: 800;
      font-size: 1.1rem;
      width: 2.2rem;
      height: 2.2rem;
      border-radius: 50%;
      border: 3px solid #b57646;
      box-shadow: 0 3px 0 #8f5c34;
      flex-shrink: 0;
    }

    .step-content {
      flex: 1;
      color: #3d2b1c;
      font-weight: 500;
      font-size: 0.98rem;
      line-height: 1.5;
      padding-top: 0.1rem;
    }

    .step-content code {
      background: #f9c89b;
      padding: 0.1rem 0.6rem;
      border-radius: 30px;
      font-size: 0.85rem;
      border: 1px solid #d68f5c;
      color: #4a2f1e;
      font-weight: 600;
    }

    .step-content i {
      color: #c96f3a;
      margin-right: 4px;
    }

    /* footer */
    .footer-cta {
      margin-top: 2.2rem;
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      align-items: center;
      gap: 1rem;
    }

    .footer-cta .cta-button {
      background: #d68f5c;
      border: none;
      padding: 0.7rem 2rem;
      border-radius: 60px;
      font-weight: 700;
      color: #2f1f12;
      display: inline-flex;
      align-items: center;
      gap: 12px;
      font-size: 1rem;
      transition: all 0.2s ease;
      border: 3px solid #b57646;
      box-shadow: 0 6px 0 #8f5c34, 0 8px 20px rgba(0,0,0,0.2);
      text-decoration: none;
      background: #f5b06b;
    }

    .footer-cta .cta-button i {
      font-size: 1.2rem;
      color: #5a3a22;
    }

    .footer-cta .cta-button:hover {
      background: #f5a66b;
      transform: scale(1.02);
      box-shadow: 0 8px 0 #8f5c34, 0 12px 30px #d68f5c80;
      border-color: #c96f3a;
    }

    .footer-cta .gh-link {
      color: #4a2f1e;
      text-decoration: none;
      font-size: 0.95rem;
      border-bottom: 3px dotted #d68f5c;
      transition: color 0.2s;
      font-weight: 600;
      background: #fbe1c0;
      padding: 0.2rem 1rem;
      border-radius: 40px;
    }

    .footer-cta .gh-link:hover {
      color: #2f1f12;
      border-bottom-color: #b66d3a;
      background: #f5cba0;
    }

    /* responsive */
    @media (max-width: 600px) {
      .pumpkin-card { padding: 1.8rem; border-radius: 2.5rem; }
      .name-title h1 { font-size: 2rem; }
      .avatar { width: 90px; height: 90px; }
      .profile-header { gap: 1rem; }
      .stats-grid { grid-template-columns: 1fr 1fr; }
      .bio { font-size: 0.95rem; padding: 0.6rem 1rem; }
      .step-item { flex-wrap: wrap; }
      .step-number { width: 1.8rem; height: 1.8rem; font-size: 0.9rem; }
    }

    /* floating leaves */
    .pumpkin-card .leaf {
      position: absolute;
      font-size: 2.4rem;
      opacity: 0.10;
      pointer-events: none;
      z-index: 0;
      transform: rotate(12deg);
    }
  </style>
</head>
<body>
  <div class="pumpkin-card">
    <!-- floating decorations -->
    <span class="leaf" style="top: 10px; left: 10px;">🍁</span>
    <span class="leaf" style="bottom: 20px; right: 15px; transform: rotate(30deg);">🍂</span>
    <span class="leaf" style="top: 40%; right: 8px; font-size: 3rem; opacity: 0.08;">🎃</span>

    <!-- HEADER -->
    <div class="profile-header">
      <div class="avatar-wrapper">
        <img class="avatar" src="https://avatars.githubusercontent.com/u/583231?v=4" alt="pumpkin avatar" />
        <span class="status-ring"><span class="status-dot"></span></span>
      </div>
      <div class="name-title">
        <h1>🎃 pumpkin-repo</h1>
        <span class="badge"><i class="fas fa-seedling"></i> cute · full-stack · harvest</span>
        <div style="margin-top: 8px; display: flex; gap: 12px; flex-wrap: wrap;">
          <span style="color:#4a2f1e; font-weight:600; background:#f9dbb8; padding:0.1rem 0.8rem; border-radius:40px; border:1px solid #d68f5c;">
            <i class="fas fa-map-pin" style="color:#c96f3a;"></i> autumn · cozy
          </span>
          <span style="color:#4a2f1e; font-weight:600; background:#f9dbb8; padding:0.1rem 0.8rem; border-radius:40px; border:1px solid #d68f5c;">
            <i class="fas fa-calendar-alt" style="color:#c96f3a;"></i> harvest 2026
          </span>
        </div>
      </div>
    </div>

    <!-- BIO -->
    <div class="bio">
      <i class="fas fa-pumpkin"></i> 
      building <strong>pumpkin-spiced</strong> apps & tools · <strong>React</strong> + <strong>Rust</strong> · 
      <i class="fas fa-star" style="color:#c96f3a;"></i> 4.8k stars
      <span style="display:inline-block; background:#f9c89b; padding:0.1rem 0.8rem; border-radius:60px; font-size:0.7rem; margin-left:8px; border:2px solid #d68f5c;">
        <i class="fas fa-candy-cane" style="color:#b66d3a;"></i> sweet code
      </span>
    </div>

    <!-- SOCIAL LINKS -->
    <div class="social-links">
      <a href="#"><i class="fab fa-github"></i> github</a>
      <a href="#"><i class="fab fa-twitter"></i> tweeter</a>
      <a href="#"><i class="fab fa-dev"></i> dev.to</a>
      <a href="#"><i class="fas fa-globe"></i> portfolio</a>
      <a href="#"><i class="fas fa-mug-hot"></i> buymeacoffee</a>
    </div>

    <!-- STATS -->
    <div class="stats-grid">
      <div class="stat-item">
        <span class="stat-number" data-count="32">32</span>
        <span class="stat-label"><i class="fas fa-folder-open"></i> repos</span>
      </div>
      <div class="stat-item">
        <span class="stat-number" data-count="1.8k">1.8k</span>
        <span class="stat-label"><i class="fas fa-star"></i> stars</span>
      </div>
      <div class="stat-item">
        <span class="stat-number" data-count="420">420</span>
        <span class="stat-label"><i class="fas fa-code-branch"></i> forks</span>
      </div>
      <div class="stat-item">
        <span class="stat-number" data-count="22">22</span>
        <span class="stat-label"><i class="fas fa-trophy"></i> projects</span>
      </div>
    </div>

    <!-- PROJECTS -->
    <div class="project-section">
      <h3><i class="fas fa-pumpkin"></i> pumpkin patches</h3>
      <div class="project-grid">
        <div class="project-card">
          <h4><i class="fas fa-seedling"></i> sprout-ui</h4>
          <p>Component library with autumn vibes & animations.</p>
          <span class="project-tag"><i class="fas fa-circle" style="color:#c96f3a;"></i> React</span>
          <span class="project-tag"><i class="fas fa-leaf"></i> CSS</span>
        </div>
        <div class="project-card">
          <h4><i class="fas fa-terminal"></i> harvest-cli</h4>
          <p>Rust CLI for dev productivity — fast & cozy.</p>
          <span class="project-tag"><i class="fas fa-cog"></i> Rust</span>
          <span class="project-tag"><i class="fas fa-code"></i> CLI</span>
        </div>
        <div class="project-card">
          <h4><i class="fas fa-chart-pie"></i> gourd-dash</h4>
          <p>Real-time dashboard with D3 & WebSockets.</p>
          <span class="project-tag"><i class="fas fa-chart-line"></i> D3</span>
          <span class="project-tag"><i class="fas fa-bolt"></i> TS</span>
        </div>
      </div>
    </div>

    <!-- ⭐ STEPS SECTION — HOW TO USE THIS REPO -->
    <div class="steps-section">
      <h3><i class="fas fa-footsteps"></i> steps to stand out</h3>
      <div class="step-list">
        <div class="step-item">
          <span class="step-number">1</span>
          <span class="step-content"><i class="fas fa-pen-fancy"></i> <strong>Fork</strong> this repo or copy the <code>README.md</code> template.</span>
        </div>
        <div class="step-item">
          <span class="step-number">2</span>
          <span class="step-content"><i class="fas fa-image"></i> Replace the avatar image (line ~120) with your own GitHub picture.</span>
        </div>
        <div class="step-item">
          <span class="step-number">3</span>
          <span class="step-content"><i class="fas fa-edit"></i> Update <strong>name, bio, stats</strong> and <strong>social links</strong> to match your profile.</span>
        </div>
        <div class="step-item">
          <span class="step-number">4</span>
          <span class="step-content"><i class="fas fa-folder-tree"></i> Customize the <strong>project cards</strong> — add your own repos and tags.</span>
        </div>
        <div class="step-item">
          <span class="step-number">5</span>
          <span class="step-content"><i class="fas fa-code"></i> Paste the HTML into your repo’s <code>index.html</code> or use as a README (with GitHub Pages).</span>
        </div>
        <div class="step-item">
          <span class="step-number">6</span>
          <span class="step-content"><i class="fas fa-rocket"></i> Deploy with <strong>GitHub Pages</strong> — go to Settings > Pages, select branch, and you’re live! 🎃</span>
        </div>
      </div>
    </div>

    <!-- FOOTER -->
    <div class="footer-cta">
      <a href="#" class="cta-button"><i class="fas fa-pumpkin"></i> follow @pumpkinDev</a>
      <a href="#" class="gh-link"><i class="far fa-envelope"></i> pumpkin@dev.io</a>
      <span style="color:#4a2f1e; font-weight:600; background:#f9dbb8; padding:0.1rem 0.8rem; border-radius:40px; border:1px solid #d68f5c; font-size:0.75rem;">
        <i class="fas fa-candy-cane"></i> 2026 · spooky cute
      </span>
    </div>
  </div>

  <script>
    (function() {
      // interactive sparkle on stats
      const stats = document.querySelectorAll('.stat-number');
      stats.forEach(el => {
        el.addEventListener('mouseenter', function() {
          this.style.transform = 'scale(1.1)';
          this.style.background = '#f5cba0';
          this.style.transition = '0.15s';
        });
        el.addEventListener('mouseleave', function() {
          this.style.transform = 'scale(1)';
          this.style.background = '#fbe9d2';
        });
      });
      console.log('🎃 pumpkin repo · ready to stand out!');
    })();
  </script>
</body>
</html>
