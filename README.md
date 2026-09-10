[index.html](https://github.com/user-attachments/files/32057221/index.html)
# IHI-Work-Styles<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Work Styles Inventory</title>
<style>
  :root{
    --paper:#FBFAF7; --ink:#1F2A3A; --ink-soft:#5B6473; --rule:#D9DCE3;
    --steel:#7A8FB5; --navy:#2E3F63;
    --analytical:#3F6E9C; --driver:#B4462F; --amiable:#3D8A5F; --expressive:#C4862A;
    --radius:10px;
  }
  *{box-sizing:border-box}
  html,body{margin:0;background:var(--paper);color:var(--ink);font:16px/1.5 -apple-system,"Segoe UI",Helvetica,Arial,sans-serif}
  h1,h2,h3{font-family:Georgia,"Times New Roman",serif;font-weight:400;margin:0}
  .wrap{max-width:560px;margin:0 auto;padding:20px 18px 60px}
  .band{height:8px;background:var(--steel);border-radius:4px;margin:6px 0 22px}
  h1{font-size:30px;line-height:1.15}
  .lede{color:var(--ink-soft);margin:10px 0 0}
  .progress{display:flex;gap:6px;margin:22px 0 10px}
  .progress span{flex:1;height:5px;border-radius:3px;background:var(--rule)}
  .progress span.done{background:var(--navy)}
  .progress span.cur{background:var(--steel)}
  .qnum{color:var(--ink-soft);font-size:14px}
  h2{font-size:23px;margin:4px 0 14px;line-height:1.25}
  .hint{font-size:14px;color:var(--ink-soft);margin:0 0 14px}
  .opts{display:flex;flex-direction:column;gap:10px}
  .opt{display:flex;align-items:center;gap:14px;width:100%;text-align:left;
       background:#fff;border:1.5px solid var(--rule);border-radius:var(--radius);
       padding:14px 16px;font:inherit;color:var(--ink);cursor:pointer}
  .opt:focus-visible{outline:3px solid var(--steel);outline-offset:2px}
  .opt.ranked{border-color:var(--navy);background:#F1F4FA}
  .badge{flex:none;width:34px;height:34px;border-radius:50%;border:1.5px dashed var(--rule);
         display:grid;place-items:center;font-family:Georgia,serif;font-size:19px;color:var(--ink-soft)}
  .ranked .badge{border:none;background:var(--navy);color:#fff}
  .nav{display:flex;justify-content:space-between;align-items:center;margin-top:22px;gap:10px}
  button.btn{font:inherit;font-weight:600;border:none;border-radius:var(--radius);padding:13px 20px;cursor:pointer}
  .btn.primary{background:var(--navy);color:#fff}
  .btn.primary:disabled{background:var(--rule);color:var(--ink-soft);cursor:default}
  .btn.ghost{background:transparent;color:var(--navy);padding-left:6px}
  .btn:focus-visible{outline:3px solid var(--steel);outline-offset:2px}
  .hidden{display:none}

  /* results */
  .dominant{margin:18px 0 26px}
  .dominant .label{color:var(--ink-soft);font-size:14px}
  .dominant h2{font-size:44px;line-height:1.05;margin:2px 0 0}
  .bars{display:grid;gap:12px;margin:0 0 26px}
  .bar{display:grid;grid-template-columns:96px 1fr 36px;align-items:center;gap:10px;font-size:15px}
  .bar .track{height:14px;background:#EEEFF2;border-radius:7px;overflow:hidden}
  .bar .fill{height:100%;border-radius:7px;transition:width .5s ease}
  .bar .score{text-align:right;color:var(--ink-soft);font-variant-numeric:tabular-nums}
  .bar.top .name{font-weight:600}
  .note{font-size:13px;color:var(--ink-soft);margin:-14px 0 24px}
  .desc{background:#fff;border-left:5px solid var(--c);border-radius:0 var(--radius) var(--radius) 0;padding:16px 18px;margin-bottom:26px}
  .desc h3{font-size:20px;margin-bottom:8px}
  h3.tips{font-size:20px;margin-bottom:10px}
  details{background:#fff;border:1.5px solid var(--rule);border-radius:var(--radius);margin-bottom:10px}
  summary{cursor:pointer;padding:13px 16px;font-weight:600;display:flex;align-items:center;gap:10px;list-style:none}
  summary::-webkit-details-marker{display:none}
  summary .dot{width:12px;height:12px;border-radius:50%;flex:none}
  summary::after{content:"+";margin-left:auto;color:var(--ink-soft);font-size:20px;line-height:1}
  details[open] summary::after{content:"–"}
  details p{margin:0;padding:0 16px 14px;color:var(--ink)}
  .foot{margin-top:34px;padding-top:14px;border-top:1px solid var(--rule);font-size:12px;color:var(--ink-soft)}
  .printmeta{display:none;color:var(--ink-soft);font-size:14px;margin:6px 0 0}
  @media print{
    @page{margin:18mm}
    body{background:#fff;font-size:13px}
    .wrap{max-width:none;padding:0}
    .band,.nav,.note{display:none}
    .printmeta{display:block}
    .dominant h2{font-size:34px}
    .bars{margin-bottom:18px}
    .bar .fill{transition:none}
    .desc{border-radius:0;break-inside:avoid;-webkit-print-color-adjust:exact;print-color-adjust:exact}
    details{break-inside:avoid;border-color:#bbb}
    summary::after{content:""}
    .foot{margin-top:20px}
    -webkit-print-color-adjust:exact;print-color-adjust:exact
  }
  @media (prefers-reduced-motion:reduce){.bar .fill{transition:none}}
</style>
</head>
<body>
<div class="wrap">
  <div class="band"></div>

  <section id="intro">
    <h1>Work Styles Inventory</h1>
    <p class="lede">Five quick questions. For each one, tap the four responses in order — first the one that matters most to you, last the one that matters least. You'll get your dominant work style and tips for working with the other three.</p>
    <div class="nav"><span></span><button class="btn primary" onclick="start()">Begin</button></div>
    <p class="foot">Source: IHI Tool "Work Styles Inventory Worksheet" (© 2019 Institute for Healthcare Improvement, ihi.org), itself an adaptation of Bolton R, Bolton D. <em>People Styles at Work</em>, 2nd ed. AMACOM; 2009. For educational, not-for-profit use.</p>
  </section>

  <section id="quiz" class="hidden">
    <div class="progress" id="progress"></div>
    <div class="qnum" id="qnum"></div>
    <h2 id="qtext"></h2>
    <p class="hint">Tap in order of importance. Tap again to undo.</p>
    <div class="opts" id="opts"></div>
    <div class="nav">
      <button class="btn ghost" id="back" onclick="back()">Back</button>
      <button class="btn primary" id="next" onclick="next()" disabled>Next</button>
    </div>
    <p class="foot">Source: IHI Tool "Work Styles Inventory Worksheet" (© 2019 Institute for Healthcare Improvement, ihi.org), itself an adaptation of Bolton R, Bolton D. <em>People Styles at Work</em>, 2nd ed. AMACOM; 2009. For educational, not-for-profit use.</p>
  </section>

  <section id="results" class="hidden">
    <h1>Your work style</h1>
    <p class="printmeta" id="printmeta"></p>
    <div class="dominant"><div class="label">Dominant style</div><h2 id="domName"></h2></div>
    <div class="bars" id="bars"></div>
    <p class="note">Lower total = stronger preference. Bars show relative strength.</p>
    <div class="desc" id="desc"></div>
    <h3 class="tips">Try these tips for working with others</h3>
    <div id="tips"></div>
    <div class="nav"><button class="btn ghost" onclick="retake()">Start over</button><button class="btn ghost" onclick="shareResult()">Copy summary</button><button class="btn primary" onclick="savePDF()">Save as PDF</button></div>
    <p class="foot">Source: IHI Tool "Work Styles Inventory Worksheet" (© 2019 Institute for Healthcare Improvement, ihi.org), itself an adaptation of Bolton R, Bolton D. <em>People Styles at Work</em>, 2nd ed. AMACOM; 2009. For educational, not-for-profit use.</p>
  </section>
</div>

<script>
const Q = [
  {stem:"When performing a job, it is most important to:", opts:[
    "do it correctly, regardless of time.",
    "set deadlines and get it done.",
    "work cooperatively as a team.",
    "contribute my talents and excitement."]},
  {stem:"The best part of working on a job is:", opts:[
    "the information you learn.",
    "the results you achieve.",
    "the people you work with.",
    "seeing the job contribute to progress."]},
  {stem:"When I have several ways to get a job done, I:", opts:[
    "review pros and cons of each way.",
    "choose a way I can begin now.",
    "discuss the options with others.",
    "follow my “gut” about the best option."]},
  {stem:"In working on a long-term job, it is most important to:", opts:[
    "thoughtfully complete each step.",
    "complete the work efficiently.",
    "work with others as a team.",
    "keep the work stimulating."]},
  {stem:"I am willing to take a risky action if:", opts:[
    "there are facts to support it.",
    "it gets the job done.",
    "it will not hurt others’ feelings.",
    "it feels right for the situation."]},
];

const STYLES = [
  {key:"analytical", name:"Analytical", color:"var(--analytical)",
   summary:"You are cautious in your actions and decisions. You like to ask many questions about specific details before moving ahead. At times, your desire to be accurate can mean you rely too much on data collection. You like organization and structure and prefer an objective, task-oriented work environment. You tend to dislike involvement with others and to seek security and self-actualization.",
   tips:{
     analytical:"Establish priority of tasks to be done. Commit to firm time frames for your work and stick to them.",
     driver:"Organize your work around major themes; prepare “executive summaries” with headings or bullets that state the conclusions first and supporting data and analysis second.",
     amiable:"Start off on a personal note and gravitate toward project specifics and expectations. Emphasize the greater good of the project.",
     expressive:"Make your presentation lively and try to include the big picture. Involve the Expressive person in developing the “vision” or marketing plan."}},
  {key:"driver", name:"Driver", color:"var(--driver)",
   summary:"You are cool, independent, and competitive. You like control and enjoy taking decisive action. You prefer maximum freedom to manage yourself and others. You have low tolerance for feelings, attitudes, and advice of others. You work quickly and efficiently on your own and become frustrated by inaction in others.",
   tips:{
     analytical:"Take a deep breath, relax, and slow down. You need to demonstrate you have considered all or most options before moving ahead.",
     driver:"Remind each other of your similarities and your need to adopt qualities of the other styles.",
     amiable:"Spend time upfront gaining trust and confidence and be inclusive. Be sure to be specific about deadlines, even when they seem obvious.",
     expressive:"Be patient. Consider working with a flip chart to harness creative spirits. Emphasize timelines and due dates. Build in flexibility to allow creativity."}},
  {key:"amiable", name:"Amiable", color:"var(--amiable)",
   summary:"You have excellent ability to gain support from others. You like close, personal relationships and work slowly and cohesively with others, taking your time to make decisions. You dislike interpersonal conflict and seek security and inclusion. As a teammate, you are supportive and listen thoughtfully to others. You are weak at goal setting and self-direction.",
   tips:{
     analytical:"Cut short the social hour and get right down to the specifics. The more information you can provide to support your position, the better.",
     driver:"Don’t take anything personally. Getting results is what counts with drivers; be decisive and dynamic. Emphasize the bottom line.",
     amiable:"Laugh with each other about how important it is being relational. Then focus on what you really need to accomplish and get to work.",
     expressive:"Show your appreciation for their vision and creativity. Harness this energy to deal with the pesky but important details that only they can address."}},
  {key:"expressive", name:"Expressive", color:"var(--expressive)",
   summary:"You are comfortable with risk-taking and spontaneity. You love to generate new and innovative ideas and do not feel limited by tradition. You tend to dream and get others caught up in the dream, although you may struggle with follow through, especially because you often jump from one activity to another. You work quickly and excitedly with others.",
   tips:{
     analytical:"Translate your vision into specific tasks or goals. Involve the Analytical person in research and developing the details of the plan.",
     driver:"Take time to think about what your vision really is; translate it into action steps with objectives and timelines.",
     amiable:"Tell the Amiable person how important teamwork is for making your vision a reality. Give him or her the job of building the team to make the dream come true.",
     expressive:"Remind each other of your tendency to generate a lot of ideas without thinking through how to implement them."}},
];

let cur = 0;
let answers = Q.map(() => [null,null,null,null]); // rank per option index

function start(){ show("quiz"); render(); }
function show(id){ for(const s of ["intro","quiz","results"]) document.getElementById(s).classList.toggle("hidden", s!==id); window.scrollTo(0,0); }

function render(){
  const q = Q[cur], a = answers[cur];
  document.getElementById("progress").innerHTML = Q.map((_,i)=>`<span class="${i<cur?'done':i===cur?'cur':''}"></span>`).join("");
  document.getElementById("qnum").textContent = `Question ${cur+1} of ${Q.length}`;
  document.getElementById("qtext").textContent = q.stem;
  document.getElementById("opts").innerHTML = q.opts.map((t,i)=>`
    <button class="opt ${a[i]?'ranked':''}" onclick="tap(${i})" aria-pressed="${!!a[i]}">
      <span class="badge">${a[i]??''}</span><span>${t}</span></button>`).join("");
  document.getElementById("back").style.visibility = cur===0 ? "hidden" : "visible";
  const complete = a.every(v=>v);
  const nextBtn = document.getElementById("next");
  nextBtn.disabled = !complete;
  nextBtn.textContent = cur===Q.length-1 ? "See my style" : "Next";
}

function tap(i){
  const a = answers[cur];
  if(a[i]){ // undo: remove this rank and shift higher ranks down
    const r = a[i]; a[i]=null;
    for(let j=0;j<4;j++) if(a[j] && a[j]>r) a[j]--;
  } else {
    a[i] = a.filter(Boolean).length + 1;
  }
  render();
}
function next(){ if(cur<Q.length-1){cur++; render();} else finish(); }
function back(){ if(cur>0){cur--; render();} }

function finish(){
  const totals = [0,0,0,0];
  answers.forEach(a=>a.forEach((r,i)=>totals[i]+=r));
  const min = Math.min(...totals);
  const dom = STYLES.filter((_,i)=>totals[i]===min);
  document.getElementById("domName").textContent = dom.map(s=>s.name).join(" / ");
  document.getElementById("domName").style.color = dom[0].color;
  document.getElementById("bars").innerHTML = STYLES.map((s,i)=>`
    <div class="bar ${totals[i]===min?'top':''}">
      <span class="name">${s.name}</span>
      <div class="track"><div class="fill" style="width:0;background:${s.color}" data-w="${Math.round((20-totals[i])/15*100)}"></div></div>
      <span class="score">${totals[i]}</span></div>`).join("");
  requestAnimationFrame(()=>requestAnimationFrame(()=>document.querySelectorAll(".fill").forEach(f=>f.style.width=f.dataset.w+"%")));
  const d = dom[0];
  document.getElementById("desc").style.setProperty("--c", d.color);
  document.getElementById("desc").innerHTML = `<h3>${d.name}</h3><p style="margin:0">${d.summary}</p>` +
    (dom.length>1 ? `<p style="margin:10px 0 0;color:var(--ink-soft);font-size:14px">You tied across ${dom.length} styles — read the others below too.</p>` : "");
  document.getElementById("tips").innerHTML = STYLES.map(s=>`
    <details><summary><span class="dot" style="background:${s.color}"></span>With ${s.name}s</summary><p>${d.tips[s.key]}</p></details>`).join("");
  _res={totals,dom,min};
  window._summary = `Work Styles Inventory — dominant style: ${dom.map(s=>s.name).join("/")}\n` + STYLES.map((s,i)=>`${s.name}: ${totals[i]}`).join(", ");
  document.getElementById("printmeta").textContent = "Work Styles Inventory results · " + new Date().toLocaleDateString(undefined,{year:"numeric",month:"long",day:"numeric"});
  show("results");
}

let _res=null;
function loadJsPDF(){
  return new Promise((ok,fail)=>{
    if(window.jspdf) return ok();
    const sc=document.createElement("script");
    sc.src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js";
    sc.onload=ok; sc.onerror=fail; document.head.appendChild(sc);
  });
}
async function savePDF(){
  const btn=event.target, old=btn.textContent; btn.textContent="Preparing…"; btn.disabled=true;
  try{ await loadJsPDF(); buildPDF(); }
  catch(e){ // fallback to print
    document.querySelectorAll("#tips details").forEach(d=>d.open=true);
    window.print();
  }
  btn.textContent=old; btn.disabled=false;
}
function hex(v){ return {"var(--analytical)":"#3F6E9C","var(--driver)":"#B4462F","var(--amiable)":"#3D8A5F","var(--expressive)":"#C4862A"}[v]; }
function buildPDF(){
  const {jsPDF}=window.jspdf; const {totals,dom,min}=_res; const d=dom[0];
  const doc=new jsPDF({unit:"pt",format:"letter"});
  const W=612, M=54, CW=W-2*M; let y=M;
  const navy=[46,63,99], soft=[91,100,115], ink=[31,42,58];
  const para=(txt,size,color,font,lh)=>{ doc.setFont("helvetica",font||"normal"); doc.setFontSize(size); doc.setTextColor(...color);
    const lines=doc.splitTextToSize(txt,CW); for(const l of lines){ if(y>740){doc.addPage(); y=M;} doc.text(l,M,y); y+=lh||size*1.35; } };
  doc.setFillColor(122,143,181); doc.rect(M,y,CW,6,"F"); y+=26;
  doc.setFont("times","normal"); doc.setFontSize(24); doc.setTextColor(...ink); doc.text("Work Styles Inventory — Results",M,y); y+=18;
  doc.setFont("helvetica","normal"); doc.setFontSize(10); doc.setTextColor(...soft);
  doc.text(new Date().toLocaleDateString(undefined,{year:"numeric",month:"long",day:"numeric"}),M,y); y+=30;
  doc.setFontSize(10); doc.text("DOMINANT STYLE",M,y); y+=24;
  const c=hex(d.color); doc.setFont("times","normal"); doc.setFontSize(34);
  doc.setTextColor(parseInt(c.slice(1,3),16),parseInt(c.slice(3,5),16),parseInt(c.slice(5,7),16));
  doc.text(dom.map(s=>s.name).join(" / "),M,y); y+=30;
  // bars
  doc.setFont("helvetica","normal"); doc.setFontSize(11);
  STYLES.forEach((s,i)=>{
    const col=hex(s.color); const top=totals[i]===min;
    doc.setFont("helvetica",top?"bold":"normal"); doc.setTextColor(...ink); doc.text(s.name,M,y+9);
    doc.setFillColor(238,239,242); doc.roundedRect(M+90,y,CW-130,12,6,6,"F");
    const w=(20-totals[i])/15*(CW-130);
    doc.setFillColor(parseInt(col.slice(1,3),16),parseInt(col.slice(3,5),16),parseInt(col.slice(5,7),16));
    if(w>0) doc.roundedRect(M+90,y,Math.max(w,12),12,6,6,"F");
    doc.setFont("helvetica","normal"); doc.setTextColor(...soft); doc.text(String(totals[i]),M+CW,y+9,{align:"right"});
    y+=22;
  });
  doc.setFontSize(9); doc.setTextColor(...soft); doc.text("Lower total = stronger preference. Bars show relative strength.",M,y); y+=28;
  // description
  doc.setFillColor(parseInt(c.slice(1,3),16),parseInt(c.slice(3,5),16),parseInt(c.slice(5,7),16)); doc.rect(M,y-12,4,20+doc.splitTextToSize(d.summary,CW-16).length*14,"F");
  doc.setFont("times","normal"); doc.setFontSize(16); doc.setTextColor(...ink); doc.text(d.name,M+14,y+2); y+=20;
  doc.setFont("helvetica","normal"); doc.setFontSize(11); const dl=doc.splitTextToSize(d.summary,CW-16);
  for(const l of dl){ doc.text(l,M+14,y); y+=14; } y+=8;
  if(dom.length>1){ para("You tied across "+dom.length+" styles; consider each of the tied descriptions.",9,soft); }
  y+=10;
  doc.setFont("times","normal"); doc.setFontSize(16); doc.setTextColor(...ink); doc.text("Try these tips for working with others",M,y); y+=20;
  STYLES.forEach(s=>{
    if(y>700){doc.addPage(); y=M;}
    const col=hex(s.color);
    doc.setFillColor(parseInt(col.slice(1,3),16),parseInt(col.slice(3,5),16),parseInt(col.slice(5,7),16)); doc.circle(M+4,y-3,4,"F");
    doc.setFont("helvetica","bold"); doc.setFontSize(11); doc.setTextColor(...ink); doc.text("With "+s.name+"s",M+14,y); y+=15;
    doc.setFont("helvetica","normal"); const tl=doc.splitTextToSize(d.tips[s.key],CW-14);
    for(const l of tl){ if(y>740){doc.addPage(); y=M;} doc.text(l,M+14,y); y+=14; } y+=8;
  });
  // footer on each page
  const foot='Source: IHI Tool "Work Styles Inventory Worksheet" (© 2019 Institute for Healthcare Improvement, ihi.org), an adaptation of Bolton R, Bolton D. People Styles at Work, 2nd ed. AMACOM; 2009. For educational, not-for-profit use.';
  const n=doc.getNumberOfPages();
  for(let i=1;i<=n;i++){ doc.setPage(i); doc.setDrawColor(217,220,227); doc.line(M,742,W-M,742);
    doc.setFont("helvetica","normal"); doc.setFontSize(7.5); doc.setTextColor(...soft);
    const fl=doc.splitTextToSize(foot,CW); let fy=754; for(const l of fl){ doc.text(l,M,fy); fy+=10; } }
  doc.save("work-styles-results-"+dom.map(s=>s.name.toLowerCase()).join("-")+".pdf");
}
function retake(){ cur=0; answers = Q.map(()=>[null,null,null,null]); show("intro"); }
async function shareResult(){
  try{ await navigator.clipboard.writeText(window._summary); const b=event.target; b.textContent="Copied"; setTimeout(()=>b.textContent="Copy summary",1500); }
  catch(e){ alert(window._summary); }
}
</script>
</body>
</html>
