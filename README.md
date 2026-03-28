<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GitHub Profile Banner</title>
<link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500&family=Plus+Jakarta+Sans:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;}
@keyframes bgMove{0%{background-position:0% 50%}50%{background-position:100% 50%}100%{background-position:0% 50%}}
@keyframes spinRing{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}
@keyframes pulseGlow{0%,100%{box-shadow:0 0 0 0 rgba(139,92,246,.3)}50%{box-shadow:0 0 0 12px rgba(139,92,246,0)}}
@keyframes fadeUp{from{opacity:0;transform:translateY(14px)}to{opacity:1;transform:translateY(0)}}
@keyframes tagFloat{0%,100%{transform:translateY(0)}50%{transform:translateY(-3px)}}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
@keyframes orb1{0%,100%{transform:translate(0,0)}50%{transform:translate(30px,-20px)}}
@keyframes orb2{0%,100%{transform:translate(0,0)}50%{transform:translate(-20px,25px)}}
@keyframes shimmer{0%{background-position:-200% center}100%{background-position:200% center}}
@keyframes cursor{0%,100%{opacity:1}50%{opacity:0}}

body{background:#0a0a0f;display:flex;align-items:center;justify-content:center;min-height:100vh;padding:20px;}

.banner{
  font-family:'Plus Jakarta Sans',sans-serif;
  border-radius:18px;
  overflow:hidden;
  position:relative;
  padding:28px 32px;
  background:linear-gradient(-45deg,#0f0c29,#302b63,#1a1040,#0d1b3e);
  background-size:400% 400%;
  animation:bgMove 10s ease infinite;
  width:900px;
  max-width:100%;
  border:1px solid rgba(139,92,246,0.2);
}

/* Orbs */
.orb{position:absolute;border-radius:50%;filter:blur(70px);pointer-events:none;}
.orb1{width:260px;height:260px;background:#7c3aed33;top:-80px;left:-60px;animation:orb1 8s ease-in-out infinite;}
.orb2{width:200px;height:200px;background:#0891b233;bottom:-60px;right:100px;animation:orb2 9s ease-in-out infinite;}
.orb3{width:140px;height:140px;background:#db277733;top:30px;right:200px;}

/* Grid */
.grid{position:absolute;inset:0;background-image:linear-gradient(rgba(255,255,255,.018) 1px,transparent 1px),linear-gradient(90deg,rgba(255,255,255,.018) 1px,transparent 1px);background-size:36px 36px;}

/* Top/bottom lines */
.topbar{position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,#8b5cf6,#06b6d4,#f472b6,#8b5cf6,transparent);}
.bottombar{position:absolute;bottom:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,#4f46e5,#06b6d4,#4f46e5,transparent);}

/* Inner layout */
.inner{position:relative;z-index:5;display:flex;align-items:center;gap:24px;}

/* Avatar */
.av-wrap{flex-shrink:0;position:relative;width:90px;height:90px;}
.ring{position:absolute;inset:-8px;border-radius:50%;border:1.5px solid transparent;background:linear-gradient(#1a1040,#1a1040) padding-box,linear-gradient(135deg,#8b5cf6,#06b6d4,#f472b6,#8b5cf6) border-box;animation:spinRing 5s linear infinite;}
.ring2{position:absolute;inset:-3px;border-radius:50%;border:1px solid rgba(139,92,246,0.2);}
.avatar{width:90px;height:90px;border-radius:50%;overflow:hidden;position:relative;z-index:2;animation:pulseGlow 3s ease-in-out infinite;}
.avatar img{width:100%;height:100%;object-fit:cover;}

/* Info */
.info{flex:1;animation:fadeUp .7s ease .1s both;}

.name{
  font-size:26px;font-weight:800;letter-spacing:-.3px;margin-bottom:2px;
  background:linear-gradient(90deg,#fff 0%,#c4b5fd 40%,#67e8f9 80%,#fff 100%);
  background-size:200%;
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  animation:shimmer 5s linear infinite;
}

.role{
  font-family:'Fira Code',monospace;font-size:12px;color:#a78bfa;
  letter-spacing:1.2px;margin-bottom:3px;
}
.role::before{content:'// ';color:#4b5563;}

/* Typewriter */
.typewriter-wrap{font-family:'Fira Code',monospace;font-size:11px;color:#64748b;margin-bottom:14px;min-height:16px;}
.typewriter-wrap span.typed{color:#38bdf8;}
.cursor{display:inline-block;width:7px;height:11px;background:#7c3aed;border-radius:1px;margin-left:2px;vertical-align:middle;animation:cursor 0.8s ease-in-out infinite;}

/* Tags */
.tags{display:flex;flex-direction:column;gap:6px;}
.row{display:flex;align-items:center;gap:5px;flex-wrap:wrap;}
.row-label{font-family:'Fira Code',monospace;font-size:9px;color:#475569;letter-spacing:2px;width:46px;flex-shrink:0;}
.tag{font-family:'Fira Code',monospace;font-size:10px;padding:4px 11px;border-radius:20px;letter-spacing:.3px;}
.tReact{background:#0c2340;color:#7dd3fc;border:1px solid #0369a1;animation:tagFloat 3.2s ease-in-out infinite 0s}
.tNext{background:#18181b;color:#e4e4e7;border:1px solid #3f3f46;animation:tagFloat 3.2s ease-in-out infinite .2s}
.tTS{background:#1a0f2e;color:#c4b5fd;border:1px solid #5b21b6;animation:tagFloat 3.2s ease-in-out infinite .4s}
.tNode{background:#052e16;color:#6ee7b7;border:1px solid #065f46;animation:tagFloat 3.2s ease-in-out infinite .6s}
.tExpress{background:#1c1c1c;color:#d1d5db;border:1px solid #374151;animation:tagFloat 3.2s ease-in-out infinite .8s}
.tMongo{background:#052e16;color:#86efac;border:1px solid #166534;animation:tagFloat 3.2s ease-in-out infinite 1s}
.tPG{background:#0c1a3a;color:#93c5fd;border:1px solid #1e40af;animation:tagFloat 3.2s ease-in-out infinite 1.2s}
.tPrisma{background:#1a0f2e;color:#c4b5fd;border:1px solid #5b21b6;animation:tagFloat 3.2s ease-in-out infinite 1.4s}

/* Status card */
.card{
  flex-shrink:0;
  background:rgba(255,255,255,.04);
  border:1px solid rgba(255,255,255,.08);
  border-radius:14px;
  padding:18px 20px;
  display:flex;flex-direction:column;gap:10px;
  backdrop-filter:blur(8px);
  min-width:190px;
  animation:fadeUp .7s ease .3s both;
}
.card-title{font-family:'Fira Code',monospace;font-size:9px;color:#475569;letter-spacing:2.5px;margin-bottom:2px;}
.stat{font-family:'Fira Code',monospace;font-size:11px;color:#94a3b8;display:flex;align-items:center;gap:8px;white-space:nowrap;}
.stat .val{color:#e2e8f0;font-weight:500;}
.dot{width:6px;height:6px;border-radius:50%;flex-shrink:0;}
.dg{background:#22c55e;box-shadow:0 0 7px #22c55e;animation:blink 2s ease-in-out infinite;}
.dp{background:#a78bfa;box-shadow:0 0 7px #a78bfa;animation:blink 2.5s ease-in-out infinite .5s;}
.dc{background:#06b6d4;box-shadow:0 0 7px #06b6d4;animation:blink 3s ease-in-out infinite 1s;}
.divider{height:1px;background:rgba(255,255,255,.07);}
.email{font-family:'Fira Code',monospace;font-size:10px;color:#4b5563;}
</style>
</head>
<body>
<div class="banner">
  <div class="orb orb1"></div>
  <div class="orb orb2"></div>
  <div class="orb orb3"></div>
  <div class="grid"></div>
  <div class="topbar"></div>
  <div class="bottombar"></div>

  <div class="inner">
    <!-- Avatar -->
    <div class="av-wrap">
      <div class="ring"></div>
      <div class="ring2"></div>
      <div class="avatar">
        <img src="data:image/jpeg;base64,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" alt="Selim Islam"/>
      </div>
    </div>

    <!-- Info -->
    <div class="info">
      <div class="name">MD Selim Islam</div>
      <div class="role">Frontend Developer</div>
      <div class="typewriter-wrap">
        <span class="typed" id="typed"></span><span class="cursor" id="cursor"></span>
      </div>
      <div class="tags">
        <div class="row">
          <span class="row-label">FRONT</span>
          <span class="tag tReact">React.js</span>
          <span class="tag tNext">Next.js</span>
          <span class="tag tTS">TypeScript</span>
        </div>
        <div class="row">
          <span class="row-label">BACK</span>
          <span class="tag tNode">Node.js</span>
          <span class="tag tExpress">Express.js</span>
        </div>
        <div class="row">
          <span class="row-label">DB/ORM</span>
          <span class="tag tMongo">MongoDB</span>
          <span class="tag tPG">PostgreSQL</span>
          <span class="tag tPrisma">Prisma</span>
        </div>
      </div>
    </div>

    <!-- Status Card -->
    <div class="card">
      <div class="card-title">// STATUS</div>
      <div class="stat"><span class="dot dg"></span><span>status</span><span class="val">open to work</span></div>
      <div class="stat"><span class="dot dp"></span><span>focus</span><span class="val">full-stack</span></div>
      <div class="stat"><span class="dot dc"></span><span>from</span><span class="val">Bangladesh 🇧🇩</span></div>
      <div class="divider"></div>
      <div class="email">✉ salimislam0036@gmail.com</div>
    </div>
  </div>
</div>

<script>
const phrases = [
  "Crafting scalable apps · MERN · Next.js",
  "Building clean & responsive UIs 💻",
  "Exploring Next.js & PostgreSQL 🚀",
  "Passionate about clean code ✨",
  "Open to work · Bangladesh 🇧🇩"
];

let phraseIdx = 0, charIdx = 0, deleting = false;
const el = document.getElementById('typed');

function type() {
  const current = phrases[phraseIdx];
  if (!deleting) {
    el.textContent = current.slice(0, ++charIdx);
    if (charIdx === current.length) {
      deleting = true;
      setTimeout(type, 1800);
      return;
    }
  } else {
    el.textContent = current.slice(0, --charIdx);
    if (charIdx === 0) {
      deleting = false;
      phraseIdx = (phraseIdx + 1) % phrases.length;
    }
  }
  setTimeout(type, deleting ? 40 : 60);
}
type();
</script>
</body>
</html>
