<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ronnel Zamora — Software Developer</title>
<meta name="description" content="Portfolio of Ronnel Zamora, software developer.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,500;9..144,600&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#FAFAF9;
    --bg-raised:#FFFFFF;
    --ink:#15171C;
    --ink-soft:#6B7078;
    --ink-faint:#9A9DA4;
    --accent:#3452FF;
    --accent-ink:#1E3AE0;
    --line:#E5E4DF;
    --line-strong:#D3D2CB;
    --added:#1F9D55;
    --font-display:'Fraunces', serif;
    --font-body:'Inter', -apple-system, sans-serif;
    --font-mono:'JetBrains Mono', monospace;
    --maxw:920px;
  }

  *{margin:0;padding:0;box-sizing:border-box;}

  html{scroll-behavior:smooth;}

  body{
    background:var(--bg);
    color:var(--ink);
    font-family:var(--font-body);
    font-size:16px;
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }

  a{color:inherit;text-decoration:none;}

  ::selection{background:var(--accent);color:#fff;}

  .wrap{max-width:var(--maxw);margin:0 auto;padding:0 32px;}

  /* ---------- Nav ---------- */
  header{
    position:sticky;top:0;z-index:50;
    background:rgba(250,250,249,0.85);
    backdrop-filter:blur(10px);
    -webkit-backdrop-filter:blur(10px);
    border-bottom:1px solid var(--line);
  }
  nav{
    max-width:var(--maxw);margin:0 auto;padding:18px 32px;
    display:flex;align-items:center;justify-content:space-between;
  }
  .logo{
    font-family:var(--font-mono);
    font-size:14px;font-weight:500;
    display:flex;align-items:center;gap:8px;
  }
  .logo .dot{width:7px;height:7px;border-radius:50%;background:var(--added);display:inline-block;}
  .navlinks{display:flex;gap:28px;font-size:14px;color:var(--ink-soft);}
  .navlinks a{position:relative;padding:2px 0;transition:color .15s ease;}
  .navlinks a:hover{color:var(--ink);}
  .navlinks a::after{
    content:'';position:absolute;left:0;bottom:-2px;width:0;height:1px;
    background:var(--accent);transition:width .2s ease;
  }
  .navlinks a:hover::after{width:100%;}
  .nav-cta{
    font-family:var(--font-mono);font-size:13px;
    border:1px solid var(--line-strong);border-radius:6px;
    padding:7px 14px;transition:all .15s ease;
  }
  .nav-cta:hover{border-color:var(--accent);color:var(--accent);}
  .menu-btn{display:none;background:none;border:none;cursor:pointer;padding:4px;}
  .menu-btn span{display:block;width:20px;height:1.5px;background:var(--ink);margin:5px 0;}

  /* ---------- Sections generic ---------- */
  section{padding:96px 0;border-bottom:1px solid var(--line);}
  section:last-of-type{border-bottom:none;}
  .eyebrow{
    font-family:var(--font-mono);font-size:13px;color:var(--accent);
    text-transform:uppercase;letter-spacing:.08em;margin-bottom:14px;
    display:flex;align-items:center;gap:8px;
  }
  .eyebrow::before{content:'';width:16px;height:1px;background:var(--accent);display:inline-block;}
  h2{font-family:var(--font-display);font-weight:500;font-size:clamp(28px,4vw,38px);letter-spacing:-0.01em;margin-bottom:8px;}
  .section-intro{color:var(--ink-soft);max-width:520px;margin-bottom:56px;font-size:16px;}

  .reveal{opacity:0;transform:translateY(16px);transition:opacity .6s ease, transform .6s ease;}
  .reveal.in{opacity:1;transform:translateY(0);}

  /* ---------- Hero ---------- */
  #hero{
    min-height:88vh;display:flex;flex-direction:column;justify-content:center;
    padding:60px 0 96px;
  }
  .hero-kicker{
    font-family:var(--font-mono);font-size:14px;color:var(--ink-soft);
    display:flex;align-items:center;gap:10px;margin-bottom:24px;
  }
  .hero-kicker .cursor{
    display:inline-block;width:8px;height:16px;background:var(--accent);
    animation:blink 1.1s step-end infinite;
  }
  @keyframes blink{50%{opacity:0;}}
  h1{
    font-family:var(--font-display);
    font-weight:500;
    font-size:clamp(44px,8vw,84px);
    line-height:0.98;
    letter-spacing:-0.02em;
    margin-bottom:28px;
    max-width:820px;
  }
  h1 em{font-style:italic;color:var(--accent);}
  .hero-sub{
    font-size:19px;color:var(--ink-soft);max-width:560px;margin-bottom:40px;
    line-height:1.65;
  }
  .hero-actions{display:flex;gap:14px;flex-wrap:wrap;margin-bottom:64px;}
  .btn{
    font-family:var(--font-body);font-weight:500;font-size:15px;
    padding:13px 24px;border-radius:8px;transition:all .18s ease;
    display:inline-flex;align-items:center;gap:8px;
  }
  .btn-primary{background:var(--ink);color:#fff;}
  .btn-primary:hover{background:var(--accent);transform:translateY(-1px);}
  .btn-ghost{border:1px solid var(--line-strong);color:var(--ink);}
  .btn-ghost:hover{border-color:var(--ink);}

  .hero-meta{
    display:flex;gap:40px;flex-wrap:wrap;
    font-family:var(--font-mono);font-size:13px;color:var(--ink-faint);
    padding-top:28px;border-top:1px solid var(--line);
  }
  .hero-meta strong{color:var(--ink);font-weight:500;}

  /* ---------- About ---------- */
  .about-grid{display:grid;grid-template-columns:1.4fr 1fr;gap:64px;align-items:start;}
  .about-body p{color:var(--ink-soft);margin-bottom:18px;font-size:16px;max-width:52ch;}
  .about-body p strong{color:var(--ink);font-weight:500;}
  .facts{list-style:none;}
  .facts li{
    display:flex;justify-content:space-between;padding:14px 0;
    border-bottom:1px solid var(--line);font-size:14px;
  }
  .facts li:first-child{padding-top:0;}
  .facts .label{color:var(--ink-faint);font-family:var(--font-mono);}
  .facts .value{color:var(--ink);font-weight:500;text-align:right;}

  /* ---------- Projects ---------- */
  .project{
    display:grid;grid-template-columns:64px 1fr auto;gap:24px;align-items:start;
    padding:32px 0;border-top:1px solid var(--line);
    transition:padding-left .2s ease;
  }
  .project:hover{padding-left:8px;}
  .project:last-child{border-bottom:1px solid var(--line);}
  .project-index{font-family:var(--font-mono);color:var(--ink-faint);font-size:14px;padding-top:4px;}
  .project-title{
    font-family:var(--font-display);font-weight:500;font-size:24px;
    margin-bottom:8px;display:flex;align-items:center;gap:10px;
  }
  .project-title a{transition:color .15s ease;}
  .project:hover .project-title a{color:var(--accent);}
  .status{
    font-family:var(--font-mono);font-size:11px;padding:2px 8px;border-radius:20px;
    display:inline-flex;align-items:center;gap:5px;font-weight:500;
    border:1px solid var(--line-strong);color:var(--ink-soft);
  }
  .status.shipped{color:var(--added);border-color:var(--added);}
  .status.shipped::before{content:'';width:5px;height:5px;border-radius:50%;background:var(--added);}
  .project-desc{color:var(--ink-soft);font-size:15px;max-width:56ch;margin-bottom:14px;}
  .tags{display:flex;flex-wrap:wrap;gap:8px;}
  .tag{
    font-family:var(--font-mono);font-size:12px;color:var(--ink-soft);
    background:var(--bg-raised);border:1px solid var(--line);
    padding:3px 9px;border-radius:5px;
  }
  .tag .plus{color:var(--added);margin-right:2px;}
  .project-links{display:flex;flex-direction:column;gap:10px;align-items:flex-end;padding-top:6px;}
  .project-links a{
    font-family:var(--font-mono);font-size:13px;color:var(--ink-soft);
    display:flex;align-items:center;gap:6px;white-space:nowrap;transition:color .15s ease;
  }
  .project-links a:hover{color:var(--accent);}

  /* ---------- Skills ---------- */
  .skill-groups{display:grid;grid-template-columns:repeat(3,1fr);gap:40px;}
  .skill-group-label{
    font-family:var(--font-mono);font-size:12px;color:var(--ink-faint);
    text-transform:uppercase;letter-spacing:.06em;margin-bottom:16px;
  }
  .skill-list{display:flex;flex-direction:column;gap:2px;}
  .skill-row{
    display:flex;align-items:center;gap:10px;padding:9px 0;
    border-bottom:1px solid var(--line);font-size:15px;
  }
  .skill-row .plus{font-family:var(--font-mono);color:var(--added);font-size:14px;}

  /* ---------- Contact ---------- */
  #contact{text-align:left;}
  .contact-inner{display:flex;justify-content:space-between;align-items:flex-end;flex-wrap:wrap;gap:40px;}
  .contact-big{font-family:var(--font-display);font-weight:500;font-size:clamp(32px,5vw,52px);letter-spacing:-0.01em;max-width:600px;line-height:1.1;}
  .contact-big a{border-bottom:2px solid var(--accent);}
  .contact-big a:hover{color:var(--accent);}
  .social-list{display:flex;flex-direction:column;gap:12px;}
  .social-list a{
    font-family:var(--font-mono);font-size:14px;color:var(--ink-soft);
    display:flex;align-items:center;gap:8px;
  }
  .social-list a:hover{color:var(--accent);}
  .social-list .arrow{transition:transform .15s ease;}
  .social-list a:hover .arrow{transform:translate(2px,-2px);}

  footer{
    padding:28px 0;display:flex;justify-content:space-between;
    font-family:var(--font-mono);font-size:12px;color:var(--ink-faint);
    flex-wrap:wrap;gap:8px;
  }

  /* ---------- Mobile ---------- */
  @media (max-width:760px){
    .navlinks{display:none;}
    .menu-btn{display:block;}
    .about-grid{grid-template-columns:1fr;gap:40px;}
    .skill-groups{grid-template-columns:1fr;gap:28px;}
    .project{grid-template-columns:1fr;gap:10px;}
    .project-index{display:none;}
    .project-links{align-items:flex-start;flex-direction:row;gap:20px;}
    .contact-inner{flex-direction:column;align-items:flex-start;}
    section{padding:64px 0;}
    .wrap{padding:0 20px;}
    nav{padding:16px 20px;}
  }

  @media (prefers-reduced-motion:reduce){
    *{animation-duration:0.01ms !important;transition-duration:0.01ms !important;}
    html{scroll-behavior:auto;}
  }

  :focus-visible{outline:2px solid var(--accent);outline-offset:2px;}
</style>
</head>
<body>

<header>
  <nav>
    <div class="logo"><span class="dot"></span>ronnel.zamora</div>
    <div class="navlinks">
      <a href="#about">About</a>
      <a href="#work">Work</a>
      <a href="#skills">Skills</a>
      <a href="#contact">Contact</a>
    </div>
    <a class="nav-cta" href="#contact">say hi ↗</a>
  </nav>
</header>

<main class="wrap">

  <section id="hero">
    <div class="hero-kicker">
      <span class="cursor"></span>
      status: open to new-grad software roles
    </div>
    <h1>Building software<br>that's <em>obviously</em> well made.</h1>
    <p class="hero-sub">
      I'm Ronnel Zamora, a computer science graduate who likes taking ideas from a blank
      file to something people actually use. I care about clean code, fast feedback loops,
      and interfaces that don't need a manual.
    </p>
    <div class="hero-actions">
      <a class="btn btn-primary" href="#work">View my work</a>
      <a class="btn btn-ghost" href="#contact">Get in touch</a>
    </div>
    <div class="hero-meta">
      <div><strong>B.S. Computer Science</strong> · 2026</div>
      <div><strong>4</strong> shipped projects</div>
      <div><strong>Based in</strong> Manila, PH</div>
    </div>
  </section>

  <section id="about">
    <div class="eyebrow">About</div>
    <div class="about-grid">
      <div class="about-body reveal">
        <p>
          I got into programming by trying to fix a scoreboard spreadsheet for a
          school club, and never really stopped. Since then I've spent four years
          studying <strong>computer science</strong>, building side projects most
          weekends, and slowly getting less embarrassed about my old code.
        </p>
        <p>
          I like working across the stack, but I'm happiest when I'm turning a rough
          product idea into something with a clear structure &mdash; the kind of code
          a teammate can read without a walkthrough. Outside of school projects, I've
          contributed to a couple of open-source tools and mentored first-year students
          in my department's coding club.
        </p>
        <p>
          Right now I'm looking for a <strong>software engineering role</strong> where
          I can keep learning from people who've shipped more than I have.
        </p>
      </div>
      <ul class="facts reveal">
        <li><span class="label">education</span><span class="value">B.S. Computer Science</span></li>
        <li><span class="label">graduating</span><span class="value">June 2026</span></li>
        <li><span class="label">focus</span><span class="value">Full-stack &amp; systems</span></li>
        <li><span class="label">based in</span><span class="value">Manila, Philippines</span></li>
        <li><span class="label">available</span><span class="value">Full-time, remote or on-site</span></li>
      </ul>
    </div>
  </section>

  <section id="work">
    <div class="eyebrow">Selected work</div>
    <h2>Things I've built</h2>
    <p class="section-intro">A few projects from coursework, hackathons, and weekends. Each one taught me something I use in the next.</p>

    <div class="project reveal">
      <div class="project-index">01</div>
      <div>
        <div class="project-title"><a href="#">Routine <span class="status shipped">shipped</span></a></div>
        <p class="project-desc">A habit-tracking app with a shared-accountability feed, built for my senior capstone. Handles 400+ daily active test users during the pilot.</p>
        <div class="tags">
          <span class="tag"><span class="plus">+</span>React</span>
          <span class="tag"><span class="plus">+</span>Node.js</span>
          <span class="tag"><span class="plus">+</span>PostgreSQL</span>
          <span class="tag"><span class="plus">+</span>Docker</span>
        </div>
      </div>
      <div class="project-links">
        <a href="#">Live site ↗</a>
        <a href="#">Source ↗</a>
      </div>
    </div>

    <div class="project reveal">
      <div class="project-index">02</div>
      <div>
        <div class="project-title"><a href="#">Pathfind <span class="status shipped">shipped</span></a></div>
        <p class="project-desc">An interactive visualizer for graph search algorithms &mdash; A*, Dijkstra, BFS &mdash; built to help classmates study for our algorithms final.</p>
        <div class="tags">
          <span class="tag"><span class="plus">+</span>TypeScript</span>
          <span class="tag"><span class="plus">+</span>Canvas API</span>
          <span class="tag"><span class="plus">+</span>Vite</span>
        </div>
      </div>
      <div class="project-links">
        <a href="#">Live site ↗</a>
        <a href="#">Source ↗</a>
      </div>
    </div>

    <div class="project reveal">
      <div class="project-index">03</div>
      <div>
        <div class="project-title"><a href="#">Mess Hall <span class="status">in progress</span></a></div>
        <p class="project-desc">A CLI tool that parses a fridge inventory and suggests recipes, with a small local model doing the matching. Weekend project, still growing.</p>
        <div class="tags">
          <span class="tag"><span class="plus">+</span>Python</span>
          <span class="tag"><span class="plus">+</span>SQLite</span>
          <span class="tag"><span class="plus">+</span>Click</span>
        </div>
      </div>
      <div class="project-links">
        <a href="#">Source ↗</a>
      </div>
    </div>

    <div class="project reveal">
      <div class="project-index">04</div>
      <div>
        <div class="project-title"><a href="#">Campus API <span class="status shipped">shipped</span></a></div>
        <p class="project-desc">A REST API wrapping my university's public course catalog, used by three other student projects including a schedule builder.</p>
        <div class="tags">
          <span class="tag"><span class="plus">+</span>FastAPI</span>
          <span class="tag"><span class="plus">+</span>Redis</span>
          <span class="tag"><span class="plus">+</span>Railway</span>
        </div>
      </div>
      <div class="project-links">
        <a href="#">Docs ↗</a>
        <a href="#">Source ↗</a>
      </div>
    </div>
  </section>

  <section id="skills">
    <div class="eyebrow">Skills &amp; technologies</div>
    <h2>What I work with</h2>
    <p class="section-intro">Tools I reach for most, roughly grouped by where they show up in a project.</p>

    <div class="skill-groups">
      <div class="reveal">
        <div class="skill-group-label">Languages</div>
        <div class="skill-list">
          <div class="skill-row"><span class="plus">+</span>JavaScript / TypeScript</div>
          <div class="skill-row"><span class="plus">+</span>Python</div>
          <div class="skill-row"><span class="plus">+</span>Java</div>
          <div class="skill-row"><span class="plus">+</span>SQL</div>
          <div class="skill-row"><span class="plus">+</span>C</div>
        </div>
      </div>
      <div class="reveal">
        <div class="skill-group-label">Frameworks &amp; libraries</div>
        <div class="skill-list">
          <div class="skill-row"><span class="plus">+</span>React</div>
          <div class="skill-row"><span class="plus">+</span>Node.js / Express</div>
          <div class="skill-row"><span class="plus">+</span>FastAPI</div>
          <div class="skill-row"><span class="plus">+</span>Tailwind CSS</div>
          <div class="skill-row"><span class="plus">+</span>Pandas</div>
        </div>
      </div>
      <div class="reveal">
        <div class="skill-group-label">Tools &amp; platforms</div>
        <div class="skill-list">
          <div class="skill-row"><span class="plus">+</span>Git / GitHub</div>
          <div class="skill-row"><span class="plus">+</span>Docker</div>
          <div class="skill-row"><span class="plus">+</span>PostgreSQL</div>
          <div class="skill-row"><span class="plus">+</span>AWS (EC2, S3)</div>
          <div class="skill-row"><span class="plus">+</span>Linux</div>
        </div>
      </div>
    </div>
  </section>

  <section id="contact">
    <div class="eyebrow">Get in touch</div>
    <div class="contact-inner">
      <div class="contact-big reveal">
        Have a role in mind, or just want to talk shop?<br>
        <a href="mailto:ronnelzamora00@gmail.com">ronnelzamora00@gmail.com</a>
      </div>
      <div class="social-list reveal">
        <a href="#">GitHub <span class="arrow">↗</span></a>
        <a href="#">LinkedIn <span class="arrow">↗</span></a>
        <a href="#">Resume (PDF) <span class="arrow">↗</span></a>
      </div>
    </div>
  </section>

</main>

<footer class="wrap">
  <span>&copy; 2026 Ronnel Zamora</span>
  <span>Built from scratch, no template</span>
</footer>

<script>
  const io = new IntersectionObserver((entries)=>{
    entries.forEach(e=>{
      if(e.isIntersecting){ e.target.classList.add('in'); io.unobserve(e.target); }
    });
  }, {threshold:0.15});
  document.querySelectorAll('.reveal').forEach(el=>io.observe(el));
</script>

</body>
</html>
