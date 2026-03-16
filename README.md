<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Angel Urdaneta — Full-Stack Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@700;800&family=DM+Sans:wght@300;400;500;600&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --orange: #ff6a00;
  --blue: #00aaff;
  --bg: #040d1a;
  --card: #060f22;
  --card2: #0a1830;
  --border: rgba(0,180,255,0.14);
  --text: rgba(255,255,255,0.75);
  --muted: rgba(255,255,255,0.35);
}

html { scroll-behavior: smooth; }

body {
  font-family: 'DM Sans', sans-serif;
  background: var(--bg);
  color: var(--text);
  min-height: 100vh;
  padding: 20px 16px 60px;
}

/* ── WRAPPER ── */
.wrap {
  max-width: 860px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 0;
}

/* ── CARD BASE ── */
.card {
  background: linear-gradient(135deg, var(--card) 0%, var(--card2) 50%, var(--card) 100%);
  border: 1px solid var(--border);
  position: relative;
  overflow: hidden;
}
.card::before {
  content: '';
  position: absolute; inset: 0;
  background-image:
    linear-gradient(rgba(0,180,255,0.035) 1px, transparent 1px),
    linear-gradient(90deg, rgba(0,180,255,0.035) 1px, transparent 1px);
  background-size: 40px 40px;
  pointer-events: none;
}

/* corner brackets */
.card .c { position: absolute; width: 16px; height: 16px; border-color: rgba(0,180,255,0.35); border-style: solid; }
.c.tl { top:12px; left:12px; border-width:2px 0 0 2px; }
.c.tr { top:12px; right:12px; border-width:2px 2px 0 0; }
.c.bl { bottom:12px; left:12px; border-width:0 0 2px 2px; }
.c.br { bottom:12px; right:12px; border-width:0 2px 2px 0; }

/* ── HERO SECTION ── */
#hero {
  border-radius: 20px 20px 0 0;
  padding: 48px 36px 40px;
  text-align: center;
  box-shadow: 0 0 100px rgba(0,100,255,0.1);
}

.glow { position:absolute; top:-80px; left:50%; transform:translateX(-50%); width:600px; height:260px; background:radial-gradient(ellipse,rgba(0,130,255,0.12) 0%,transparent 70%); pointer-events:none; }

.laptop-wrap {
  display: flex; justify-content: center;
  margin-bottom: 28px;
  animation: float 3.5s ease-in-out infinite alternate;
}
@keyframes float { from{transform:translateY(0)} to{transform:translateY(-10px)} }
.laptop-wrap svg { width: 170px; filter: drop-shadow(0 12px 32px rgba(0,140,255,0.38)); }

.greeting { font-size:11px; letter-spacing:4px; text-transform:uppercase; color:var(--muted); margin-bottom:10px; }

.hero-name {
  font-family: 'Syne', sans-serif;
  font-size: clamp(40px, 9vw, 74px);
  font-weight: 800;
  letter-spacing: -1px;
  line-height: 1;
  margin-bottom: 6px;
}
.hero-name .w { color: #fff; }
.hero-name .o { color: var(--orange); }

.hero-sub { font-size:13px; letter-spacing:2.5px; color:var(--muted); margin-bottom:18px; text-transform:uppercase; }

.badge {
  display: inline-flex; align-items: center; gap: 10px;
  background: rgba(255,106,0,0.09);
  border: 1px solid rgba(255,106,0,0.32);
  border-radius: 8px; padding: 8px 24px; margin-bottom: 14px;
}
.badge span { color: var(--orange); font-family:'Syne',sans-serif; font-weight:700; font-size:16px; letter-spacing:1px; }
.badge .bar { color:rgba(255,106,0,0.4); font-size:18px; }

.spec { font-size:13px; color:var(--muted); letter-spacing:1px; margin-bottom:32px; }
.spec .dot { color:var(--orange); margin:0 8px; }

/* ── DIVIDER ── */
.sec-div {
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(0,180,255,0.2), transparent);
  margin: 0;
}

/* ── ABOUT ── */
#about { padding: 36px 36px; }
.sec-title {
  font-family: 'Syne', sans-serif;
  font-size: 13px; letter-spacing: 3px;
  text-transform: uppercase;
  color: var(--orange);
  margin-bottom: 18px;
  display: flex; align-items: center; gap: 10px;
}
.sec-title::after { content:''; flex:1; height:1px; background:linear-gradient(90deg,rgba(255,106,0,0.3),transparent); }

.code-block {
  background: rgba(0,0,0,0.35);
  border: 1px solid rgba(0,180,255,0.1);
  border-radius: 12px;
  padding: 22px 24px;
  font-family: 'Fira Code', monospace;
  font-size: 13px;
  line-height: 1.9;
  text-align: left;
  overflow-x: auto;
}
.kw { color: #ff6a00; }
.va { color: #61dafb; }
.st { color: #4ade80; }
.cm { color: rgba(255,255,255,0.28); }
.pu { color: rgba(255,255,255,0.5); }

/* ── CONTACTS ── */
#contacts { padding: 28px 36px 32px; }
.contact-row {
  display: flex; flex-wrap: wrap;
  justify-content: center; gap: 10px;
}
.ct {
  display: flex; align-items: center; gap: 8px;
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 8px; padding: 9px 16px;
  text-decoration: none;
  transition: border-color 0.2s, background 0.2s, transform 0.2s;
  font-size: 13px; color: var(--text);
}
.ct:hover { border-color:rgba(0,180,255,0.45); background:rgba(0,180,255,0.07); transform:translateY(-2px); }
.ct svg { flex-shrink:0; }

/* ── TECH STACK ── */
#stack { padding: 28px 36px 36px; }
.stack-cat { margin-bottom: 24px; }
.cat-label {
  font-size: 11px; letter-spacing: 2.5px; text-transform: uppercase;
  color: var(--muted); margin-bottom: 12px;
  display: flex; align-items: center; gap: 8px;
}
.cat-label span { color: var(--orange); font-size: 14px; }
.cat-label::after { content:''; flex:1; height:1px; background:rgba(255,255,255,0.07); }

.sk-row { display:flex; flex-wrap:wrap; gap:8px; }

.sk {
  display: flex; align-items: center; gap: 7px;
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 8px; padding: 7px 13px;
  font-size: 12px; color: var(--text);
  transition: transform 0.2s, border-color 0.2s, box-shadow 0.2s;
  cursor: default;
}
.sk:hover {
  transform: translateY(-3px);
  border-color: rgba(255,106,0,0.4);
  box-shadow: 0 6px 20px rgba(255,106,0,0.15);
}
.sk svg { width:18px; height:18px; flex-shrink:0; }

/* ── STATS ── */
#stats { padding: 28px 36px 36px; }
.stats-grid { display:flex; flex-wrap:wrap; gap:12px; justify-content:center; }
.stat-card {
  flex: 1 1 180px;
  background: rgba(0,0,0,0.25);
  border: 1px solid rgba(0,180,255,0.1);
  border-radius: 12px;
  padding: 20px 18px;
  text-align: center;
}
.stat-num {
  font-family: 'Syne', sans-serif;
  font-size: 32px; font-weight: 800;
  color: var(--orange); line-height: 1;
  margin-bottom: 4px;
}
.stat-label { font-size: 11px; letter-spacing: 2px; text-transform: uppercase; color: var(--muted); }

/* ── FOOTER ── */
#footer {
  border-radius: 0 0 20px 20px;
  padding: 28px 36px;
  text-align: center;
}
.footer-line { width:80px; height:2px; background:linear-gradient(90deg,transparent,var(--orange),transparent); margin:0 auto 18px; }
.footer-text { font-size:13px; color:var(--muted); letter-spacing:1px; }
.footer-text strong { color:var(--orange); }

.sparkle { position:absolute; color:rgba(0,180,255,0.35); font-size:16px; animation:twinkle 2.2s ease-in-out infinite alternate; pointer-events:none; }
@keyframes twinkle { from{opacity:.15;transform:scale(.8) rotate(0deg)} to{opacity:.9;transform:scale(1.2) rotate(22deg)} }

/* ── ANIMATIONS ── */
.fade-in { opacity:0; transform:translateY(20px); animation:fadeIn 0.6s ease forwards; }
@keyframes fadeIn { to{opacity:1;transform:translateY(0)} }
.fade-in:nth-child(1){animation-delay:0.1s}
.fade-in:nth-child(2){animation-delay:0.2s}
.fade-in:nth-child(3){animation-delay:0.3s}

/* ── RESPONSIVE ── */
@media(max-width:600px){
  body { padding:12px 10px 50px; }
  #hero,#about,#contacts,#stack,#stats,#footer { padding-left:20px; padding-right:20px; }
  .code-block { font-size:11.5px; padding:16px; }
  .stat-card { flex:1 1 130px; }
}
</style>
</head>
<body>
<div class="wrap">

  <!-- ══════════ HERO ══════════ -->
  <section class="card" id="hero">
    <div class="glow"></div>
    <div class="c tl"></div><div class="c tr"></div>
    <div class="c bl"></div><div class="c br"></div>
    <div class="sparkle" style="bottom:26px;right:26px;animation-delay:0s">✦</div>
    <div class="sparkle" style="top:50px;left:24px;font-size:10px;animation-delay:.8s">✦</div>

    <!-- Laptop -->
    <div class="laptop-wrap">
      <svg viewBox="0 0 300 200" xmlns="http://www.w3.org/2000/svg">
        <rect x="20" y="155" width="260" height="18" rx="5" fill="#1a2a4a" stroke="#2a4a7a" stroke-width="1"/>
        <rect x="108" y="155" width="84" height="5" rx="2" fill="#0d1e38"/>
        <rect x="35" y="18" width="230" height="142" rx="9" fill="#0d1e38" stroke="#1e3a6a" stroke-width="1.5"/>
        <rect x="43" y="27" width="214" height="124" rx="5" fill="#020810"/>
        <rect x="58" y="42" width="75" height="5" rx="2.5" fill="#ff6a00" opacity="0.85"/>
        <rect x="58" y="54" width="115" height="4" rx="2" fill="#00aaff" opacity="0.65"/>
        <rect x="70" y="64" width="85" height="4" rx="2" fill="#00aaff" opacity="0.45"/>
        <rect x="70" y="74" width="58" height="4" rx="2" fill="#4ade80" opacity="0.55"/>
        <rect x="58" y="84" width="98" height="4" rx="2" fill="#00aaff" opacity="0.6"/>
        <rect x="70" y="94" width="72" height="4" rx="2" fill="#ff6a00" opacity="0.5"/>
        <rect x="58" y="104" width="48" height="4" rx="2" fill="#4ade80" opacity="0.45"/>
        <rect x="70" y="114" width="108" height="4" rx="2" fill="#00aaff" opacity="0.3"/>
        <circle cx="218" cy="84" r="20" fill="rgba(0,140,255,0.08)" stroke="rgba(0,180,255,0.25)" stroke-width="1.5"/>
        <circle cx="218" cy="84" r="9" fill="none" stroke="rgba(0,180,255,0.5)" stroke-width="2"/>
        <circle cx="218" cy="84" r="3" fill="rgba(0,180,255,0.4)"/>
        <circle cx="148" cy="31" r="2.5" fill="#1e3a6a"/>
        <line x1="35" y1="160" x2="265" y2="160" stroke="#1e3a6a" stroke-width="1"/>
      </svg>
    </div>

    <p class="greeting">Hello, I'm —</p>
    <h1 class="hero-name"><span class="w">ANGEL </span><span class="o">URDANETA</span></h1>
    <p class="hero-sub">Colombia 🇨🇴</p>

    <div class="badge">
      <span class="bar">|</span>
      <span>Full-Stack Developer</span>
      <span class="bar">|</span>
    </div>
    <br/>
    <p class="spec">AI &amp; Automation <span class="dot">•</span> Backend &amp; Database Infrastructure</p>
  </section>

  <div class="sec-div"></div>

  <!-- ══════════ ABOUT ══════════ -->
  <section class="card" id="about">
    <div class="c tl"></div><div class="c tr"></div>

    <p class="sec-title">✨ About Me</p>
    <div class="code-block">
<span class="kw">const</span> <span class="va">angel</span> <span class="pu">= {</span><br>
&nbsp;&nbsp;<span class="va">name</span><span class="pu">:</span>     <span class="st">"Angel Urdaneta"</span><span class="pu">,</span><br>
&nbsp;&nbsp;<span class="va">role</span><span class="pu">:</span>     <span class="st">"Full-Stack Developer"</span><span class="pu">,</span><br>
&nbsp;&nbsp;<span class="va">location</span><span class="pu">:</span> <span class="st">"Colombia 🇨🇴"</span><span class="pu">,</span><br>
&nbsp;&nbsp;<span class="va">focus</span><span class="pu">:</span>    <span class="pu">[</span><span class="st">"AI &amp; Automation"</span><span class="pu">,</span> <span class="st">"Backend &amp; Database"</span><span class="pu">],</span><br>
&nbsp;&nbsp;<span class="va">building</span><span class="pu">:</span> <span class="st">"Proyectos reales para aprender y demostrar mis habilidades"</span><span class="pu">,</span><br>
&nbsp;&nbsp;<span class="va">phone</span><span class="pu">:</span>    <span class="st">"+57 301 367 9860"</span><span class="pu">,</span><br>
&nbsp;&nbsp;<span class="va">email</span><span class="pu">:</span>    <span class="st">"urdanetaangel886@gmail.com"</span><span class="pu">,</span><br>
&nbsp;&nbsp;<span class="va">motto</span><span class="pu">:</span>    <span class="st">"Código limpio, soluciones reales 💡"</span><br>
<span class="pu">};</span>
    </div>
  </section>

  <div class="sec-div"></div>

  <!-- ══════════ CONTACTS ══════════ -->
  <section class="card" id="contacts">
    <div class="c tl"></div><div class="c tr"></div>
    <p class="sec-title">🌐 Contacts</p>
    <div class="contact-row">
      <a class="ct" href="https://github.com/xUr4Sx" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="rgba(255,255,255,0.7)"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>
        github.com/xUr4Sx
      </a>
      <a class="ct" href="https://linkedin.com/in/angel-urdaneta-686a552a7/" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="#0a66c2"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        Angel Urdaneta
      </a>
      <a class="ct" href="mailto:urdanetaangel886@gmail.com">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#ea4335" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 7 10 7 10-7"/></svg>
        urdanetaangel886@gmail.com
      </a>
      <a class="ct" href="https://wa.me/573013679860" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="#25d366"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
        +57 301 367 9860
      </a>
    </div>
  </section>

  <div class="sec-div"></div>

  <!-- ══════════ TECH STACK ══════════ -->
  <section class="card" id="stack">
    <div class="c tl"></div><div class="c tr"></div>
    <p class="sec-title">🖥️ Languages &amp; Tools</p>

    <!-- Frontend -->
    <div class="stack-cat">
      <p class="cat-label"><span>🎨</span> Frontend</p>
      <div class="sk-row">
        <div class="sk" title="HTML5">
          <svg viewBox="0 0 32 32"><path d="M6 2l2.5 22L16 26l7.5-2L26 2z" fill="#e44d26"/><path d="M16 4v20.4l6.1-1.7 2.1-18.7z" fill="#f16529"/><path d="M16 13.5H11.5l-.3-3.5H16V6.5H8.5l.8 9H16zm0 6.5l-.1.1-4.1-1.1-.3-3H9l.6 6.3 6.4 1.8V20z" fill="#ebebeb"/><path d="M16 13.5v3.5h4.1l-.4 4.4-3.7 1v3.6l6.4-1.8 1.6-18H16V13.5z" fill="#fff"/></svg>
          HTML5
        </div>
        <div class="sk" title="CSS3">
          <svg viewBox="0 0 32 32"><path d="M6 2l2.5 22L16 26l7.5-2L26 2z" fill="#1572b6"/><path d="M16 4v20.4l6.1-1.7 2.1-18.7z" fill="#33a9dc"/><path d="M16 13.5H11.5l-.2-2.5H16V7.5H8.8l.7 8H16zm0 6.5l-.1.1-4-1-.3-3H9.3l.5 6 6.2 1.7V20z" fill="#ebebeb"/><path d="M16 13.5v3.5h3.9l-.4 3.9-3.5.9v3.6l6.2-1.7 1.5-17H16v3.5h4.1l-.3 3H16z" fill="#fff"/></svg>
          CSS3
        </div>
        <div class="sk" title="JavaScript">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#f7df1e"/><path d="M9.5 24.5c.7 1.1 1.6 1.9 3.2 1.9 1.4 0 2.2-.7 2.2-1.6 0-1.1-.9-1.5-2.4-2.1l-.8-.4c-2.4-1-4-2.3-4-5 0-2.5 1.9-4.3 4.8-4.3 2.1 0 3.6.7 4.7 2.6l-2.5 1.6c-.6-1-.9-1.5-1.9-1.5s-1.6.6-1.6 1.4c0 1 .6 1.4 2 2l.8.4c2.8 1.2 4.4 2.4 4.4 5.2 0 2.9-2.3 4.6-5.4 4.6-3 0-4.9-1.5-5.8-3.4zm10.8.3c.8 1.4 1.9 2.4 3.8 2.4 1.6 0 2.6-.8 2.6-1.9 0-1.3-1-1.8-2.8-2.5l-.8-.4c-2.8-1.2-4.6-2.6-4.6-5.7 0-2.5 1.9-4.3 4.8-4.3 2.1 0 3.6.7 4.7 2.6l-2.5 1.6c-.6-1-1-1.5-2.1-1.5s-1.6.6-1.6 1.4c0 1 .6 1.4 2 2l.8.4c2.8 1.2 4.4 2.4 4.4 5.2 0 2.9-2.3 4.6-5.4 4.6-3 0-4.9-1.5-5.8-3.4z" fill="#323330"/></svg>
          JavaScript
        </div>
        <div class="sk" title="TypeScript">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#007acc"/><path d="M18 17.5v1.7c.4.2.9.4 1.4.5.5.1 1 .1 1.5.1.5 0 1-.1 1.5-.2.4-.1.8-.3 1.1-.6.3-.2.6-.5.7-.9.2-.4.3-.8.3-1.3 0-.4-.1-.7-.2-1-.1-.3-.3-.5-.5-.7-.2-.2-.5-.4-.8-.5-.3-.2-.6-.3-1-.4-.3-.1-.5-.2-.8-.3-.2-.1-.4-.2-.6-.3-.1-.1-.3-.2-.3-.3-.1-.1-.1-.2-.1-.4 0-.1 0-.2.1-.3.1-.1.1-.2.3-.2.1-.1.3-.1.4-.1.2 0 .4 0 .6.1.2.1.3.1.5.2l.3.3v-1.6c-.3-.1-.7-.2-1.1-.3-.4-.1-.8-.1-1.3-.1-.5 0-.9.1-1.3.2-.4.1-.7.3-1 .6-.3.2-.5.5-.6.8-.2.3-.2.7-.2 1.1 0 .6.2 1.1.5 1.5.3.4.8.7 1.5.9.3.1.6.2.9.3.3.1.5.2.7.3.2.1.3.2.4.3.1.1.1.3.1.4 0 .1 0 .2-.1.4-.1.1-.2.2-.3.3-.1.1-.3.1-.5.2h-.6c-.3 0-.6-.1-.9-.2-.3-.1-.5-.3-.7-.5zM13 14h3V12H7v2h3v9h3v-9z" fill="white"/></svg>
          TypeScript
        </div>
        <div class="sk" title="React">
          <svg viewBox="0 0 32 32"><circle cx="16" cy="16" r="2.5" fill="#61dafb"/><ellipse cx="16" cy="16" rx="12" ry="5" fill="none" stroke="#61dafb" stroke-width="1.5"/><ellipse cx="16" cy="16" rx="12" ry="5" fill="none" stroke="#61dafb" stroke-width="1.5" transform="rotate(60 16 16)"/><ellipse cx="16" cy="16" rx="12" ry="5" fill="none" stroke="#61dafb" stroke-width="1.5" transform="rotate(120 16 16)"/></svg>
          React
        </div>
        <div class="sk" title="Angular">
          <svg viewBox="0 0 32 32"><path d="M16 3L4 7l1.8 15.5L16 29l10.2-6.5L28 7z" fill="#dd0031"/><path d="M16 3v26l10.2-6.5L28 7z" fill="#c3002f"/><path d="M16 8l-6 14h2.3l1.2-3h5l1.2 3H22L16 8zm0 4l1.8 5h-3.6z" fill="white"/></svg>
          Angular
        </div>
        <div class="sk" title="Bootstrap">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="6" fill="#563d7c"/><path d="M10 8h7.5c3.3 0 5.5 1.5 5.5 4.2 0 1.8-1 3-2.5 3.5 1.8.4 3 1.7 3 3.8 0 3-2.3 4.5-6 4.5H10V8zm3 5.5h4c1.5 0 2.5-.7 2.5-2s-1-2-2.5-2H13v4zm0 5.5h4.5c1.7 0 2.7-.8 2.7-2.2s-1-2.3-2.7-2.3H13v4.5z" fill="white"/></svg>
          Bootstrap
        </div>
      </div>
    </div>

    <!-- Backend -->
    <div class="stack-cat">
      <p class="cat-label"><span>⚙️</span> Backend</p>
      <div class="sk-row">
        <div class="sk" title="Node.js">
          <svg viewBox="0 0 32 32"><path d="M16 3L4 10v12l12 7 12-7V10z" fill="#3c873a"/><text x="16" y="20" text-anchor="middle" font-family="sans-serif" font-size="6" font-weight="bold" fill="white">NODE</text></svg>
          Node.js
        </div>
        <div class="sk" title="Python">
          <svg viewBox="0 0 32 32"><path d="M15.9 2C10.2 2 10.6 4.5 10.6 4.5V7h5.5v1H7.2S4 7.7 4 13.5s3.7 5.6 3.7 5.6H9v-2.7s-.1-3.7 3.6-3.7h6.2s3.5.1 3.5-3.4V5.1S22.8 2 15.9 2zm-3.4 2c.6 0 1.1.5 1.1 1.1s-.5 1.1-1.1 1.1S11.4 5.7 11.4 5c0-.6.5-1 1.1-1z" fill="#366a96"/><path d="M16.1 30c5.7 0 5.3-2.5 5.3-2.5V25H16v-1h8.8S28 24.3 28 18.5s-3.7-5.6-3.7-5.6H23v2.7s.1 3.7-3.6 3.7h-6.2S9.7 19.2 9.7 22.7v4.2S9.2 30 16.1 30zm3.4-2c-.6 0-1.1-.5-1.1-1.1s.5-1.1 1.1-1.1 1.1.5 1.1 1.1-.5 1.1-1.1 1.1z" fill="#ffc331"/></svg>
          Python
        </div>
        <div class="sk" title="C#">
          <svg viewBox="0 0 32 32"><path d="M28 8.5l-12-7-12 7v15l12 7 12-7z" fill="#239120"/><text x="16" y="21" text-anchor="middle" font-family="sans-serif" font-size="11" font-weight="bold" fill="white">C#</text></svg>
          C#
        </div>
        <div class="sk" title="PHP">
          <svg viewBox="0 0 32 32"><ellipse cx="16" cy="16" rx="14" ry="9" fill="#8892bf"/><text x="16" y="20" text-anchor="middle" font-family="sans-serif" font-size="9" font-weight="bold" fill="white">php</text></svg>
          PHP
        </div>
        <div class="sk" title="Laravel">
          <svg viewBox="0 0 32 32"><path d="M29 5.5L16.5 3 4 5.5l2 18 10.5 5.5L27 23.5z" fill="#ff2d20"/><text x="16" y="20" text-anchor="middle" font-family="sans-serif" font-size="6" font-weight="bold" fill="white">LARAVEL</text></svg>
          Laravel
        </div>
      </div>
    </div>

    <!-- Databases -->
    <div class="stack-cat">
      <p class="cat-label"><span>🗄️</span> Databases</p>
      <div class="sk-row">
        <div class="sk" title="SQL Server">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#cc2927"/><text x="16" y="14" text-anchor="middle" font-family="sans-serif" font-size="5" font-weight="bold" fill="white">SQL</text><text x="16" y="22" text-anchor="middle" font-family="sans-serif" font-size="5" font-weight="bold" fill="white">SERVER</text></svg>
          SQL Server
        </div>
        <div class="sk" title="MySQL">
          <svg viewBox="0 0 32 32"><path d="M4 8h24v4H4z" fill="#00758f"/><path d="M4 12h24v4H4z" fill="#f29111"/><path d="M4 16h24v8H4z" fill="#00758f"/><text x="16" y="23" text-anchor="middle" font-family="sans-serif" font-size="4.5" font-weight="bold" fill="white">MySQL</text></svg>
          MySQL
        </div>
        <div class="sk" title="PostgreSQL">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#336791"/><ellipse cx="16" cy="10" rx="9" ry="4" fill="#fff" opacity="0.9"/><rect x="7" y="10" width="18" height="12" fill="#336791"/><ellipse cx="16" cy="22" rx="9" ry="4" fill="#fff" opacity="0.7"/><text x="16" y="18" text-anchor="middle" font-family="sans-serif" font-size="4" font-weight="bold" fill="white">SQL</text></svg>
          PostgreSQL
        </div>
        <div class="sk" title="Redis">
          <svg viewBox="0 0 32 32"><ellipse cx="16" cy="22" rx="12" ry="4" fill="#912626"/><rect x="4" y="10" width="24" height="12" fill="#d82c20"/><ellipse cx="16" cy="10" rx="12" ry="4" fill="#f05032"/><text x="16" y="18" text-anchor="middle" font-family="sans-serif" font-size="5" font-weight="bold" fill="white">REDIS</text></svg>
          Redis
        </div>
      </div>
    </div>

    <!-- AI & Automation -->
    <div class="stack-cat">
      <p class="cat-label"><span>🤖</span> AI &amp; Automation</p>
      <div class="sk-row">
        <div class="sk" title="n8n">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="6" fill="#ea4b71"/><text x="16" y="21" text-anchor="middle" font-family="sans-serif" font-size="10" font-weight="bold" fill="white">n8n</text></svg>
          n8n
        </div>
        <div class="sk" title="OpenAI">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="6" fill="#412991"/><circle cx="16" cy="16" r="7" fill="none" stroke="white" stroke-width="2"/><circle cx="16" cy="16" r="3" fill="white"/></svg>
          OpenAI
        </div>
        <div class="sk" title="AWS">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#232f3e"/><text x="16" y="16" text-anchor="middle" font-family="sans-serif" font-size="6" font-weight="bold" fill="#ff9900">AWS</text><path d="M8 20c0 1.4 3.6 2.5 8 2.5s8-1.1 8-2.5" stroke="#ff9900" stroke-width="1.5" fill="none"/></svg>
          AWS
        </div>
        <div class="sk" title="Google Cloud">
          <svg viewBox="0 0 32 32"><path d="M19.5 10h-7L9 14l3 5h8l3-5z" fill="#4285f4"/><circle cx="12.5" cy="14" r="3" fill="#ea4335"/><circle cx="19.5" cy="14" r="3" fill="#fbbc04"/><circle cx="16" cy="22" r="3" fill="#34a853"/></svg>
          Google Cloud
        </div>
      </div>
    </div>

    <!-- Tools -->
    <div class="stack-cat" style="margin-bottom:0">
      <p class="cat-label"><span>🧰</span> Tools</p>
      <div class="sk-row">
        <div class="sk" title="Git">
          <svg viewBox="0 0 32 32"><path d="M29.5 14.5l-12-12a2.1 2.1 0 00-3 0l-2.6 2.6 3.3 3.3c.8-.3 1.7-.1 2.3.5.6.6.8 1.5.5 2.3l3.2 3.2c.8-.3 1.7-.1 2.3.5a2.1 2.1 0 010 3 2.1 2.1 0 01-3-.1 2.1 2.1 0 01-.4-2.3L17 12.8v8.5a2.1 2.1 0 011.2 3.8 2.1 2.1 0 01-3-3 2.1 2.1 0 011.3-.5V12.7a2.1 2.1 0 01-.6-3.5L12.6 5.9 2.5 16a2.1 2.1 0 000 3l12 12a2.1 2.1 0 003 0l12-12a2.1 2.1 0 000-2.5z" fill="#f05033"/></svg>
          Git
        </div>
        <div class="sk" title="GitHub">
          <svg viewBox="0 0 24 24" fill="rgba(255,255,255,0.85)"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>
          GitHub
        </div>
        <div class="sk" title="Docker">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#0db7ed" opacity="0.15"/><path d="M4 16c0 4 3.5 7 8 7h8c4.5 0 8-3 8-7" fill="none" stroke="#0db7ed" stroke-width="1.5"/><rect x="7" y="10" width="4" height="4" rx="1" fill="#0db7ed"/><rect x="12" y="10" width="4" height="4" rx="1" fill="#0db7ed"/><rect x="17" y="10" width="4" height="4" rx="1" fill="#0db7ed"/><rect x="12" y="15" width="4" height="4" rx="1" fill="#0db7ed" opacity="0.6"/></svg>
          Docker
        </div>
        <div class="sk" title="Apache">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#d42029" opacity="0.15"/><text x="16" y="20" text-anchor="middle" font-family="sans-serif" font-size="7" font-weight="bold" fill="#d42029">APACHE</text></svg>
          Apache
        </div>
        <div class="sk" title="VS Code">
          <svg viewBox="0 0 32 32"><path d="M24 4L12 16 6 11 4 13l8 8-8 8 2 2 6-5 12 8 4-2V6z" fill="#007acc"/></svg>
          VS Code
        </div>
        <div class="sk" title="npm">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#cb0000"/><rect x="6" y="10" width="20" height="12" fill="white"/><rect x="9" y="13" width="5" height="6" fill="#cb0000"/><rect x="18" y="13" width="5" height="3" fill="#cb0000"/></svg>
          npm
        </div>
      </div>
    </div>
  </section>

  <div class="sec-div"></div>

  <!-- ══════════ STATS ══════════ -->
  <section class="card" id="stats">
    <div class="c tl"></div><div class="c tr"></div>
    <p class="sec-title">📊 Stats</p>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-num" id="cnt-exp">3+</div>
        <div class="stat-label">Años de experiencia</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">16+</div>
        <div class="stat-label">Tecnologías</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">Full</div>
        <div class="stat-label">Stack Developer</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">∞</div>
        <div class="stat-label">Ganas de aprender</div>
      </div>
    </div>
  </section>

  <div class="sec-div"></div>

  <!-- ══════════ FOOTER ══════════ -->
  <section class="card" id="footer">
    <div class="c bl"></div><div class="c br"></div>
    <div class="sparkle" style="bottom:20px;right:22px;font-size:13px">✦</div>
    <div class="footer-line"></div>
    <p class="footer-text">⭐ <strong>Código limpio, soluciones reales.</strong> — Angel Urdaneta 2025</p>
  </section>

</div>
</body>
</html>
