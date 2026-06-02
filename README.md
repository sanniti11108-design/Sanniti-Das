# Sanniti-Das

HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Healing Horizon — Pivot Blueprint</title>
  
  <!-- FIX: Corrected Google Fonts CDN Links -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Mono:ital,wght@0,300;0,400;0,500;1,300&family=DM+Sans:ital,opsz,wght@0,9..40,100..1000;1,9..40,100..1000&display=swap" rel="stylesheet">

  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --black: #080808;
      --surface: #0f0f0f;
      --surface2: #161616;
      --surface3: #1e1e1e;
      --border: rgba(255,255,255,0.07);
      --border-bright: rgba(255,255,255,0.14);
      --red: #E8402A;
      --red-dim: rgba(232,64,42,0.12);
      --red-mid: rgba(232,64,42,0.25);
      --amber: #E8A020;
      --amber-dim: rgba(232,160,32,0.10);
      --green: #3DB869;
      --green-dim: rgba(61,184,105,0.10);
      --blue: #3A8FD4;
      --blue-dim: rgba(58,143,212,0.10);
      --text: #E8E6DF;
      --text-muted: #7A7870;
      --text-mid: #AAA89F;
      --font-display: 'Bebas Neue', sans-serif;
      --font-body: 'DM Sans', sans-serif;
      --font-mono: 'DM Mono', monospace;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--black);
      color: var(--text);
      font-family: var(--font-body);
      font-size: 16px;
      line-height: 1.6;
      overflow-x: hidden;
    }

    body::before {
      content: '';
      position: fixed;
      inset: 0;
      pointer-events: none;
      z-index: 9999;
      opacity: 0.025;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
      background-size: 200px 200px;
    }

    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 1.25rem 3rem;
      border-bottom: 1px solid var(--border);
      background: rgba(8,8,8,0.85);
      backdrop-filter: blur(12px);
    }

    .nav-logo {
      font-family: var(--font-mono);
      font-size: 12px;
      font-weight: 500;
      color: var(--text-muted);
      letter-spacing: 0.12em;
      text-transform: uppercase;
    }
    .nav-logo span { color: var(--red); }

    .nav-links {
      display: flex;
      gap: 2.5rem;
      list-style: none;
    }
    .nav-links a {
      font-family: var(--font-mono);
      font-size: 11px;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--text-muted);
      text-decoration: none;
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--text); }

    .hero {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      padding: 8rem 3rem 4rem;
      position: relative;
      overflow: hidden;
    }

    .hero-bg-text {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      font-family: var(--font-display);
      font-size: clamp(180px, 28vw, 380px);
      color: rgba(255,255,255,0.02);
      white-space: nowrap;
      pointer-events: none;
      user-select: none;
      letter-spacing: -0.02em;
    }

    .hero-eyebrow {
      font-family: var(--font-mono);
      font-size: 11px;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--red);
      margin-bottom: 1.5rem;
      display: flex;
      align-items: center;
      gap: 0.75rem;
    }
    .hero-eyebrow::before {
      content: '';
      display: block;
      width: 32px;
      height: 1px;
      background: var(--red);
    }

    .hero-headline {
      font-family: var(--font-display);
      font-size: clamp(72px, 11vw, 160px);
      line-height: 0.92;
      letter-spacing: -0.01em;
      color: var(--text);
      margin-bottom: 2rem;
    }
    .hero-headline .line-red { color: var(--red); }

    .hero-sub {
      max-width: 560px;
      font-size: 17px;
      color: var(--text-muted);
      line-height: 1.7;
      margin-bottom: 3rem;
      font-weight: 300;
    }

    .hero-cta-row {
      display: flex;
      gap: 1rem;
      align-items: center;
      flex-wrap: wrap;
    }

    .btn-primary {
      background: var(--red);
      color: #fff;
      border: none;
      padding: 0.85rem 2rem;
      font-family: var(--font-mono);
      font-size: 12px;
      font-weight: 500;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      cursor: pointer;
      text-decoration: none;
      display: inline-block;
      transition: background 0.2s, transform 0.15s;
    }
    .btn-primary:hover { background: #c93420; transform: translateY(-1px); }

    .btn-ghost {
      background: transparent;
      color: var(--text-muted);
      border: 1px solid var(--border-bright);
      padding: 0.85rem 2rem;
      font-family: var(--font-mono);
      font-size: 12px;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      cursor: pointer;
      text-decoration: none;
      display: inline-block;
      transition: border-color 0.2s, color 0.2s;
    }
    .btn-ghost:hover { border-color: rgba(255,255,255,0.3); color: var(--text); }

    section { padding: 6rem 3rem; }
    section + section { border-top: 1px solid var(--border); }

    .section-label {
      font-family: var(--font-mono);
      font-size: 10px;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--text-muted);
      margin-bottom: 3.5rem;
      display: flex;
      align-items: center;
      gap: 1rem;
    }
    .section-label::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--border);
      max-width: 400px;
    }

    .section-title {
      font-family: var(--font-display);
      font-size: clamp(48px, 6vw, 88px);
      line-height: 0.95;
      letter-spacing: 0.01em;
      margin-bottom: 1.5rem;
    }

    #purge { background: var(--black); }

    .purge-intro {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      margin-bottom: 4rem;
      align-items: start;
    }

    .purge-intro-text {
      font-size: 18px;
      color: var(--text-muted);
      font-weight: 300;
      line-height: 1.7;
    }
    .purge-intro-text strong { color: var(--text); font-weight: 400; }

    .kill-cards {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
    }

    .kill-card {
      background: var(--surface);
      padding: 2rem;
      position: relative;
      overflow: hidden;
      transition: background 0.2s;
    }
    .kill-card:hover { background: var(--surface2); }
    .kill-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 2px;
      background: var(--red);
    }

    .kill-badge {
      display: inline-block;
      font-family: var(--font-mono);
      font-size: 9px;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--red);
      background: var(--red-dim);
      border: 1px solid var(--red-mid);
      padding: 3px 10px;
      margin-bottom: 1.25rem;
    }

    .kill-card h3 {
      font-family: var(--font-display);
      font-size: 32px;
      letter-spacing: 0.02em;
      color: var(--text);
      margin-bottom: 0.75rem;
      line-height: 1;
    }

    .kill-card p {
      font-size: 14px;
      color: var(--text-muted);
      line-height: 1.65;
      font-weight: 300;
    }

    .kill-replace {
      margin-top: 1rem;
      padding-top: 1rem;
      border-top: 1px solid var(--border);
      font-family: var(--font-mono);
      font-size: 11px;
      color: var(--green);
      display: flex;
      align-items: flex-start;
      gap: 8px;
    }
    .kill-replace::before { content: '→'; flex-shrink: 0; }

    .kill-num {
      position: absolute;
      bottom: 1.5rem;
      right: 1.75rem;
      font-family: var(--font-display);
      font-size: 80px;
      color: rgba(232,64,42,0.05);
      line-height: 1;
      pointer-events: none;
    }

    #pivot { background: var(--surface); }

    .pivot-layout {
      display: grid;
      grid-template-columns: 1fr 1.4fr;
      gap: 5rem;
      align-items: start;
    }

    .pivot-left p {
      font-size: 16px;
      color: var(--text-muted);
      line-height: 1.75;
      font-weight: 300;
      margin-bottom: 1.5rem;
    }

    .aria-card {
      background: var(--blue-dim);
      border: 1px solid rgba(58,143,212,0.2);
      padding: 2rem;
      margin-top: 2rem;
    }

    .aria-card-title {
      font-family: var(--font-mono);
      font-size: 10px;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--blue);
      margin-bottom: 1.25rem;
    }

    .aria-quote {
      font-family: var(--font-display);
      font-size: 28px;
      color: var(--text);
      line-height: 1.2;
      letter-spacing: 0.02em;
    }
    .aria-quote span { color: var(--blue); }

    .pivot-tactics {
      display: flex;
      flex-direction: column;
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
    }

    .tactic {
      background: var(--surface2);
      padding: 1.75rem 2rem;
      display: flex;
      gap: 1.5rem;
      align-items: flex-start;
      transition: background 0.2s;
    }
    .tactic:hover { background: var(--surface3); }

    .tactic-icon {
      width: 40px;
      height: 40px;
      background: var(--blue-dim);
      border: 1px solid rgba(58,143,212,0.2);
      display: flex;
      align-items: center;
      justify-content: center;
      flex-shrink: 0;
      font-size: 16px;
    }

    .tactic-body h4 {
      font-family: var(--font-body);
      font-size: 15px;
      font-weight: 500;
      color: var(--text);
      margin-bottom: 0.35rem;
    }

    .tactic-body p {
      font-size: 13px;
      color: var(--text-muted);
      line-height: 1.6;
      font-weight: 300;
    }

    .tactic-tag {
      display: inline-block;
      font-family: var(--font-mono);
      font-size: 9px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--blue);
      background: var(--blue-dim);
      border: 1px solid rgba(58,143,212,0.2);
      padding: 2px 8px;
      margin-left: 8px;
      vertical-align: middle;
    }

    #shield { background: var(--black); }

    .shield-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 2rem;
      margin-top: 1rem;
    }

    .shield-card {
      background: var(--surface);
      border: 1px solid var(--border);
      padding: 2rem;
      position: relative;
      overflow: hidden;
    }

    .shield-card.critical {
      border-color: rgba(232,160,32,0.3);
      background: var(--amber-dim);
    }
    .shield-card.critical::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 2px;
      background: var(--amber);
    }

    .shield-card h3 {
      font-size: 16px;
      font-weight: 500;
      color: var(--text);
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      gap: 0.75rem;
    }

    .shield-badge {
      font-family: var(--font-mono);
      font-size: 9px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--amber);
      background: rgba(232,160,32,0.1);
      border: 1px solid rgba(232,160,32,0.25);
      padding: 2px 8px;
    }
    .shield-badge.green {
      color: var(--green);
      background: var(--green-dim);
      border-color: rgba(61,184,105,0.25);
    }

    .shield-card p, .shield-card li {
      font-size: 14px;
      color: var(--text-muted);
      line-height: 1.7;
      font-weight: 300;
    }

    .shield-card ul {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 0.6rem;
    }

    .shield-card li {
      display: flex;
      gap: 10px;
      align-items: flex-start;
    }
    .shield-card li::before {
      content: '×';
      color: var(--red);
      font-weight: 400;
      flex-shrink: 0;
      margin-top: 1px;
    }
    .shield-card li.ok::before {
      content: '→';
      color: var(--green);
    }

    .crisis-modal-preview {
      background: #000;
      border: 1px solid rgba(232,160,32,0.4);
      padding: 1.5rem;
      margin-top: 1.25rem;
      text-align: center;
    }

    .crisis-modal-preview .crisis-title {
      font-family: var(--font-display);
      font-size: 22px;
      color: var(--amber);
      letter-spacing: 0.05em;
      margin-bottom: 0.5rem;
    }

    .crisis-modal-preview .crisis-body {
      font-size: 13px;
      color: #888;
      margin-bottom: 1rem;
    }

    .crisis-btn {
      display: block;
      background: var(--amber);
      color: #000;
      font-family: var(--font-mono);
      font-size: 12px;
      font-weight: 500;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      padding: 0.75rem 1.5rem;
      border: none;
      cursor: pointer;
      width: 100%;
      margin-bottom: 0.5rem;
    }

    .crisis-note {
      font-family: var(--font-mono);
      font-size: 10px;
      color: #555;
      letter-spacing: 0.08em;
    }

    #choice { background: var(--surface); }

    .choice-split {
      display: grid;
      grid-template-columns: 1fr 1fr;
      border: 1px solid var(--border);
      margin-top: 2rem;
    }

    .choice-panel {
      padding: 3rem;
      position: relative;
      overflow: hidden;
      transition: background 0.25s;
    }

    .choice-panel.bad {
      border-right: 1px solid var(--border);
      background: var(--red-dim);
    }
    .choice-panel.bad:hover { background: rgba(232,64,42,0.18); }

    .choice-panel.good { background: var(--green-dim); }
    .choice-panel.good:hover { background: rgba(61,184,105,0.16); }

    .choice-panel::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 3px;
    }
    .choice-panel.bad::before { background: var(--red); }
    .choice-panel.good::before { background: var(--green); }

    .choice-label {
      font-family: var(--font-mono);
      font-size: 10px;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      margin-bottom: 1.5rem;
    }
    .bad .choice-label { color: var(--red); }
    .good .choice-label { color: var(--green); }

    .choice-title {
      font-family: var(--font-display);
      font-size: clamp(36px, 4vw, 56px);
      line-height: 1;
      letter-spacing: 0.02em;
      margin-bottom: 1.25rem;
      color: var(--text);
    }

    .choice-desc {
      font-size: 15px;
      color: var(--text-muted);
      line-height: 1.7;
      font-weight: 300;
      margin-bottom: 2rem;
    }

    .choice-consequences {
      display: flex;
      flex-direction: column;
      gap: 0.6rem;
      margin-bottom: 2rem;
    }

    .consequence {
      font-family: var(--font-mono);
      font-size: 12px;
    }
    .consequence.bad-item { color: rgba(232,64,42,0.7); }
    .consequence.good-item { color: rgba(61,184,105,0.8); }

    .choice-verdict {
      font-family: var(--font-display);
      font-size: 48px;
      letter-spacing: 0.05em;
      line-height: 1;
    }
    .bad .choice-verdict { color: var(--red); }
    .good .choice-verdict { color: var(--green); }

    .choice-bg-num {
      position: absolute;
      bottom: -10px;
      right: 2rem;
      font-family: var(--font-display);
      font-size: 180px;
      line-height: 1;
      opacity: 0.04;
      pointer-events: none;
    }
    .bad .choice-bg-num { color: var(--red); }
    .good .choice-bg-num { color: var(--green); }

    footer {
      border-top: 1px solid var(--border);
      padding: 3rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .footer-logo {
      font-family: var(--font-mono);
      font-size: 11px;
      color: var(--text-muted);
      letter-spacing: 0.1em;
      text-transform: uppercase;
    }
    .footer-logo span { color: var(--red); }

    .footer-note {
      font-family: var(--font-mono);
      font-size: 10px;
      color: var(--text-muted);
      letter-spacing: 0.08em;
    }

    /* Scroll Engine Adjustments */
    .fade-in {
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.6s cubic-bezier(0.16, 1, 0.3, 1), transform 0.6s cubic-bezier(0.16, 1, 0.3, 1);
    }
    .fade-in.visible {
      opacity: 1;
      transform: translateY(0);
    }

    @media (max-width: 900px) {
      .kill-cards { grid-template-columns: 1fr; }
      .pivot-layout { grid-template-columns: 1fr; gap: 3rem; }
    }

    @media (max-width: 768px) {
      nav { padding: 1rem 1.5rem; }
      .nav-links { display: none; }
      .hero { padding: 7rem 1.5rem 3rem; }
      section { padding: 4rem 1.5rem; }
      .purge-intro { grid-template-columns: 1fr; gap: 2rem; }
      .shield-grid { grid-template-columns: 1fr; }
      .choice-split { grid-template-columns: 1fr; }
      .choice-panel.bad { border-right: none; border-bottom: 1px solid var(--border); }
      footer { padding: 2rem 1.5rem; }
    }
  </style>
</head>
<body>

<!-- FIX: Relative Anchors applied -->
<nav>
  <div class="nav-logo"><span>HH</span> / Healing Horizon</div>
  <ul class="nav-links">
    <li><a href="#purge">Phase 1: Purge</a></li>
    <li><a href="#pivot">Phase 2: Pivot</a></li>
    <li><a href="#shield">Phase 3: Shield</a></li>
    <li><a href="#choice">The Choice</a></li>
  </ul>
</nav>

<section class="hero">
  <div class="hero-bg-text">SURGERY</div>
  <div class="hero-eyebrow">Pivot blueprint — internal document</div>
  <h1 class="hero-headline">Stop<br><span class="line-red">boiling</span><br>the ocean.</h1>
  <p class="hero-sub">You are building software, not running a hospital. Strip the dead weight, double down on Aria, and install the legal guardrails before you touch another line of code.</p>
  <div class="hero-cta-row">
    <a href="#purge" class="btn-primary">Start the surgery</a>
    <a href="#choice" class="btn-ghost">See the choice</a>
  </div>
</section>

<section id="purge">
  <div class="section-label">Phase 1 of 3 — The Purge</div>
  <div class="purge-intro">
    <div><h2 class="section-title" style="color: var(--red);">Kill the<br>dead weight.</h2></div>
    <div>
      <p class="purge-intro-text">Every feature you add <strong>dilutes your core value.</strong> Cut the scope creep that's killing your focus before it kills your runway.</p>
      <p class="purge-intro-text">Three things must go. Now. Not in the next sprint — <strong>today.</strong></p>
    </div>
  </div>

  <div class="kill-cards">
    <div class="kill-card fade-in">
      <div class="kill-badge">Kill immediately</div>
      <h3>Utopic World</h3>
      <p>Building a 3D or immersive VR space is an entirely different company. It requires a hardware supply chain, spatial UX, 3D assets, and latency engineering you don't have.</p>
      <div class="kill-replace">It's a distraction. Drop it entirely.</div>
      <div class="kill-num">01</div>
    </div>
    <div class="kill-card fade-in">
      <div class="kill-badge">Kill immediately</div>
      <h3>Influencers</h3>
      <p>Remove Chetan Bhagat and Sandeep Maheshwari. Pop-motivation and fiction writers compromise clinical credibility. One headline connecting them to your mental health tool ends you.</p>
      <div class="kill-replace">Keep only certified clinical psychologists and legitimate NGOs.</div>
      <div class="kill-num">02</div>
    </div>
    <div class="kill-card fade-in">
      <div class="kill-badge">Kill &amp; replace</div>
      <h3>Gamification badges</h3>
      <p>"Mood Master" and "Horizon Hero" trivialize the experience. Users don't need cartoon sprouts. They need data they can show their actual doctor.</p>
      <div class="kill-replace">Replace with a clean 30-day emotional baseline dashboard — private, clinical, shareable.</div>
      <div class="kill-num">03</div>
    </div>
  </div>
</section>

<section id="pivot">
  <div class="section-label">Phase 2 of 3 — The Pivot</div>
  <div class="pivot-layout">
    <div class="pivot-left">
      <h2 class="section-title">Double<br>down on<br><span style="color: var(--blue);">Aria.</span></h2>
      <p>Your strongest asset is being positioned wrong. It cannot be a therapist. It must be a <strong style="color: var(--text); font-weight: 500;">Triage and Coping Engine.</strong></p>
      <p>The reframe is everything. "Mental Wellness Companion" for non-clinical stress, burnout, and emotional venting. You become the place people go <em>before</em> they need a doctor.</p>
      <div class="aria-card">
        <div class="aria-card-title">Aria's new positioning</div>
        <div class="aria-quote">"You are <span>the funnel</span>,<br>not the provider."</div>
      </div>
    </div>

    <div class="pivot-tactics">
      <div class="tactic fade-in">
        <div class="tactic-icon">🧠</div>
        <div class="tactic-body">
          <h4>CBT journaling prompts <span class="tactic-tag">Clinical-grade</span></h4>
          <p>Structured Cognitive Behavioral Therapy prompts — not just listening. Aria guides users through frameworks, not vibes.</p>
        </div>
      </div>
      <div class="tactic fade-in">
        <div class="tactic-icon">🫁</div>
        <div class="tactic-body">
          <h4>4-7-8 breathing exercises <span class="tactic-tag">Evidence-backed</span></h4>
          <p>Rendered as a timed visual in-UI — not just text instructions. Measurable, evidence-backed, and legally defensible as a wellness tool.</p>
        </div>
      </div>
      <div class="tactic fade-in">
        <div class="tactic-icon">📋</div>
        <div class="tactic-body">
          <h4>Cognitive task offloading <span class="tactic-tag">Utility</span></h4>
          <p>Help users organize an overwhelming task list by urgency and energy cost. Focus on cognitive relief, not medical treatment.</p>
        </div>
      </div>
      <div class="tactic fade-in">
        <div class="tactic-icon">🔗</div>
        <div class="tactic-body">
          <h4>API handoff to Practo / MFine <span class="tactic-tag">Partner</span></h4>
          <p>Integrate, don't build the marketplace. Route users to existing clinical platforms when Aria detects needs beyond digital coping.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="shield">
  <div class="section-label">Phase 3 of 3 — The Shield</div>
  <h2 class="section-title" style="color: var(--amber); margin-bottom: 0.5rem;">Legal<br>guardrails.</h2>
  <p style="color: var(--text-muted); font-size: 16px; margin-bottom: 3rem; font-weight: 300; max-width: 540px;">You are operating in a high-risk sector. One adverse event without these in place ends the company.</p>

  <div class="shield-grid">
    <div class="shield-card critical fade-in">
      <h3><span class="shield-badge">CRITICAL — hardcode this</span></h3>
      <h3 style="font-family: var(--font-display); font-size: 28px; letter-spacing: 0.02em; margin-bottom: 1rem; margin-top: 0.5rem;">The Hard Kill-Switch</h3>
      <p style="margin-bottom: 1rem;">Detect high-risk keywords: <code style="font-family: var(--font-mono); font-size: 12px; color: var(--amber);">suicide / self-harm / ending it</code></p>
      <p style="margin-bottom: 1rem;">The AI must stop text generation immediately and deploy an un-closable modal.</p>
      <div class="crisis-modal-preview">
        <div class="crisis-title">You are not alone.</div>
        <div class="crisis-body">A real person is available right now. Please reach out.</div>
        <button class="crisis-btn">📞 iCall — 9152987821</button>
        <button class="crisis-btn" style="background: var(--surface); color: var(--text); border: 1px solid rgba(232,160,32,0.3); margin-top: 0;">📞 Vandrevala Foundation — 1860-2662-345</button>
      </div>
    </div>

    <div style="display: flex; flex-direction: column; gap: 2rem;">
      <div class="shield-card fade-in">
        <h3>Sanitize all copy <span class="shield-badge green">Legal</span></h3>
        <ul style="margin-top: 1rem;">
          <li>What we <del style="opacity:0.5">treat</del></li>
          <li class="ok">What we <strong style="color: var(--text);">support</strong></li>
          <li class="ok">We provide <strong style="color: var(--text);">management and support</strong> — nothing more</li>
        </ul>
      </div>
      <div class="shield-card fade-in">
        <h3>The clinical handoff <span class="shield-badge green">Architecture</span></h3>
        <p>In India, the Mental Healthcare Act 2017 and DPDP Act create real exposure. Your marketing copy is the first thing regulators read. Use affiliate routing seamlessly.</p>
      </div>
    </div>
  </div>
</section>

<section id="choice">
  <div class="section-label">The decision</div>
  <h2 class="section-title" style="margin-bottom: 0.5rem;">You have a choice<br>to make right now.</h2>
  
  <div class="choice-split">
    <div class="choice-panel bad fade-in">
      <div class="choice-label">Option A — The wrong move</div>
      <div class="choice-title">Boil<br>the ocean.</div>
      <p class="choice-desc">Full clinical directory + VR + influencers + gamification.</p>
      <div class="choice-verdict">DIES.</div>
      <div class="choice-bg-num">A</div>
    </div>
    <div class="choice-panel good fade-in">
      <div class="choice-label">Option B — The only move</div>
      <div class="choice-title">Hyper-focused<br>AI triage.</div>
      <p class="choice-desc">Aria as the product. Strict non-clinical positioning. Utility tracking.</p>
      <div class="choice-verdict">LIVES.</div>
      <div class="choice-bg-num">B</div>
    </div>
  </div>
</section>

<footer>
  <div class="footer-logo"><span>HH</span> — Healing Horizon Pivot Blueprint</div>
  <div class="footer-note">Internal document · Not for distribution</div>
</footer>

<script>
  // Robust Intersection Observer for smooth styling reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
      }
    });
  }, { threshold: 0.05, rootMargin: '0px 0px -20px 0px' });

  document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));
</script>

</body>
</html>
