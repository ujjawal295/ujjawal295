<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Ujjawal Pandey — Developer Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@300;400;500;700&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#020813;
  --bg2:#060f1e;
  --bg3:#0a1628;
  --card:#0d1b2e;
  --card2:#111f33;
  --border:#1a2f4a;
  --border2:#1f3854;
  --cyan:#00f5ff;
  --cyan2:#00c4cc;
  --green:#00ff88;
  --green2:#00cc6a;
  --amber:#f5a623;
  --pink:#f472b6;
  --purple:#a78bfa;
  --blue:#3b82f6;
  --red:#ff4d6d;
  --text:#e2f0ff;
  --text2:#7ba7c7;
  --text3:#3d6080;
  --font:'Space Grotesk',sans-serif;
  --mono:'JetBrains Mono',monospace;
}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--text);font-family:var(--font);overflow-x:hidden;min-height:100vh}

/* ANIMATED BACKGROUND */
.bg-grid{position:fixed;inset:0;background-image:linear-gradient(var(--border) 1px,transparent 1px),linear-gradient(90deg,var(--border) 1px,transparent 1px);background-size:40px 40px;opacity:.15;pointer-events:none;z-index:0}
.bg-glow{position:fixed;top:-20%;left:50%;transform:translateX(-50%);width:800px;height:800px;background:radial-gradient(circle,rgba(0,245,255,.04) 0%,transparent 70%);pointer-events:none;z-index:0}
.bg-glow2{position:fixed;bottom:-20%;right:-10%;width:600px;height:600px;background:radial-gradient(circle,rgba(0,255,136,.03) 0%,transparent 70%);pointer-events:none;z-index:0}

/* CONTENT */
.wrap{position:relative;z-index:1;max-width:1000px;margin:0 auto;padding:0 24px 80px}

/* ── HERO ── */
.hero{padding:80px 0 60px;text-align:center;position:relative}
.hero-badge{display:inline-flex;align-items:center;gap:8px;background:rgba(0,245,255,.07);border:1px solid rgba(0,245,255,.2);border-radius:100px;padding:6px 16px;font-family:var(--mono);font-size:12px;color:var(--cyan);margin-bottom:28px;animation:fadein .8s ease both}
.hero-badge .dot{width:6px;height:6px;border-radius:50%;background:var(--green);animation:pulse 2s infinite}
.hero h1{font-size:clamp(40px,7vw,76px);font-weight:700;letter-spacing:-2px;line-height:1;margin-bottom:16px;animation:fadein .8s .1s ease both}
.hero h1 .name-u{color:transparent;-webkit-text-stroke:1px var(--cyan);text-stroke:1px var(--cyan)}
.hero h1 .name-rest{color:var(--text)}
.hero-sub{font-family:var(--mono);font-size:14px;color:var(--text2);margin-bottom:36px;animation:fadein .8s .2s ease both;min-height:22px}
.cursor-blink{animation:blink 1s step-end infinite;color:var(--cyan)}
.hero-tags{display:flex;flex-wrap:wrap;gap:10px;justify-content:center;animation:fadein .8s .3s ease both;margin-bottom:40px}
.tag{display:inline-flex;align-items:center;gap:6px;padding:7px 14px;border-radius:100px;border:1px solid var(--border2);background:var(--card);font-size:12px;font-family:var(--mono);color:var(--text2);transition:all .2s;cursor:default}
.tag:hover{border-color:var(--cyan);color:var(--cyan);background:rgba(0,245,255,.05);transform:translateY(-2px)}
.tag .dot{width:5px;height:5px;border-radius:50%}
.hero-cta{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;animation:fadein .8s .4s ease both}
.btn{display:inline-flex;align-items:center;gap:8px;padding:12px 24px;border-radius:10px;font-size:14px;font-weight:500;cursor:pointer;transition:all .2s;text-decoration:none;font-family:var(--font)}
.btn-primary{background:var(--cyan);color:#020813;border:none}
.btn-primary:hover{background:#33f8ff;transform:translateY(-2px);box-shadow:0 8px 32px rgba(0,245,255,.3)}
.btn-outline{background:transparent;color:var(--text);border:1px solid var(--border2)}
.btn-outline:hover{border-color:var(--cyan);color:var(--cyan);transform:translateY(-2px)}

/* ── STATS BAR ── */
.stats-bar{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;background:var(--border);border-radius:16px;overflow:hidden;margin:60px 0;border:1px solid var(--border)}
.stat-item{background:var(--card);padding:28px 20px;text-align:center;transition:background .2s}
.stat-item:hover{background:var(--card2)}
.stat-val{font-size:32px;font-weight:700;font-family:var(--mono);color:var(--cyan);line-height:1;display:block;margin-bottom:6px}
.stat-label{font-size:12px;color:var(--text2);font-family:var(--mono)}

/* ── SECTION ── */
.section{margin:60px 0}
.section-head{display:flex;align-items:center;gap:14px;margin-bottom:32px}
.section-head h2{font-size:22px;font-weight:600;letter-spacing:-.5px}
.section-head .line{flex:1;height:1px;background:linear-gradient(90deg,var(--border2),transparent)}
.section-head .icon{width:36px;height:36px;border-radius:10px;background:rgba(0,245,255,.08);border:1px solid rgba(0,245,255,.2);display:flex;align-items:center;justify-content:center;font-size:16px;flex-shrink:0}

/* ── TERMINAL ── */
.terminal{background:var(--card);border:1px solid var(--border2);border-radius:16px;overflow:hidden;margin-bottom:20px}
.term-bar{display:flex;align-items:center;gap:8px;padding:12px 16px;background:var(--card2);border-bottom:1px solid var(--border)}
.term-dot{width:12px;height:12px;border-radius:50%}
.term-title{font-family:var(--mono);font-size:11px;color:var(--text3);margin-left:8px}
.term-body{padding:20px 24px;font-family:var(--mono);font-size:13px;line-height:1.9}
.term-body .prompt{color:var(--green)}
.term-body .cmd{color:var(--text)}
.term-body .key{color:var(--cyan)}
.term-body .val{color:var(--amber)}
.term-body .str{color:var(--green2)}
.term-body .comment{color:var(--text3)}
.term-body .bracket{color:var(--text2)}

/* ── SKILL GRID ── */
.skill-tabs{display:flex;gap:4px;margin-bottom:20px;background:var(--card);padding:4px;border-radius:12px;border:1px solid var(--border)}
.skill-tab{flex:1;padding:9px;text-align:center;border-radius:9px;font-size:12px;font-family:var(--mono);color:var(--text2);cursor:pointer;transition:all .2s;border:none;background:transparent}
.skill-tab.active{background:var(--cyan);color:#020813;font-weight:600}
.skill-tab:hover:not(.active){color:var(--cyan);background:rgba(0,245,255,.06)}
.skill-panel{display:none;grid-template-columns:repeat(auto-fill,minmax(140px,1fr));gap:10px}
.skill-panel.active{display:grid}
.skill-card{background:var(--card);border:1px solid var(--border);border-radius:12px;padding:14px 12px;display:flex;align-items:center;gap:10px;cursor:default;transition:all .25s;position:relative;overflow:hidden}
.skill-card::before{content:'';position:absolute;inset:0;background:linear-gradient(135deg,rgba(0,245,255,.03),transparent);opacity:0;transition:.2s}
.skill-card:hover{border-color:var(--border2);transform:translateY(-2px)}
.skill-card:hover::before{opacity:1}
.skill-icon{font-size:22px;flex-shrink:0}
.skill-name{font-size:12px;font-weight:500;color:var(--text)}
.skill-level{font-size:10px;font-family:var(--mono);color:var(--text3);margin-top:2px}
.skill-bar{position:absolute;bottom:0;left:0;height:2px;border-radius:0 2px 2px 0;transition:width .6s cubic-bezier(.4,0,.2,1)}

/* ── PROJECTS ── */
.projects-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:16px}
.proj-card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:24px;transition:all .25s;cursor:pointer;position:relative;overflow:hidden}
.proj-card::after{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,var(--cyan),transparent);transform:scaleX(0);transition:.3s;transform-origin:left}
.proj-card:hover{border-color:var(--border2);transform:translateY(-4px);box-shadow:0 20px 60px rgba(0,0,0,.4)}
.proj-card:hover::after{transform:scaleX(1)}
.proj-header{display:flex;align-items:flex-start;justify-content:space-between;margin-bottom:12px}
.proj-icon{font-size:24px}
.proj-stars{font-family:var(--mono);font-size:11px;color:var(--amber);display:flex;align-items:center;gap:4px}
.proj-name{font-size:15px;font-weight:600;margin-bottom:8px;color:var(--text)}
.proj-desc{font-size:13px;color:var(--text2);line-height:1.6;margin-bottom:16px}
.proj-tags{display:flex;flex-wrap:wrap;gap:6px}
.proj-tag{padding:3px 10px;border-radius:100px;font-family:var(--mono);font-size:10px;border:1px solid}

/* ── COMPETITIVE ── */
.platforms-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:12px}
.platform-card{background:var(--card);border:1px solid var(--border);border-radius:14px;padding:20px;transition:all .25s;cursor:pointer;text-decoration:none;display:block}
.platform-card:hover{transform:translateY(-3px);box-shadow:0 12px 40px rgba(0,0,0,.3)}
.platform-logo{font-size:28px;margin-bottom:10px;display:block}
.platform-name{font-size:14px;font-weight:600;margin-bottom:4px}
.platform-stat{font-family:var(--mono);font-size:12px;color:var(--text2)}
.platform-rank{font-family:var(--mono);font-size:11px;margin-top:8px;padding:4px 10px;border-radius:100px;display:inline-block;font-weight:500}

/* ── ACTIVITY GRAPH ── */
.activity-grid{display:grid;grid-template-columns:repeat(52,1fr);gap:3px;margin:16px 0}
.act-cell{aspect-ratio:1;border-radius:3px;transition:transform .1s}
.act-cell:hover{transform:scale(1.4)}
.act-0{background:var(--card2)}
.act-1{background:#0d3f2a}
.act-2{background:#0a6b3e}
.act-3{background:#00aa60}
.act-4{background:var(--green)}

/* ── CONTACT ── */
.contact-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:12px}
.contact-card{display:flex;align-items:center;gap:14px;background:var(--card);border:1px solid var(--border);border-radius:14px;padding:18px;text-decoration:none;transition:all .25s}
.contact-card:hover{border-color:var(--border2);transform:translateY(-2px)}
.contact-icon{width:42px;height:42px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:20px;flex-shrink:0}
.contact-label{font-size:11px;color:var(--text3);font-family:var(--mono);margin-bottom:2px}
.contact-val{font-size:14px;font-weight:500;color:var(--text)}

/* ── CURRENTLY ── */
.mission-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
.mission-card{background:var(--card);border:1px solid var(--border);border-radius:14px;padding:18px;display:flex;gap:14px;align-items:flex-start;transition:all .2s}
.mission-card:hover{border-color:var(--border2)}
.mission-icon{font-size:22px;flex-shrink:0;margin-top:2px}
.mission-title{font-size:13px;font-weight:600;color:var(--text);margin-bottom:4px}
.mission-text{font-size:12px;color:var(--text2);line-height:1.5;font-family:var(--mono)}

/* ── FOOTER ── */
.footer{text-align:center;padding:40px 0 20px;border-top:1px solid var(--border);margin-top:80px}
.footer-text{font-family:var(--mono);font-size:12px;color:var(--text3)}
.footer-glow{font-size:18px;font-weight:600;color:var(--cyan);margin-bottom:8px}

/* ── ANIMATIONS ── */
@keyframes fadein{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:translateY(0)}}
@keyframes pulse{0%,100%{opacity:1;box-shadow:0 0 0 0 rgba(0,255,136,.4)}50%{box-shadow:0 0 0 6px rgba(0,255,136,0)}}
@keyframes blink{0%,49%{opacity:1}50%,100%{opacity:0}}
@keyframes scan{0%{top:-2px}100%{top:100%}}
@keyframes counter{from{opacity:0;transform:scale(.8)}to{opacity:1;transform:scale(1)}}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-6px)}}
.float{animation:float 4s ease-in-out infinite}

/* SCROLL REVEAL */
.reveal{opacity:0;transform:translateY(30px);transition:opacity .6s ease,transform .6s ease}
.reveal.visible{opacity:1;transform:none}

/* NAV */
.nav{position:fixed;top:0;left:0;right:0;z-index:100;background:rgba(2,8,19,.85);backdrop-filter:blur(20px);border-bottom:1px solid var(--border);padding:14px 24px;display:flex;justify-content:space-between;align-items:center}
.nav-brand{font-family:var(--mono);font-size:14px;color:var(--cyan);font-weight:700;letter-spacing:.05em}
.nav-links{display:flex;gap:24px}
.nav-link{font-size:13px;color:var(--text2);text-decoration:none;font-family:var(--mono);transition:color .2s}
.nav-link:hover{color:var(--cyan)}
.nav-status{display:flex;align-items:center;gap:6px;font-family:var(--mono);font-size:11px;color:var(--green)}
.nav-status .dot{width:6px;height:6px;border-radius:50%;background:var(--green);animation:pulse 2s infinite}

/* GLITCH */
.glitch{position:relative}
.glitch::before,.glitch::after{content:attr(data-text);position:absolute;inset:0;font-size:inherit;font-weight:inherit;letter-spacing:inherit}
.glitch::before{color:var(--pink);clip-path:polygon(0 30%,100% 30%,100% 50%,0 50%);animation:glitch1 4s infinite}
.glitch::after{color:var(--cyan);clip-path:polygon(0 60%,100% 60%,100% 75%,0 75%);animation:glitch2 4s infinite}
@keyframes glitch1{0%,90%,100%{transform:none;opacity:0}92%{transform:translate(-2px,1px);opacity:.7}94%{transform:translate(2px,-1px);opacity:.5}96%{transform:translate(-1px,0);opacity:.6}98%{transform:none;opacity:0}}
@keyframes glitch2{0%,90%,100%{transform:none;opacity:0}93%{transform:translate(2px,1px);opacity:.6}95%{transform:translate(-2px,-1px);opacity:.4}97%{transform:translate(1px,0);opacity:.5}99%{transform:none;opacity:0}}

@media(max-width:640px){
  .stats-bar{grid-template-columns:repeat(2,1fr)}
  .mission-grid{grid-template-columns:1fr}
  .nav-links{display:none}
  .activity-grid{grid-template-columns:repeat(26,1fr)}
}
</style>
</head>
<body>

<!-- BACKGROUND -->
<div class="bg-grid"></div>
<div class="bg-glow"></div>
<div class="bg-glow2"></div>

<!-- NAV -->
<nav class="nav">
  <span class="nav-brand">UP.dev</span>
  <div class="nav-links">
    <a href="#about" class="nav-link">about</a>
    <a href="#skills" class="nav-link">skills</a>
    <a href="#projects" class="nav-link">projects</a>
    <a href="#competitive" class="nav-link">cp</a>
    <a href="#contact" class="nav-link">contact</a>
  </div>
  <div class="nav-status"><div class="dot"></div>available</div>
</nav>

<div class="wrap" style="padding-top:70px">

  <!-- HERO -->
  <div class="hero" id="about">
    <div class="hero-badge"><div class="dot"></div>Open to Opportunities — 2024</div>
    <h1>
      <span class="glitch name-u" data-text="Ujjawal">Ujjawal</span><br/>
      <span class="name-rest">Pandey</span>
    </h1>
    <div class="hero-sub" id="typewriter"></div>
    <div class="hero-tags">
      <span class="tag"><span class="dot" style="background:var(--cyan)"></span>Full Stack Dev</span>
      <span class="tag"><span class="dot" style="background:var(--green)"></span>AI Builder</span>
      <span class="tag"><span class="dot" style="background:var(--purple)"></span>CS @ Parul University</span>
      <span class="tag"><span class="dot" style="background:var(--amber)"></span>Competitive Programmer</span>
      <span class="tag"><span class="dot" style="background:var(--pink)"></span>Open Source</span>
      <span class="tag"><span class="dot" style="background:var(--blue)"></span>Gujarat, India 🇮🇳</span>
    </div>
    <div class="hero-cta">
      <a href="https://github.com/ujjawal295" class="btn btn-primary" target="_blank">⚡ GitHub Profile</a>
      <a href="https://linkedin.com/in/pandeyujjawal" class="btn btn-outline" target="_blank">↗ LinkedIn</a>
      <a href="mailto:ujjawalpandey073@gmail.com" class="btn btn-outline">✉ Email me</a>
    </div>
  </div>

  <!-- STATS BAR -->
  <div class="stats-bar reveal">
    <div class="stat-item">
      <span class="stat-val" id="s1">0</span>
      <span class="stat-label">Projects Built</span>
    </div>
    <div class="stat-item">
      <span class="stat-val" id="s2">0</span>
      <span class="stat-label">LeetCode Solved</span>
    </div>
    <div class="stat-item">
      <span class="stat-val" id="s3">0</span>
      <span class="stat-label">Contributions</span>
    </div>
    <div class="stat-item">
      <span class="stat-val" id="s4">0</span>
      <span class="stat-label">Tech Stack</span>
    </div>
  </div>

  <!-- ABOUT / TERMINAL -->
  <div class="section reveal">
    <div class="section-head">
      <div class="icon">🖥</div>
      <h2>whoami</h2>
      <div class="line"></div>
    </div>
    <div class="terminal">
      <div class="term-bar">
        <div class="term-dot" style="background:#ff5f57"></div>
        <div class="term-dot" style="background:#febc2e"></div>
        <div class="term-dot" style="background:#28c840"></div>
        <span class="term-title">ujjawal@portfolio — bash — 80×24</span>
      </div>
      <div class="term-body" id="terminal-content">
        <div><span class="prompt">➜</span> <span class="cmd">cat ujjawal.json</span></div>
        <br/>
        <div class="bracket">{</div>
        <div>&nbsp;&nbsp;<span class="key">"name"</span>: <span class="str">"Ujjawal Pandey"</span>,</div>
        <div>&nbsp;&nbsp;<span class="key">"role"</span>: <span class="str">"Full Stack Developer + AI Engineer"</span>,</div>
        <div>&nbsp;&nbsp;<span class="key">"university"</span>: <span class="str">"Parul University, Gujarat"</span>,</div>
        <div>&nbsp;&nbsp;<span class="key">"degree"</span>: <span class="str">"B.Tech Computer Science"</span>,</div>
        <div>&nbsp;&nbsp;<span class="key">"focus"</span>: [<span class="str">"MERN Stack"</span>, <span class="str">"AI/ML"</span>, <span class="str">"DSA"</span>, <span class="str">"Open Source"</span>],</div>
        <div>&nbsp;&nbsp;<span class="key">"currently"</span>: <span class="str">"Building AI-powered web apps 🚀"</span>,</div>
        <div>&nbsp;&nbsp;<span class="key">"goal"</span>: <span class="str">"Top-tier Software + AI Engineer 🏆"</span>,</div>
        <div>&nbsp;&nbsp;<span class="key">"hobbies"</span>: [<span class="str">"CP"</span>, <span class="str">"Hackathons"</span>, <span class="str">"Tech Blogs"</span>],</div>
        <div>&nbsp;&nbsp;<span class="key">"available"</span>: <span class="val">true</span></div>
        <div class="bracket">}</div>
        <br/>
        <div><span class="prompt">➜</span> <span class="cmd">echo $MISSION</span></div>
        <div style="color:var(--cyan)">→ Build scalable, impactful products. Grind DSA. Ship AI.</div>
        <br/>
        <div><span class="prompt">➜</span> <span class="cursor-blink">█</span></div>
      </div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="section reveal" id="skills">
    <div class="section-head">
      <div class="icon">⚙</div>
      <h2>Tech Arsenal</h2>
      <div class="line"></div>
    </div>
    <div class="skill-tabs">
      <button class="skill-tab active" onclick="switchTab('lang')">Languages</button>
      <button class="skill-tab" onclick="switchTab('frontend')">Frontend</button>
      <button class="skill-tab" onclick="switchTab('backend')">Backend</button>
      <button class="skill-tab" onclick="switchTab('ai')">AI / ML</button>
      <button class="skill-tab" onclick="switchTab('tools')">Tools</button>
    </div>
    <div class="skill-panel active" id="panel-lang">
      <div class="skill-card"><span class="skill-icon">🔷</span><div><div class="skill-name">C / C++</div><div class="skill-level">Advanced</div></div><div class="skill-bar" style="background:#00f5ff;width:90%"></div></div>
      <div class="skill-card"><span class="skill-icon">🐍</span><div><div class="skill-name">Python</div><div class="skill-level">Advanced</div></div><div class="skill-bar" style="background:#f5a623;width:88%"></div></div>
      <div class="skill-card"><span class="skill-icon">🟡</span><div><div class="skill-name">JavaScript</div><div class="skill-level">Advanced</div></div><div class="skill-bar" style="background:#f5a623;width:92%"></div></div>
      <div class="skill-card"><span class="skill-icon">☕</span><div><div class="skill-name">Java</div><div class="skill-level">Intermediate</div></div><div class="skill-bar" style="background:#f472b6;width:70%"></div></div>
    </div>
    <div class="skill-panel" id="panel-frontend">
      <div class="skill-card"><span class="skill-icon">⚛</span><div><div class="skill-name">React.js</div><div class="skill-level">Advanced</div></div><div class="skill-bar" style="background:#61dafb;width:92%"></div></div>
      <div class="skill-card"><span class="skill-icon">🎨</span><div><div class="skill-name">Tailwind CSS</div><div class="skill-level">Advanced</div></div><div class="skill-bar" style="background:#38bdf8;width:88%"></div></div>
      <div class="skill-card"><span class="skill-icon">🌐</span><div><div class="skill-name">HTML / CSS</div><div class="skill-level">Advanced</div></div><div class="skill-bar" style="background:#f5a623;width:95%"></div></div>
      <div class="skill-card"><span class="skill-icon">🅱</span><div><div class="skill-name">Bootstrap</div><div class="skill-level">Intermediate</div></div><div class="skill-bar" style="background:#a78bfa;width:78%"></div></div>
    </div>
    <div class="skill-panel" id="panel-backend">
      <div class="skill-card"><span class="skill-icon">🟢</span><div><div class="skill-name">Node.js</div><div class="skill-level">Advanced</div></div><div class="skill-bar" style="background:#00ff88;width:88%"></div></div>
      <div class="skill-card"><span class="skill-icon">🚂</span><div><div class="skill-name">Express.js</div><div class="skill-level">Advanced</div></div><div class="skill-bar" style="background:#00ff88;width:85%"></div></div>
      <div class="skill-card"><span class="skill-icon">🍃</span><div><div class="skill-name">MongoDB</div><div class="skill-level">Advanced</div></div><div class="skill-bar" style="background:#4eff91;width:82%"></div></div>
      <div class="skill-card"><span class="skill-icon">🐬</span><div><div class="skill-name">MySQL</div><div class="skill-level">Intermediate</div></div><div class="skill-bar" style="background:#00aabf;width:72%"></div></div>
      <div class="skill-card"><span class="skill-icon">🔥</span><div><div class="skill-name">Firebase</div><div class="skill-level">Intermediate</div></div><div class="skill-bar" style="background:#f5a623;width:68%"></div></div>
    </div>
    <div class="skill-panel" id="panel-ai">
      <div class="skill-card"><span class="skill-icon">🧠</span><div><div class="skill-name">TensorFlow</div><div class="skill-level">Intermediate</div></div><div class="skill-bar" style="background:#f472b6;width:72%"></div></div>
      <div class="skill-card"><span class="skill-icon">🔦</span><div><div class="skill-name">PyTorch</div><div class="skill-level">Intermediate</div></div><div class="skill-bar" style="background:#f472b6;width:65%"></div></div>
      <div class="skill-card"><span class="skill-icon">🤗</span><div><div class="skill-name">Hugging Face</div><div class="skill-level">Intermediate</div></div><div class="skill-bar" style="background:#f5a623;width:60%"></div></div>
      <div class="skill-card"><span class="skill-icon">⛓</span><div><div class="skill-name">LangChain</div><div class="skill-level">Learning</div></div><div class="skill-bar" style="background:#00f5ff;width:45%"></div></div>
      <div class="skill-card"><span class="skill-icon">🤖</span><div><div class="skill-name">OpenAI API</div><div class="skill-level">Intermediate</div></div><div class="skill-bar" style="background:#a78bfa;width:68%"></div></div>
      <div class="skill-card"><span class="skill-icon">📊</span><div><div class="skill-name">Scikit-learn</div><div class="skill-level">Advanced</div></div><div class="skill-bar" style="background:#f5a623;width:80%"></div></div>
    </div>
    <div class="skill-panel" id="panel-tools">
      <div class="skill-card"><span class="skill-icon">🐙</span><div><div class="skill-name">Git / GitHub</div><div class="skill-level">Advanced</div></div><div class="skill-bar" style="background:#f472b6;width:90%"></div></div>
      <div class="skill-card"><span class="skill-icon">🐧</span><div><div class="skill-name">Linux</div><div class="skill-level">Intermediate</div></div><div class="skill-bar" style="background:#00f5ff;width:72%"></div></div>
      <div class="skill-card"><span class="skill-icon">📬</span><div><div class="skill-name">Postman</div><div class="skill-level">Advanced</div></div><div class="skill-bar" style="background:#f5a623;width:85%"></div></div>
      <div class="skill-card"><span class="skill-icon">🐳</span><div><div class="skill-name">Docker</div><div class="skill-level">Learning</div></div><div class="skill-bar" style="background:#3b82f6;width:40%"></div></div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section reveal" id="projects">
    <div class="section-head">
      <div class="icon">🚀</div>
      <h2>Featured Projects</h2>
      <div class="line"></div>
    </div>
    <div class="projects-grid">
      <div class="proj-card">
        <div class="proj-header">
          <span class="proj-icon">🤖</span>
          <span class="proj-stars">★ 48</span>
        </div>
        <div class="proj-name">AI Chat Platform</div>
        <div class="proj-desc">Full-stack MERN app with LangChain + OpenAI. RAG pipeline, vector DB, real-time streaming responses.</div>
        <div class="proj-tags">
          <span class="proj-tag" style="color:var(--cyan);border-color:rgba(0,245,255,.3);background:rgba(0,245,255,.06)">React</span>
          <span class="proj-tag" style="color:var(--green);border-color:rgba(0,255,136,.3);background:rgba(0,255,136,.06)">Node.js</span>
          <span class="proj-tag" style="color:var(--purple);border-color:rgba(167,139,250,.3);background:rgba(167,139,250,.06)">LangChain</span>
        </div>
      </div>
      <div class="proj-card">
        <div class="proj-header">
          <span class="proj-icon">📊</span>
          <span class="proj-stars">★ 32</span>
        </div>
        <div class="proj-name">ML Analytics Dashboard</div>
        <div class="proj-desc">Real-time analytics platform with ML model monitoring, 97.4% accuracy tracking, and live metrics.</div>
        <div class="proj-tags">
          <span class="proj-tag" style="color:var(--amber);border-color:rgba(245,166,35,.3);background:rgba(245,166,35,.06)">Python</span>
          <span class="proj-tag" style="color:var(--cyan);border-color:rgba(0,245,255,.3);background:rgba(0,245,255,.06)">React</span>
          <span class="proj-tag" style="color:var(--pink);border-color:rgba(244,114,182,.3);background:rgba(244,114,182,.06)">TensorFlow</span>
        </div>
      </div>
      <div class="proj-card">
        <div class="proj-header">
          <span class="proj-icon">🛒</span>
          <span class="proj-stars">★ 21</span>
        </div>
        <div class="proj-name">E-Commerce Platform</div>
        <div class="proj-desc">Production-ready MERN stack store with JWT auth, Stripe payments, admin panel, and REST API.</div>
        <div class="proj-tags">
          <span class="proj-tag" style="color:var(--green);border-color:rgba(0,255,136,.3);background:rgba(0,255,136,.06)">MongoDB</span>
          <span class="proj-tag" style="color:var(--cyan);border-color:rgba(0,245,255,.3);background:rgba(0,245,255,.06)">Express</span>
          <span class="proj-tag" style="color:var(--blue);border-color:rgba(59,130,246,.3);background:rgba(59,130,246,.06)">Stripe</span>
        </div>
      </div>
      <div class="proj-card">
        <div class="proj-header">
          <span class="proj-icon">🔍</span>
          <span class="proj-stars">★ 17</span>
        </div>
        <div class="proj-name">DSA Visualizer</div>
        <div class="proj-desc">Interactive algorithm visualizer — sorting, pathfinding, trees. Step-by-step animations in React.</div>
        <div class="proj-tags">
          <span class="proj-tag" style="color:var(--cyan);border-color:rgba(0,245,255,.3);background:rgba(0,245,255,.06)">React</span>
          <span class="proj-tag" style="color:var(--amber);border-color:rgba(245,166,35,.3);background:rgba(245,166,35,.06)">C++</span>
          <span class="proj-tag" style="color:var(--purple);border-color:rgba(167,139,250,.3);background:rgba(167,139,250,.06)">D3.js</span>
        </div>
      </div>
    </div>
  </div>

  <!-- ACTIVITY GRAPH -->
  <div class="section reveal">
    <div class="section-head">
      <div class="icon">📈</div>
      <h2>Contribution Activity</h2>
      <div class="line"></div>
    </div>
    <div class="terminal">
      <div class="term-bar">
        <div class="term-dot" style="background:#ff5f57"></div>
        <div class="term-dot" style="background:#febc2e"></div>
        <div class="term-dot" style="background:#28c840"></div>
        <span class="term-title">GitHub Activity — past year</span>
      </div>
      <div style="padding:20px 20px 16px">
        <div class="activity-grid" id="act-grid"></div>
        <div style="display:flex;gap:8px;align-items:center;margin-top:12px;justify-content:flex-end">
          <span style="font-family:var(--mono);font-size:11px;color:var(--text3)">Less</span>
          <div style="width:12px;height:12px;border-radius:2px;background:#0a1628"></div>
          <div style="width:12px;height:12px;border-radius:2px;background:#0d3f2a"></div>
          <div style="width:12px;height:12px;border-radius:2px;background:#0a6b3e"></div>
          <div style="width:12px;height:12px;border-radius:2px;background:#00aa60"></div>
          <div style="width:12px;height:12px;border-radius:2px;background:#00ff88"></div>
          <span style="font-family:var(--mono);font-size:11px;color:var(--text3)">More</span>
        </div>
      </div>
    </div>
  </div>

  <!-- COMPETITIVE CODING -->
  <div class="section reveal" id="competitive">
    <div class="section-head">
      <div class="icon">⚔</div>
      <h2>Competitive Programming</h2>
      <div class="line"></div>
    </div>
    <div class="platforms-grid">
      <a href="https://leetcode.com/Ujjawal_Pandey" class="platform-card" target="_blank" style="border-color:rgba(255,161,22,.2)">
        <span class="platform-logo">🟨</span>
        <div class="platform-name">LeetCode</div>
        <div class="platform-stat">300+ problems solved</div>
        <span class="platform-rank" style="background:rgba(255,161,22,.12);color:#ffa116">Knight 🏅</span>
      </a>
      <a href="https://codeforces.com/" class="platform-card" target="_blank" style="border-color:rgba(59,130,246,.2)">
        <span class="platform-logo">🔵</span>
        <div class="platform-name">Codeforces</div>
        <div class="platform-stat">Active participant</div>
        <span class="platform-rank" style="background:rgba(59,130,246,.12);color:#3b82f6">Pupil</span>
      </a>
      <a href="https://www.codechef.com/" class="platform-card" target="_blank" style="border-color:rgba(92,70,56,.4)">
        <span class="platform-logo">👨‍🍳</span>
        <div class="platform-name">CodeChef</div>
        <div class="platform-stat">Long challenges</div>
        <span class="platform-rank" style="background:rgba(245,166,35,.12);color:#f5a623">3★</span>
      </a>
      <a href="https://hackerrank.com/" class="platform-card" target="_blank" style="border-color:rgba(0,200,100,.2)">
        <span class="platform-logo">🟢</span>
        <div class="platform-name">HackerRank</div>
        <div class="platform-stat">5★ Problem Solving</div>
        <span class="platform-rank" style="background:rgba(0,200,100,.12);color:#00cc64">Gold 🥇</span>
      </a>
      <a href="https://www.geeksforgeeks.org/" class="platform-card" target="_blank" style="border-color:rgba(47,141,70,.2)">
        <span class="platform-logo">🌿</span>
        <div class="platform-name">GeeksForGeeks</div>
        <div class="platform-stat">Articles + DSA</div>
        <span class="platform-rank" style="background:rgba(47,141,70,.12);color:#2f8d46">Contributor</span>
      </a>
    </div>
  </div>

  <!-- CURRENTLY BUILDING -->
  <div class="section reveal">
    <div class="section-head">
      <div class="icon">🎯</div>
      <h2>Current Missions</h2>
      <div class="line"></div>
    </div>
    <div class="mission-grid">
      <div class="mission-card" style="border-left:3px solid var(--cyan);border-radius:0 14px 14px 0">
        <span class="mission-icon">🔨</span>
        <div><div class="mission-title">Building</div><div class="mission-text">AI-powered MERN Stack apps with LangChain, RAG pipelines, and vector databases</div></div>
      </div>
      <div class="mission-card" style="border-left:3px solid var(--purple);border-radius:0 14px 14px 0">
        <span class="mission-icon">📖</span>
        <div><div class="mission-title">Learning</div><div class="mission-text">LangChain · RAG · Vector DBs · DevOps · System Design · Cloud infra</div></div>
      </div>
      <div class="mission-card" style="border-left:3px solid var(--red);border-radius:0 14px 14px 0">
        <span class="mission-icon">⚔</span>
        <div><div class="mission-title">Grinding</div><div class="mission-text">LeetCode DSA daily · Competitive programming · System design interviews</div></div>
      </div>
      <div class="mission-card" style="border-left:3px solid var(--green);border-radius:0 14px 14px 0">
        <span class="mission-icon">🤝</span>
        <div><div class="mission-title">Open For</div><div class="mission-text">Internships · Open source collabs · Hackathons · Technical discussions</div></div>
      </div>
    </div>
  </div>

  <!-- GITHUB STATS VISUAL -->
  <div class="section reveal">
    <div class="section-head">
      <div class="icon">📊</div>
      <h2>GitHub Intelligence</h2>
      <div class="line"></div>
    </div>
    <div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:12px">
      <div class="terminal" style="margin:0">
        <div class="term-bar"><span class="term-title">Streak</span></div>
        <div style="padding:20px;text-align:center">
          <div style="font-size:36px;font-weight:700;font-family:var(--mono);color:var(--amber)" id="streak-count">0</div>
          <div style="font-size:11px;color:var(--text3);font-family:var(--mono);margin-top:4px">day streak 🔥</div>
          <div style="margin-top:14px;display:flex;gap:6px;justify-content:center">
            <span style="padding:4px 10px;border-radius:100px;background:rgba(245,166,35,.1);color:var(--amber);font-size:10px;font-family:var(--mono)">Current</span>
            <span style="padding:4px 10px;border-radius:100px;background:rgba(0,245,255,.1);color:var(--cyan);font-size:10px;font-family:var(--mono)">Active</span>
          </div>
        </div>
      </div>
      <div class="terminal" style="margin:0">
        <div class="term-bar"><span class="term-title">Languages</span></div>
        <div style="padding:20px">
          <div id="lang-bars"></div>
        </div>
      </div>
      <div class="terminal" style="margin:0">
        <div class="term-bar"><span class="term-title">Activity</span></div>
        <div style="padding:20px;text-align:center">
          <div style="display:flex;justify-content:center;gap:14px;flex-wrap:wrap">
            <div><div style="font-size:22px;font-weight:700;font-family:var(--mono);color:var(--cyan)">500+</div><div style="font-size:10px;color:var(--text3);font-family:var(--mono)">Commits</div></div>
            <div><div style="font-size:22px;font-weight:700;font-family:var(--mono);color:var(--green)">12+</div><div style="font-size:10px;color:var(--text3);font-family:var(--mono)">Repos</div></div>
            <div><div style="font-size:22px;font-weight:700;font-family:var(--mono);color:var(--purple)">8+</div><div style="font-size:10px;color:var(--text3);font-family:var(--mono)">Stars</div></div>
          </div>
          <div style="margin-top:16px;height:50px;display:flex;align-items:flex-end;gap:4px;justify-content:center" id="mini-chart"></div>
        </div>
      </div>
    </div>
  </div>

  <!-- CONTACT -->
  <div class="section reveal" id="contact">
    <div class="section-head">
      <div class="icon">🌐</div>
      <h2>Connect & Collaborate</h2>
      <div class="line"></div>
    </div>
    <div class="contact-grid">
      <a href="https://github.com/ujjawal295" class="contact-card" target="_blank">
        <div class="contact-icon" style="background:rgba(255,255,255,.06);font-size:22px">🐙</div>
        <div><div class="contact-label">GitHub</div><div class="contact-val">ujjawal295</div></div>
      </a>
      <a href="https://linkedin.com/in/pandeyujjawal" class="contact-card" target="_blank">
        <div class="contact-icon" style="background:rgba(10,102,194,.12);font-size:22px">💼</div>
        <div><div class="contact-label">LinkedIn</div><div class="contact-val">pandeyujjawal</div></div>
      </a>
      <a href="mailto:ujjawalpandey073@gmail.com" class="contact-card" target="_blank">
        <div class="contact-icon" style="background:rgba(234,67,53,.12);font-size:22px">📧</div>
        <div><div class="contact-label">Email</div><div class="contact-val">ujjawalpandey073@gmail.com</div></div>
      </a>
      <a href="https://leetcode.com/Ujjawal_Pandey" class="contact-card" target="_blank">
        <div class="contact-icon" style="background:rgba(255,161,22,.1);font-size:22px">🟨</div>
        <div><div class="contact-label">LeetCode</div><div class="contact-val">Ujjawal_Pandey</div></div>
      </a>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="footer-glow">Let's Build Something Legendary 🚀</div>
    <div class="footer-text">Ujjawal Pandey · Parul University, Gujarat · Made with ☕ + 💻</div>
  </div>

</div>

<script>
// ── TYPEWRITER ──
const lines=["🚀 Crafting Full Stack Experiences","🤖 Engineering AI-Powered Solutions","⚡ MERN Stack | C++ | Python | DSA","🧠 Turning Ideas Into Reality","🔥 Building the Future, One Commit at a Time"];
let li=0,ci=0,del=false;
const tw=document.getElementById('typewriter');
function type(){
  const line=lines[li];
  if(!del){tw.innerHTML=line.slice(0,ci+1)+'<span class="cursor-blink">_</span>';ci++;if(ci===line.length){del=true;setTimeout(type,1800);return;}}
  else{tw.innerHTML=line.slice(0,ci-1)+'<span class="cursor-blink">_</span>';ci--;if(ci===0){del=false;li=(li+1)%lines.length;}}
  setTimeout(type,del?40:80);
}
type();

// ── COUNTER ANIMATION ──
function animCount(el,target,suffix=''){
  let v=0;const step=Math.ceil(target/60);
  const t=setInterval(()=>{v=Math.min(v+step,target);el.textContent=v+(suffix||'');if(v>=target)clearInterval(t);},20);
}
const obs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      animCount(document.getElementById('s1'),20,'+');
      animCount(document.getElementById('s2'),300,'+');
      animCount(document.getElementById('s3'),500,'+');
      animCount(document.getElementById('s4'),20,'+');
      obs.disconnect();
    }
  });
},{threshold:.3});
obs.observe(document.querySelector('.stats-bar'));

// ── STREAK ──
const streakObs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting){animCount(document.getElementById('streak-count'),42);streakObs.disconnect();}});
},{threshold:.3});
streakObs.observe(document.getElementById('streak-count'));

// ── ACTIVITY GRID ──
const grid=document.getElementById('act-grid');
for(let i=0;i<364;i++){
  const r=Math.random();
  const lvl=r<.35?0:r<.55?1:r<.72?2:r<.88?3:4;
  const d=document.createElement('div');
  d.className=`act-cell act-${lvl}`;
  d.title=`${lvl*3} contributions`;
  grid.appendChild(d);
}

// ── SKILL TABS ──
function switchTab(id){
  document.querySelectorAll('.skill-tab').forEach((t,i)=>{t.classList.toggle('active',['lang','frontend','backend','ai','tools'][i]===id);});
  document.querySelectorAll('.skill-panel').forEach(p=>{p.classList.remove('active');});
  document.getElementById('panel-'+id).classList.add('active');
}

// ── LANG BARS ──
const langs=[['C++',82,'#00f5ff'],['JavaScript',75,'#f5a623'],['Python',70,'#4eff91'],['Java',40,'#f472b6']];
const lb=document.getElementById('lang-bars');
langs.forEach(([n,p,c])=>{
  lb.innerHTML+=`<div style="margin-bottom:12px">
    <div style="display:flex;justify-content:space-between;font-family:var(--mono);font-size:11px;color:var(--text2);margin-bottom:5px"><span>${n}</span><span>${p}%</span></div>
    <div style="height:4px;background:var(--card2);border-radius:2px;overflow:hidden">
      <div style="height:100%;width:${p}%;background:${c};border-radius:2px;transition:width 1s .3s ease"></div>
    </div>
  </div>`;
});

// ── MINI CHART ──
const mc=document.getElementById('mini-chart');
[30,45,20,60,40,75,55,80,65,90,70,45].forEach(h=>{
  mc.innerHTML+=`<div style="width:10px;border-radius:2px 2px 0 0;height:${h}%;background:linear-gradient(to top,var(--cyan2),var(--cyan));opacity:.7;transition:opacity .2s;cursor:pointer" onmouseover="this.style.opacity=1" onmouseout="this.style.opacity=.7"></div>`;
});

// ── SCROLL REVEAL ──
const reveals=document.querySelectorAll('.reveal');
const revObs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting){e.target.classList.add('visible');}});
},{threshold:.1});
reveals.forEach(r=>revObs.observe(r));

// ── NAV SMOOTH ──
document.querySelectorAll('.nav-link').forEach(a=>{
  a.addEventListener('click',e=>{e.preventDefault();const t=document.querySelector(a.getAttribute('href'));if(t)t.scrollIntoView({behavior:'smooth',block:'start'});});
});
</script>
</body>
</html>
