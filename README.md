# -<!DOCTYPE html>

<html lang="ja">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>おかいけいマスター！</title>

<style>

:root {

  --ink: #553b32;

  --muted: #92796b;

  --orange: #ee8655;

  --bg: #fff4df;

  --card: #fffdf7;

  --line: #f1d9b9;

}

* {

  box-sizing: border-box;

}

body {

  margin: 0;

  background: linear-gradient(145deg, #fff4df, #e9f8e9);

  font-family: sans-serif;

  color: var(--ink);

}

header {

  padding: 25px 15px;

  text-align: center;

}

h1 {

  font-size: clamp(26px, 5vw, 38px);

  color: #a95335;

}

header p {

  color: var(--muted);

  font-weight: bold;

}

.wrap {

  max-width: 900px;

  margin: auto;

  padding: 10px 14px 36px;

}

.tabs {

  display: grid;

  grid-template-columns: repeat(3, 1fr);

  gap: 8px;

  margin-bottom: 18px;

}

button, select {

  font: inherit;

}

button {

  border: 0;

  cursor: pointer;

}

.tab {

  padding: 13px 7px;

  border-radius: 17px;

  background: white;

  color: var(--muted);

  font-weight: 900;

  box-shadow: 0 4px 0 #ead4b6;

}

.tab.active {

  background: var(--orange);

  color: white;

}

.panel {

  background: var(--card);

  border: 2px solid var(--line);

  border-radius: 25px;

  padding: 20px;

  box-shadow: 0 5px 0 #e8d2b5;

  margin-bottom: 18px;

}

.tag {

  background: #fff0c8;

  color: #a85a35;

  padding: 7px 11px;

  border-radius: 30px;

  font-size: 12px;

  font-weight: bold;

}

.products {

  display: grid;

  grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));

  gap: 10px;

}

.product {

  background: #fff3df;

  border: 2px solid var(--line);

  border-radius: 19px;

  padding: 13px;

  text-align: left;

  min-height: 110px;

  color: var(--ink);

  box-shadow: 0 4px 0 #e9d0ad;

}

.product:active {

  transform: translateY(3px);

}

.emoji {

  font-size: 32px;

  display: block;

}

.price {

  color: var(--orange);

  font-weight: 900;

}

.primary {

  background: linear-gradient(#ffad69, #ee8050);

  color: white;

  padding: 13px 18px;

  border-radius: 16px;

  font-weight: 900;

  box-shadow: 0 4px 0 #c96740;

}

.secondary {

  background: #e7f5df;

  color: #4f946d;

  padding: 12px 15px;

  border-radius: 15px;

  font-weight: 900;

}

.money {

  font-size: 32px;

  font-weight: 900;

}

.row {

  display: flex;

  gap: 10px;

  align-items: center;

  flex-wrap: wrap;

}

.row > * {

  flex: 1;

}

.cartline {

  display: flex;

  justify-content: space-between;

  padding: 10px 0;

  border-bottom: 1px solid var(--line);

}

.qty {

  display: flex;

  align-items: center;

  gap: 8px;

}

.mini {

  width: 34px;

  height: 34px;

  border-radius: 10px;

  background: #fff0c8;

  color: #a85a35;

  font-weight: bold;

}

select, input {

  background: #faf9fd;

  border: 1px solid var(--line);

  border-radius: 12px;

  padding: 12px;

  color: var(--ink);

  min-height: 44px;

}

.answer {

  width: 100%;

  font-size: 22px;

  text-align: center;

  padding: 14px;

}

.stats {

  display: flex;

  gap: 10px;

}

.stat {

  flex: 1;

  background: #fff3dc;

  border-radius: 16px;

  padding: 12px;

  text-align: center;

}

.stat strong {

  display: block;

  font-size: 22px;

  color: var(--orange);

}

.good {

  color: #168b6c;

  font-weight: bold;

}

.bad {

  color: #d34e72;

  font-weight: bold;

}

.feedback {

  min-height: 25px;

  margin: 10px 0;

}

.receipt {

  background: #fffdf7;

  border: 1px dashed #d8cda9;

  border-radius: 14px;

  padding: 14px;

}

.hidden {

  display: none !important;

}

.muted {

  color: var(--muted);

  font-size: 13px;

}

footer {

  text-align: center;

  color: var(--muted);

  font-size: 12px;

  padding: 15px;

}

@media (min-width: 650px) {

  .panel {

    padding: 25px;

  }

}

</style>

</head>

<body>

<header>

  <div>🌼 わくわく おみせやさんごっこ 🌼</div>

  <h1>🍳 おかいけいマスター！</h1>

  <p>商品をえらんで、レジでピッ♪</p>

</header>

<main class="wrap">

<div class="tabs">

  <button class="tab active" data-tab="shop">🛍️ お買い物</button>

  <button class="tab" data-tab="cashier">🏪 レジ体験</button>

  <button class="tab" data-tab="quiz">⚡ 計算チャレンジ</button>

</div>

<section id="shop" class="mode">

<div class="panel">

  <h2>🛒 商品をえらぼう！</h2>

  <p class="muted">好きな商品をタップしてね。</p>

  <div class="products" id="products"></div>

</div>

<div class="panel">

  <h2>🧺 お買い物カゴ</h2>

  <button class="secondary" id="clearCart">カゴを空にする</button>

  <div id="cart"></div>

  <p>合計金額</p>

  <div class="money" id="cartTotal">¥0</div>

  <button class="primary" id="toCheckout">お会計へ進む →</button>

</div>

<div class="panel hidden" id="checkout">

  <h2>💰 お支払い</h2>

  <div class="money" id="checkoutTotal"></div>

  <select id="payment">

    <option value="1000">1,000円</option>

    <option value="2000">2,000円</option>

    <option value="3000">3,000円</option>

    <option value="5000">5,000円</option>

    <option value="10000">10,000円</option>

  </select>

  <button class="primary" id="pay">支払う！</button>

  <div class="feedback" id="payFeedback"></div>

  <div id="receipt" class="receipt hidden"></div>

</div>

</section>

<section id="cashier" class="mode hidden">

<div class="panel">

  <h2>🏪 レジ係になろう！</h2>

  <div class="products" id="cashProducts"></div>

  <h3>お会計</h3>

  <div id="cashCart"></div>

  <div class="money" id="cashTotal">¥0</div>

  <button class="secondary" id="cashReset">最初から</button>

  <h3>お客様のお支払い</h3>

  <select id="cashPaid">

    <option value="1000">1,000円</option>

    <option value="2000">2,000円</option>

    <option value="5000">5,000円</option>

    <option value="10000">10,000円</option>

  </select>

  <button class="primary" id="calcChange">お釣りを計算！</button>

  <div class="feedback" id="changeResult"></div>

</div>

<div class="panel">

  <h2>🏷️ 割引・消費税の練習</h2>

  <p>商品価格</p>

  <input id="basePrice" type="number" value="1200">

  <p>割引</p>

  <select id="discount">

    <option value="0">なし</option>

    <option value="10">10%引き</option>

    <option value="20">20%引き</option>

    <option value="30">30%引き</option>

    <option value="50">半額</option>

  </select>

  <p>消費税</p>

  <select id="tax">

    <option value="10">10%</option>

    <option value="8">8%</option>

  </select>

  <button class="primary" id="calcTax">計算する！</button>

  <div id="taxResult" class="feedback"></div>

</div>

</section>

<section id="quiz" class="mode hidden">

<div class="panel">

  <h2>⚡ 計算チャレンジ！</h2>

  <p>難易度を選んでね。</p>

  <select id="level">

    <option value="easy">初級</option>

    <option value="normal">中級</option>

    <option value="hard">上級</option>

  </select>

  <button class="primary" id="startQuiz">スタート！</button>

  <div class="stats">

    <div class="stat">問題<strong id="qNum">0 / 10</strong></div>

    <div class="stat">正解<strong id="score">0</strong></div>

    <div class="stat">連続正解<strong id="streak">0</strong></div>

  </div>

  <div id="quizArea" class="hidden">

    <h3 id="question"></h3>

    <input id="answer" class="answer" type="number" placeholder="答えを入力">

    <button class="primary" id="submitAnswer">答え合わせ</button>

    <button class="secondary" id="nextQuestion" disabled>次の問題 →</button>

    <div id="quizFeedback" class="feedback"></div>

  </div>

  <div id="quizEnd"></div>

</div>

</section>

<footer>🌼 たのしくおみせやさんのおしごとにチャレンジ！ 🌼</footer>

</main>

<script>

const items = [

  {name:"おにぎり",emoji:"🍙",price:150},

  {name:"サンドイッチ",emoji:"🥪",price:320},

  {name:"りんご",emoji:"🍎",price:120},

  {name:"牛乳",emoji:"🥛",price:220},

  {name:"ジュース",emoji:"🧃",price:160},

  {name:"プリン",emoji:"🍮",price:180},

  {name:"パン",emoji:"🥐",price:190},

  {name:"お弁当",emoji:"🍱",price:580},

  {name:"アイス",emoji:"🍦",price:210},

  {name:"チョコ",emoji:"🍫",price:140},

  {name:"カレー",emoji:"🍛",price:450},

  {name:"ケーキ",emoji:"🍰",price:420}

];

let cart = {};

let cashCart = {};

let questions = [];

let qIndex = 0;

let score = 0;

let streak = 0;

let answered = false;

const yen = n => "¥" + Math.round(n).toLocaleString("ja-JP");

function total(c) {

  return Object.entries(c).reduce(

    (sum,[i,n]) => sum + items[i].price*n, 0

  );

}

function productButtons(target, handler) {

  document.getElementById(target).innerHTML =

    items.map((p,i) => `

      <button class="product" data-i="${i}">

        <span class="emoji">${p.emoji}</span>

        <b>${p.name}</b>

        <div class="price">${yen(p.price)}</div>

      </button>

    `).join("");

  document.querySelectorAll("#"+target+" .product")

    .forEach(b => b.onclick = () => handler(items[+b.dataset.i]));

}

function renderCart(c, el) {

  const entries = Object.entries(c);

  document.getElementById(el).innerHTML = entries.length

    ? entries.map(([i,n]) => `

      <div class="cartline">

        <div>${items[i].emoji} ${items[i].name} × ${n}</div>

        <div class="qty">

          <b>${yen(items[i].price*n)}</b>

          <button class="mini" data-i="${i}">−</button>

        </div>

      </div>

    `).join("")

    : '<p class="muted">商品を選んでください。</p>';

  document.querySelectorAll("#"+el+" .mini").forEach(b => {

    b.onclick = () => {

      const i = b.dataset.i;

      c[i]--;

      if (c[i] <= 0) delete c[i];

      update();

    };

  });

}

function update() {

  renderCart(cart,"cart");

  renderCart(cashCart,"cashCart");

  document.getElementById("cartTotal").textContent = yen(total(cart));

  document.getElementById("cashTotal").textContent = yen(total(cashCart));

}

productButtons("products", p => {

  const i = items.indexOf(p);

  cart[i] = (cart[i] || 0) + 1;

  update();

});

productButtons("cashProducts", p => {

  const i = items.indexOf(p);

  cashCart[i] = (cashCart[i] || 0) + 1;

  update();

});

update();

document.getElementById("clearCart").onclick = () => {

  cart = {};

  update();

  document.getElementById("checkout").classList.add("hidden");

};

document.getElementById("toCheckout").onclick = () => {

  if (!total(cart)) {

    alert("先に商品をカゴに入れてください");

    return;

  }

  document.getElementById("checkout").classList.remove("hidden");

  document.getElementById("checkoutTotal").textContent = yen(total(cart));

};

document.getElementById("pay").onclick = () => {

  const t = total(cart);

  const p = +document.getElementById("payment").value;

  const feedback = document.getElementById("payFeedback");

  if (p < t) {

    feedback.innerHTML = '<span class="bad">お金が足りません！</span>';

    return;

  }

  const change = p - t;

  feedback.innerHTML =

    `<span class="good">お会計できました！お釣りは ${yen(change)} です！</span>`;

  const receipt = document.getElementById("receipt");

  receipt.classList.remove("hidden");

  receipt.innerHTML = `

    <b>🧾 レシート</b>

    <p>商品合計：${yen(t)}</p>

    <p>お預かり：${yen(p)}</p>

    <h2>お釣り：${yen(change)}</h2>

  `;

};

document.getElementById("cashReset").onclick = () => {

  cashCart = {};

  update();

  document.getElementById("changeResult").textContent = "";

};

document.getElementById("calcChange").onclick = () => {

  const t = total(cashCart);

  const p = +document.getElementById("cashPaid").value;

  const result = document.getElementById("changeResult");

  if (!t) {

    result.innerHTML = '<span class="bad">商品を選んでね！</span>';

  } else if (p < t) {

    result.innerHTML = '<span class="bad">お金が足りません！</span>';

  } else {

    result.innerHTML =

      `<span class="good">お釣りは ${yen(p-t)} です！</span>`;

  }

};

document.getElementById("calcTax").onclick = () => {

  const base = Math.max(0, +document.getElementById("basePrice").value || 0);

  const discount = +document.getElementById("discount").value;

  const tax = +document.getElementById("tax").value;

  const after = base * (1-discount/100);

  const final = Math.round(after * (1+tax/100));

  document.getElementById("taxResult").innerHTML =

    `割引後：${yen(after)}<br>

     <span class="good">支払金額：${yen(final)}</span>`;

};

document.querySelectorAll(".tab").forEach(button => {

  button.onclick = () => {

    document.querySelectorAll(".tab").forEach(b =>

      b.classList.toggle("active", b === button)

    );

    document.querySelectorAll(".mode").forEach(section =>

      section.classList.toggle("hidden", section.id !== button.dataset.tab)

    );

  };

});

function makeQuestion(level) {

  let a = 0, b = 0, answer = 0, question = "";

  if (level === "easy") {

    a = 100 + Math.floor(Math.random()*9)*50;

    b = 100 + Math.floor(Math.random()*8)*50;

    if (Math.random() < 0.5) {

      answer = a+b;

      question = `${yen(a)}と${yen(b)}の商品。合計はいくら？`;

    } else {

      const paid = Math.ceil((a+b)/500)*500;

      answer = paid-a;

      question = `${yen(a)}の商品を${yen(paid)}で支払うと、お釣りはいくら？`;

    }

  } else if (level === "normal") {

    a = 150 + Math.floor(Math.random()*15)*50;

    b = 120 + Math.floor(Math.random()*12)*40;

    if (Math.random() < 0.5) {

      answer = a*2+b;

      question = `${yen(a)}の商品2個と${yen(b)}の商品1個。合計は？`;

    } else {

      const discount = [10,20,30][Math.floor(Math.random()*3)];

      answer = Math.round(a*(1-discount/100));

      question = `${yen(a)}の商品が${discount}%引き。価格は？`;

    }

  } else {

    a = 500 + Math.floor(Math.random()*20)*100;

    const discount = [10,20,30,50][Math.floor(Math.random()*4)];

    const tax = [8,10][Math.floor(Math.random()*2)];

    answer = Math.round(a*(1-discount/100)*(1+tax/100));

    question = `${yen(a)}の商品が${discount}%引き。さらに消費税${tax}%を加えると？`;

  }

  return {question, answer};

}

function showQuestion() {

  const q = questions[qIndex];

  document.getElementById("qNum").textContent = `${qIndex+1} / 10`;

  document.getElementById("question").textContent = q.question;

  document.getElementById("answer").value = "";

  document.getElementById("answer").disabled = false;

  document.getElementById("submitAnswer").disabled = false;

  document.getElementById("nextQuestion").disabled = true;

  document.getElementById("quizFeedback").textContent = "";

  answered = false;

}

document.getElementById("startQuiz").onclick = () => {

  const level = document.getElementById("level").value;

  questions = Array.from({length:10}, () => makeQuestion(level));

  qIndex = 0;

  score = 0;

  streak = 0;

  document.getElementById("score").textContent = score;

  document.getElementById("streak").textContent = streak;

  document.getElementById("quizEnd").textContent = "";

  document.getElementById("quizArea").classList.remove("hidden");

  showQuestion();

};

document.getElementById("submitAnswer").onclick = () => {

  if (answered) return;

  const value = document.getElementById("answer").value;

  if (value === "") {

    document.getElementById("quizFeedback").textContent = "答えを入力してね！";

    return;

  }

  answered = true;

  const correct = Number(value) === questions[qIndex].answer;

  if (correct) {

    score++;

    streak++;

    document.getElementById("quizFeedback").innerHTML =

      '<span class="good">正解！すばらしい！🎉</span>';

  } else {

    streak = 0;

    document.getElementById("quizFeedback").innerHTML =

      `<span class="bad">おしい！正解は ${yen(questions[qIndex].answer)} です。</span>`;

  }

  document.getElementById("score").textContent = score;

  document.getElementById("streak").textContent = streak;

  document.getElementById("answer").disabled = true;

  document.getElementById("submitAnswer").disabled = true;

  document.getElementById("nextQuestion").disabled = false;

};

document.getElementById("nextQuestion").onclick = () => {

  qIndex++;

  if (qIndex >= 10) {

    document.getElementById("quizArea").classList.add("hidden");

    document.getElementById("quizEnd").innerHTML =

      `🏆 10問中 ${score}問正解！ ${score===10 ? "パーフェクト！" : "よくがんばりました！"}`;

    document.getElementById("qNum").textContent = "10 / 10";

  } else {

    showQuestion();

  }

};

document.getElementById("answer").addEventListener("keydown", event => {

  if (event.key === "Enter" &&

      !document.getElementById("submitAnswer").disabled) {

    document.getElementById("submitAnswer").click();

  }

});

</script>

</body>

</html>