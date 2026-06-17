<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@300,0&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --navy:#0d1b2a;
  --navy-2:#112336;
  --navy-3:#1a3048;
  --navy-4:#243d58;
  --gold:#c9a84c;
  --gold-2:#e6c364;
  --gold-dim:#a88830;
  --gold-muted:rgba(201,168,76,0.12);
  --gold-muted2:rgba(201,168,76,0.06);
  --cream:#e9e1d7;
  --cream-dim:#b8b0a6;
  --surface:#16130d;
  --surface-2:#1e1b15;
  --surface-3:#221f19;
  --surface-4:#2d2a23;
  --border:rgba(201,168,76,0.15);
  --border-hover:rgba(201,168,76,0.35);
  --error:#ffb4ab;
  --error-dim:rgba(255,180,171,0.15);
  --font:'Plus Jakarta Sans',sans-serif;
  --ease:cubic-bezier(0.32,0.72,0,1);
}
html{font-family:var(--font);background:var(--surface);color:var(--cream);min-height:100vh;overflow-x:hidden}
html.ar{direction:rtl}

/* Layout */
.shell{display:grid;grid-template-columns:280px 1fr;min-height:100vh}
@media(max-width:768px){.shell{grid-template-columns:1fr}}

/* Sidebar */
.sidebar{background:var(--surface-2);border-right:0.5px solid var(--border);padding:2rem 1.5rem;display:flex;flex-direction:column;gap:2rem;position:sticky;top:0;height:100vh;overflow-y:auto}
@media(max-width:768px){.sidebar{display:none}}
.ar .sidebar{border-right:none;border-left:0.5px solid var(--border)}
.brand{font-size:15px;font-weight:700;color:var(--gold-2);letter-spacing:0.02em;line-height:1.3}
.brand span{display:block;font-size:11px;font-weight:500;color:var(--cream-dim);letter-spacing:0.08em;text-transform:uppercase;margin-top:3px}

nav{display:flex;flex-direction:column;gap:2px;flex:1}
.nav-item{display:flex;align-items:center;gap:12px;padding:10px 12px;border-radius:8px;font-size:13px;font-weight:500;color:var(--cream-dim);text-decoration:none;transition:all 0.25s var(--ease);cursor:pointer;border:none;background:none;width:100%;text-align:left}
.ar .nav-item{text-align:right}
.nav-item:hover{background:var(--surface-3);color:var(--cream)}
.nav-item.active{background:var(--gold-muted);color:var(--gold-2);border-left:2px solid var(--gold)}
.ar .nav-item.active{border-left:none;border-right:2px solid var(--gold)}
.nav-item .ms{font-size:18px;font-family:'Material Symbols Outlined';color:inherit}

.sidebar-footer{border-top:0.5px solid var(--border);padding-top:1.25rem;display:flex;align-items:center;gap:10px}
.avatar{width:36px;height:36px;border-radius:50%;background:var(--gold-muted);border:1px solid var(--border-hover);display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:700;color:var(--gold-2);flex-shrink:0}
.avatar-info p{font-size:12px;font-weight:600;color:var(--cream)}
.avatar-info span{font-size:11px;color:var(--cream-dim)}

/* Main */
.main{display:flex;flex-direction:column;min-height:100vh}

/* Topbar */
.topbar{background:var(--surface);border-bottom:0.5px solid var(--border);padding:0 2rem;height:64px;display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:10}
.topbar-left{display:flex;align-items:center;gap:10px}
.topbar-left .ms{font-family:'Material Symbols Outlined';font-size:20px;color:var(--gold)}
.topbar-title{font-size:16px;font-weight:700;color:var(--gold-2)}
.topbar-right{display:flex;align-items:center;gap:16px}
.time-block{text-align:right}
.time-block .date{font-size:12px;font-weight:500;color:var(--cream);line-height:1.2}
.time-block .time{font-size:11px;color:var(--gold);font-weight:600;letter-spacing:0.04em}
.lang-btn{border:0.5px solid var(--border-hover);background:transparent;color:var(--gold);font-family:var(--font);font-size:11px;font-weight:700;letter-spacing:0.08em;padding:5px 12px;border-radius:4px;cursor:pointer;transition:all 0.2s var(--ease)}
.lang-btn:hover{background:var(--gold-muted);border-color:var(--gold)}

/* Content */
.content{padding:2rem;display:flex;flex-direction:column;gap:1.5rem;flex:1;max-width:1100px;width:100%}
@media(max-width:768px){.content{padding:1rem}}

/* Section label */
.eyebrow{font-size:10px;font-weight:700;letter-spacing:0.12em;text-transform:uppercase;color:var(--gold);margin-bottom:10px;display:flex;align-items:center;gap:6px}
.eyebrow::before{content:'';display:block;width:16px;height:1.5px;background:var(--gold)}
.ar .eyebrow::before{display:none}
.ar .eyebrow::after{content:'';display:block;width:16px;height:1.5px;background:var(--gold)}

/* Quick Capture */
.capture-card{background:var(--surface-2);border:0.5px solid var(--border);border-radius:10px;padding:1.5rem;transition:border-color 0.25s var(--ease)}
.capture-card:focus-within{border-color:var(--border-hover)}
.capture-inner{display:flex;gap:1.25rem;align-items:flex-start}
@media(max-width:600px){.capture-inner{flex-direction:column}}
.capture-textarea{flex:1;background:var(--surface-3);border:0.5px solid var(--border);border-radius:6px;padding:12px 14px;color:var(--cream);font-family:var(--font);font-size:14px;resize:none;height:100px;transition:border-color 0.2s var(--ease);outline:none;line-height:1.6}
.capture-textarea::placeholder{color:var(--cream-dim)}
.capture-textarea:focus{border-color:var(--gold)}
.capture-tools{display:flex;gap:6px;margin-top:8px}
.icon-btn{background:transparent;border:none;color:var(--cream-dim);cursor:pointer;padding:5px 8px;border-radius:4px;font-size:12px;display:flex;align-items:center;gap:5px;transition:all 0.2s var(--ease);font-family:var(--font)}
.icon-btn:hover{color:var(--gold);background:var(--gold-muted2)}
.icon-btn .ms{font-family:'Material Symbols Outlined';font-size:16px}
.capture-actions{display:flex;flex-direction:column;gap:8px;flex-shrink:0;min-width:140px}
@media(max-width:600px){.capture-actions{flex-direction:row;min-width:auto;width:100%}}

/* Buttons */
.btn-primary{background:var(--gold);color:#1a1000;font-family:var(--font);font-size:13px;font-weight:700;border:none;padding:10px 20px;border-radius:5px;cursor:pointer;transition:all 0.2s var(--ease);width:100%;letter-spacing:0.02em}
.btn-primary:hover{background:var(--gold-2);transform:translateY(-1px)}
.btn-primary:active{transform:scale(0.98)}
.btn-outline{background:transparent;color:var(--gold);border:0.5px solid var(--border-hover);font-family:var(--font);font-size:12px;font-weight:600;padding:9px 16px;border-radius:5px;cursor:pointer;transition:all 0.2s var(--ease);width:100%;display:flex;align-items:center;justify-content:center;gap:6px;letter-spacing:0.02em}
.btn-outline:hover{background:var(--gold-muted);transform:translateY(-1px)}
.btn-outline .ms{font-family:'Material Symbols Outlined';font-size:15px}

/* 3-col grid */
.grid3{display:grid;grid-template-columns:1fr 1.4fr 1fr;gap:1.25rem;align-items:start}
@media(max-width:900px){.grid3{grid-template-columns:1fr}}

/* Triage */
.triage-list{display:flex;flex-direction:column;border:0.5px solid var(--border);border-radius:8px;overflow:hidden}
.triage-item{padding:14px 16px;background:var(--surface-2);display:flex;align-items:center;justify-content:space-between;gap:12px;border-bottom:0.5px solid var(--border);transition:background 0.18s var(--ease);cursor:pointer;position:relative}
.triage-item:last-child{border-bottom:none}
.triage-item:hover{background:var(--surface-3)}
.triage-item.priority::before{content:'';position:absolute;left:0;top:0;bottom:0;width:2.5px;background:var(--error)}
.ar .triage-item.priority::before{left:auto;right:0}
.triage-item.medium::before{background:var(--gold)}
.triage-title{font-size:13px;font-weight:500;color:var(--cream);line-height:1.4}
.triage-tag{font-size:10px;font-weight:700;letter-spacing:0.07em;text-transform:uppercase;margin-top:4px}
.triage-tag.high{color:var(--error)}
.triage-tag.medium{color:var(--gold)}
.triage-tag.low{color:var(--cream-dim)}
.triage-menu{font-family:'Material Symbols Outlined';font-size:18px;color:var(--cream-dim);cursor:pointer;transition:color 0.15s}
.triage-item:hover .triage-menu{color:var(--gold)}
.section-header{display:flex;align-items:center;justify-content:space-between;margin-bottom:10px}
.section-title{font-size:13px;font-weight:700;color:var(--cream)}
.section-action{font-size:11px;color:var(--gold);cursor:pointer;font-weight:600;letter-spacing:0.04em}

/* Portfolios */
.portfolio-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:10px}
@media(max-width:500px){.portfolio-grid{grid-template-columns:1fr}}
.port-card{background:var(--surface-2);border:0.5px solid var(--border);border-radius:8px;padding:14px;cursor:pointer;transition:all 0.22s var(--ease)}
.port-card:hover{border-color:var(--border-hover);background:var(--surface-3)}
.port-header{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:14px}
.port-title{font-size:12px;font-weight:700;color:var(--cream);line-height:1.4;max-width:100px}
.port-badge{font-size:9px;font-weight:700;text-transform:uppercase;letter-spacing:0.06em;padding:3px 8px;border-radius:3px;white-space:nowrap}
.port-badge.on-track{background:rgba(29,158,117,0.12);color:#5dcaa5}
.port-badge.planning{background:var(--surface-4);color:var(--cream-dim)}
.port-bar-bg{height:2px;background:var(--surface-4);border-radius:1px;position:relative;overflow:hidden}
.port-bar-fill{height:100%;background:var(--gold);border-radius:1px;transition:width 1s var(--ease)}
.port-meta{display:flex;justify-content:space-between;align-items:center;margin-top:6px}
.port-label{font-size:10px;color:var(--cream-dim)}
.port-pct{font-size:11px;font-weight:700;color:var(--gold)}

/* Network viz */
.net-viz{background:var(--surface-2);border:0.5px solid var(--border);border-radius:8px;height:90px;display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden}
.net-viz-label{text-align:center;position:relative;z-index:1}
.net-viz-label p{font-size:10px;font-weight:700;letter-spacing:0.1em;text-transform:uppercase;color:var(--gold);margin-bottom:3px}
.net-viz-label span{font-size:11px;color:var(--cream-dim)}
.net-pulse{position:absolute;width:60px;height:60px;border:1px solid var(--border-hover);border-radius:50%;animation:pulse 3s ease-in-out infinite}
.net-pulse:nth-child(2){width:100px;height:100px;animation-delay:1s;opacity:0.5}
@keyframes pulse{0%,100%{transform:scale(0.9);opacity:0.3}50%{transform:scale(1.1);opacity:0.7}}

/* 2-min wins */
.wins-box{background:var(--surface-3);border:0.5px solid var(--border);border-radius:8px;padding:1.25rem;display:flex;flex-direction:column;gap:12px}
.win-item{display:flex;align-items:center;gap:10px;cursor:pointer}
.win-check{width:16px;height:16px;border:1.5px solid var(--gold);border-radius:2px;flex-shrink:0;display:flex;align-items:center;justify-content:center;transition:all 0.18s var(--ease)}
.win-check.checked{background:var(--gold);border-color:var(--gold)}
.win-check .ms{font-family:'Material Symbols Outlined';font-size:11px;color:#1a1000;display:none}
.win-check.checked .ms{display:block}
.win-label{font-size:13px;color:var(--cream);transition:all 0.18s;line-height:1.4}
.win-label.done{text-decoration:line-through;opacity:0.45}
.momentum{border-top:0.5px solid var(--border);padding-top:14px;margin-top:4px}
.momentum-head{display:flex;justify-content:space-between;align-items:center;margin-bottom:6px}
.momentum-label{font-size:10px;font-weight:700;letter-spacing:0.1em;text-transform:uppercase;color:var(--gold)}
.momentum-pct{font-size:11px;color:var(--cream-dim);font-weight:500}
.momentum-bar{height:2px;background:var(--surface-4);border-radius:1px}
.momentum-fill{height:100%;background:var(--gold);border-radius:1px;transition:width 1s 0.5s var(--ease)}

/* Footer */
.footer{padding:3rem 2rem;text-align:center;opacity:0.55;border-top:0.5px solid var(--border);margin-top:auto}
.footer-quote{font-size:16px;font-weight:400;color:var(--cream-dim);font-style:italic;max-width:520px;margin:0 auto 10px;line-height:1.7}
.footer-ref{font-size:11px;font-weight:700;letter-spacing:0.1em;text-transform:uppercase;color:var(--gold)}

/* Mobile nav */
.mobile-nav{display:none;position:fixed;bottom:0;left:0;right:0;background:var(--surface-2);border-top:0.5px solid var(--border);padding:10px 0 14px;z-index:20}
@media(max-width:768px){.mobile-nav{display:flex;justify-content:space-around}}
.mob-item{display:flex;flex-direction:column;align-items:center;gap:3px;text-decoration:none;color:var(--cream-dim);font-size:10px;font-weight:500;transition:color 0.18s}
.mob-item.active,.mob-item:hover{color:var(--gold)}
.mob-item .ms{font-family:'Material Symbols Outlined';font-size:22px}

/* Animate-in */
.fade-up{opacity:0;transform:translateY(16px);transition:opacity 0.6s var(--ease),transform 0.6s var(--ease)}
.fade-up.visible{opacity:1;transform:translateY(0)}
@media(prefers-reduced-motion:reduce){.fade-up{transition:opacity 0.3s}}

/* Utils */
.ms{font-family:'Material Symbols Outlined';font-variation-settings:'FILL' 0,'wght' 300,'GRAD' 0,'opsz' 24}
</style>
</head>
<body>
<h2 class="sr-only" style="position:absolute;width:1px;height:1px;overflow:hidden">Capture and Execute Dashboard — Infrastructure Command</h2>

<div class="shell">
  <!-- Sidebar -->
  <aside class="sidebar">
    <div class="brand">Infrastructure Command<span>Capture &amp; Execute</span></div>
    <nav>
      <a class="nav-item active" href="#"><span class="ms">dashboard</span> <span id="nav-dashboard">Dashboard</span></a>
      <a class="nav-item" href="#"><span class="ms">account_tree</span> <span id="nav-portfolio">Portfolio</span></a>
      <a class="nav-item" href="#"><span class="ms">biotech</span> <span id="nav-triage">Triage</span></a>
      <a class="nav-item" href="#"><span class="ms">query_stats</span> <span id="nav-analytics">Analytics</span></a>
    </nav>
    <div class="sidebar-footer">
      <div class="avatar">PM</div>
      <div class="avatar-info">
        <p id="sidebar-role">Infrastructure PM</p>
        <span id="sidebar-time">Mogadishu · 14:30 EAT</span>
      </div>
    </div>
  </aside>

  <!-- Main -->
  <div class="main">
    <!-- Topbar -->
    <header class="topbar">
      <div class="topbar-left">
        <span class="ms">grid_view</span>
        <span class="topbar-title" id="page-title">Capture &amp; Execute</span>
      </div>
      <div class="topbar-right">
        <div class="time-block">
          <div class="date" id="top-date">Monday, 24 May</div>
          <div class="time" id="top-time">14:30 EAT</div>
        </div>
        <button class="lang-btn" onclick="toggleLang()" aria-label="Toggle language">EN/AR</button>
      </div>
    </header>

    <div class="content">

      <!-- Quick Capture -->
      <section class="fade-up">
        <div class="eyebrow" id="lbl-capture">Quick Capture</div>
        <div class="capture-card">
          <div class="capture-inner">
            <div style="flex:1">
              <textarea class="capture-textarea" id="capture-input" placeholder="What's on your mind? Capture the next infrastructure milestone..."></textarea>
              <div class="capture-tools">
                <button class="icon-btn"><span class="ms">text_fields</span> <span id="tool-text">Text</span></button>
                <button class="icon-btn"><span class="ms">mic</span> <span id="tool-voice">Voice</span></button>
                <button class="icon-btn"><span class="ms">camera_alt</span> <span id="tool-scan">Scan</span></button>
              </div>
            </div>
            <div class="capture-actions">
              <button class="btn-primary" id="btn-triage">Triage</button>
              <button class="btn-outline"><span class="ms">terminal</span> <span id="btn-github">GitHub</span></button>
            </div>
          </div>
        </div>
      </section>

      <!-- 3-col -->
      <div class="grid3">

        <!-- Triage -->
        <section class="fade-up" style="transition-delay:0.1s">
          <div class="section-header">
            <div class="section-title" id="lbl-triage">System Triage</div>
            <div class="section-action" id="lbl-filter">Priority Filter</div>
          </div>
          <div class="triage-list">
            <div class="triage-item priority">
              <div>
                <div class="triage-title" id="task-1">Draft WASH donor report</div>
                <div class="triage-tag high" id="tag-1">High Impact</div>
              </div>
              <span class="ms triage-menu">more_vert</span>
            </div>
            <div class="triage-item medium">
              <div>
                <div class="triage-title" id="task-2">Review borehole technical specs</div>
                <div class="triage-tag medium" id="tag-2">Medium Focus</div>
              </div>
              <span class="ms triage-menu">more_vert</span>
            </div>
            <div class="triage-item">
              <div>
                <div class="triage-title" id="task-3">Logistics audit for Jubaland</div>
                <div class="triage-tag low" id="tag-3">Maintenance</div>
              </div>
              <span class="ms triage-menu">more_vert</span>
            </div>
          </div>
        </section>

        <!-- Portfolios -->
        <section class="fade-up" style="transition-delay:0.2s">
          <div class="section-header">
            <div class="section-title" id="lbl-portfolios">Active Portfolios</div>
            <span class="ms" style="color:var(--cream-dim);font-size:18px;cursor:pointer">filter_list</span>
          </div>
          <div class="portfolio-grid">
            <div class="port-card">
              <div class="port-header">
                <div class="port-title" id="proj-1">Garowe Water Expansion</div>
                <div class="port-badge on-track" id="badge-1">On Track</div>
              </div>
              <div class="port-bar-bg"><div class="port-bar-fill" style="width:65%"></div></div>
              <div class="port-meta">
                <span class="port-label" id="lbl-completion">Completion</span>
                <span class="port-pct">65%</span>
              </div>
            </div>
            <div class="port-card">
              <div class="port-header">
                <div class="port-title" id="proj-2">Lower Juba Sanitation</div>
                <div class="port-badge planning" id="badge-2">Planning</div>
              </div>
              <div class="port-bar-bg"><div class="port-bar-fill" style="width:20%;background:var(--gold-dim)"></div></div>
              <div class="port-meta">
                <span class="port-label" id="lbl-completion2">Completion</span>
                <span class="port-pct" style="color:var(--cream-dim)">20%</span>
              </div>
            </div>
          </div>
          <div class="net-viz">
            <div class="net-pulse"></div>
            <div class="net-pulse"></div>
            <div class="net-viz-label">
              <p id="lbl-network">Regional Network Load</p>
              <span id="lbl-hub">Optimized · Mogadishu Hub</span>
            </div>
          </div>
        </section>

        <!-- 2-min wins -->
        <section class="fade-up" style="transition-delay:0.3s">
          <div class="section-header">
            <div class="section-title" id="lbl-wins">2-Minute Wins</div>
            <div class="section-action" id="lbl-remaining">4 remaining</div>
          </div>
          <div class="wins-box">
            <div class="win-item" onclick="toggleWin(this)">
              <div class="win-check"><span class="ms">check</span></div>
              <span class="win-label" id="win-1">Sign contractor evaluation</span>
            </div>
            <div class="win-item" onclick="toggleWin(this)">
              <div class="win-check"><span class="ms">check</span></div>
              <span class="win-label" id="win-2">Call project site lead</span>
            </div>
            <div class="win-item" onclick="toggleWin(this)">
              <div class="win-check"><span class="ms">check</span></div>
              <span class="win-label" id="win-3">Approve travel requisition</span>
            </div>
            <div class="win-item" onclick="toggleWin(this)">
              <div class="win-check"><span class="ms">check</span></div>
              <span class="win-label" id="win-4">Forward specs to HQ</span>
            </div>
            <div class="momentum">
              <div class="momentum-head">
                <span class="momentum-label" id="lbl-momentum">Daily Momentum</span>
                <span class="momentum-pct" id="momentum-val">75%</span>
              </div>
              <div class="momentum-bar"><div class="momentum-fill" id="momentum-fill" style="width:75%"></div></div>
            </div>
          </div>
        </section>

      </div>

      <!-- Footer -->
      <footer class="footer fade-up" style="transition-delay:0.4s">
        <p class="footer-quote" id="footer-quote">"And Allah does not burden a soul more than it can bear..."</p>
        <p class="footer-ref">[Quran 2:286]</p>
      </footer>
    </div>

    <!-- Mobile nav -->
    <nav class="mobile-nav" aria-label="Mobile navigation">
      <a class="mob-item active" href="#"><span class="ms">home</span> <span>Home</span></a>
      <a class="mob-item" href="#"><span class="ms">pending_actions</span> <span>Active</span></a>
      <a class="mob-item" href="#"><span class="ms">list_alt</span> <span>Tasks</span></a>
      <a class="mob-item" href="#"><span class="ms">settings</span> <span>Settings</span></a>
    </nav>
  </div>
</div>

<script>
const strings={
  en:{
    pageTitle:'Capture &amp; Execute',
    navDashboard:'Dashboard',navPortfolio:'Portfolio',navTriage:'Triage',navAnalytics:'Analytics',
    sidebarRole:'Infrastructure PM',sidebarTime:'Mogadishu · EAT',
    lblCapture:'Quick Capture',
    placeholder:"What's on your mind? Capture the next infrastructure milestone...",
    toolText:'Text',toolVoice:'Voice',toolScan:'Scan',
    btnTriage:'Triage',btnGithub:'GitHub',
    lblTriage:'System Triage',lblFilter:'Priority Filter',
    task1:'Draft WASH donor report',tag1:'High Impact',
    task2:'Review borehole technical specs',tag2:'Medium Focus',
    task3:'Logistics audit for Jubaland',tag3:'Maintenance',
    lblPortfolios:'Active Portfolios',
    proj1:'Garowe Water Expansion',badge1:'On Track',
    proj2:'Lower Juba Sanitation',badge2:'Planning',
    lblCompletion:'Completion',
    lblNetwork:'Regional Network Load',lblHub:'Optimized · Mogadishu Hub',
    lblWins:'2-Minute Wins',lblRemaining:'4 remaining',
    win1:'Sign contractor evaluation',win2:'Call project site lead',
    win3:'Approve travel requisition',win4:'Forward specs to HQ',
    lblMomentum:'Daily Momentum',
    footerQuote:'"And Allah does not burden a soul more than it can bear..."'
  },
  ar:{
    pageTitle:'التقاط وتنفيذ',
    navDashboard:'لوحة التحكم',navPortfolio:'المحفظة',navTriage:'الفرز',navAnalytics:'التحليلات',
    sidebarRole:'مدير مشروع البنية التحتية',sidebarTime:'مقديشو · EAT',
    lblCapture:'التقاط سريع',
    placeholder:'ماذا يدور في ذهنك؟ سجّل المرحلة القادمة من البنية التحتية...',
    toolText:'نص',toolVoice:'صوت',toolScan:'مسح',
    btnTriage:'فرز',btnGithub:'GitHub',
    lblTriage:'فرز النظام',lblFilter:'تصفية الأولوية',
    task1:'صياغة تقرير المانحين لبرنامج المياه',tag1:'تأثير عالٍ',
    task2:'مراجعة المواصفات التقنية للحفر',tag2:'تركيز متوسط',
    task3:'تدقيق لوجستي لجوبالاند',tag3:'صيانة',
    lblPortfolios:'المحافظ النشطة',
    proj1:'توسعة مياه غاروي',badge1:'في المسار',
    proj2:'الصرف الصحي في جوبا السفلى',badge2:'تخطيط',
    lblCompletion:'الإنجاز',
    lblNetwork:'حمل الشبكة الإقليمية',lblHub:'محسّن · مركز مقديشو',
    lblWins:'إنجازات دقيقتين',lblRemaining:'٤ متبقية',
    win1:'توقيع تقييم المقاول',win2:'الاتصال بمسؤول الموقع',
    win3:'الموافقة على طلب السفر',win4:'إرسال المواصفات إلى المقر',
    lblMomentum:'الزخم اليومي',
    footerQuote:'"لَا يُكَلِّفُ اللَّهُ نَفْسًا إِلَّا وُسْعَهَا..."'
  }
};

let lang='en';
function toggleLang(){
  lang=lang==='en'?'ar':'en';
  const s=strings[lang];
  document.getElementById('page-title').innerHTML=s.pageTitle;
  document.getElementById('nav-dashboard').textContent=s.navDashboard;
  document.getElementById('nav-portfolio').textContent=s.navPortfolio;
  document.getElementById('nav-triage').textContent=s.navTriage;
  document.getElementById('nav-analytics').textContent=s.navAnalytics;
  document.getElementById('sidebar-role').textContent=s.sidebarRole;
  document.getElementById('lbl-capture').textContent=s.lblCapture;
  document.getElementById('capture-input').placeholder=s.placeholder;
  document.getElementById('tool-text').textContent=s.toolText;
  document.getElementById('tool-voice').textContent=s.toolVoice;
  document.getElementById('tool-scan').textContent=s.toolScan;
  document.getElementById('btn-triage').textContent=s.btnTriage;
  document.getElementById('btn-github').textContent=s.btnGithub;
  document.getElementById('lbl-triage').textContent=s.lblTriage;
  document.getElementById('lbl-filter').textContent=s.lblFilter;
  document.getElementById('task-1').textContent=s.task1;
  document.getElementById('tag-1').textContent=s.tag1;
  document.getElementById('task-2').textContent=s.task2;
  document.getElementById('tag-2').textContent=s.tag2;
  document.getElementById('task-3').textContent=s.task3;
  document.getElementById('tag-3').textContent=s.tag3;
  document.getElementById('lbl-portfolios').textContent=s.lblPortfolios;
  document.getElementById('proj-1').textContent=s.proj1;
  document.getElementById('badge-1').textContent=s.badge1;
  document.getElementById('proj-2').textContent=s.proj2;
  document.getElementById('badge-2').textContent=s.badge2;
  document.getElementById('lbl-completion').textContent=s.lblCompletion;
  document.getElementById('lbl-completion2').textContent=s.lblCompletion;
  document.getElementById('lbl-network').textContent=s.lblNetwork;
  document.getElementById('lbl-hub').textContent=s.lblHub;
  document.getElementById('lbl-wins').textContent=s.lblWins;
  document.getElementById('win-1').textContent=s.win1;
  document.getElementById('win-2').textContent=s.win2;
  document.getElementById('win-3').textContent=s.win3;
  document.getElementById('win-4').textContent=s.win4;
  document.getElementById('lbl-momentum').textContent=s.lblMomentum;
  document.getElementById('footer-quote').textContent=s.footerQuote;
  document.documentElement.classList.toggle('ar',lang==='ar');
}

function toggleWin(el){
  const check=el.querySelector('.win-check');
  const label=el.querySelector('.win-label');
  check.classList.toggle('checked');
  label.classList.toggle('done');
  updateMomentum();
  updateRemaining();
}

function updateMomentum(){
  const total=document.querySelectorAll('.win-item').length;
  const done=document.querySelectorAll('.win-check.checked').length;
  const pct=Math.round((done/total)*100);
  document.getElementById('momentum-val').textContent=pct+'%';
  document.getElementById('momentum-fill').style.width=pct+'%';
}

function updateRemaining(){
  const total=document.querySelectorAll('.win-item').length;
  const done=document.querySelectorAll('.win-check.checked').length;
  const rem=total-done;
  const s=strings[lang];
  document.getElementById('lbl-remaining').textContent=lang==='en'?rem+' remaining':'٠١٢٣٤'[rem]+' متبقية';
}

function updateClock(){
  const now=new Date();
  const eat=new Date(now.toLocaleString('en-US',{timeZone:'Africa/Nairobi'}));
  const hh=String(eat.getHours()).padStart(2,'0');
  const mm=String(eat.getMinutes()).padStart(2,'0');
  document.getElementById('top-time').textContent=hh+':'+mm+' EAT';
  document.getElementById('sidebar-time').textContent='Mogadishu · '+hh+':'+mm+' EAT';
  const days=['Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturday'];
  const months=['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
  document.getElementById('top-date').textContent=days[eat.getDay()]+', '+eat.getDate()+' '+months[eat.getMonth()];
}

const io=new IntersectionObserver((entries)=>{
  entries.forEach(e=>{if(e.isIntersecting){e.target.classList.add('visible');io.unobserve(e.target)}});
},{threshold:0.15});
document.querySelectorAll('.fade-up').forEach(el=>io.observe(el));

updateClock();
setInterval(updateClock,30000);
</script>
</body>
</html>
