<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>海雲館｜值班打卡系統</title>

  <!-- iOS 風格字體 -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap" rel="stylesheet">

  <style>
    body {
      margin: 0;
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, "Helvetica Neue", Arial;
      background: #f2f2f7;
      color: #1c1c1e;
    }

    .app {
      max-width: 420px;
      margin: 0 auto;
      padding: 24px 16px 40px;
    }

    .card {
      background: rgba(255,255,255,0.85);
      backdrop-filter: blur(20px);
      border-radius: 20px;
      padding: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.08);
      margin-bottom: 16px;
    }

    h1 {
      font-size: 22px;
      margin: 0 0 8px;
      text-align: center;
    }

    .subtitle {
      text-align: center;
      font-size: 14px;
      color: #6e6e73;
      margin-bottom: 20px;
    }

    .info {
      font-size: 16px;
      margin: 8px 0;
    }

    .btn {
      width: 100%;
      padding: 16px;
      font-size: 17px;
      border-radius: 14px;
      border: none;
      background: linear-gradient(135deg, #007aff, #5ac8fa);
      color: white;
      font-weight: 600;
      cursor: pointer;
      margin-top: 12px;
    }

    .btn:active {
      transform: scale(0.98);
      opacity: 0.9;
    }

    .log {
      font-size: 14px;
      color: #333;
      margin-top: 10px;
      line-height: 1.6;
    }

    footer {
      text-align: center;
      font-size: 12px;
      color: #8e8e93;
      margin-top: 24px;
    }
  </style>
</head>
<body>
  <div class="app">
    <div class="card">
      <h1>海雲館 值班打卡系統</h1>
      <div class="subtitle">佛光大學 男宿｜對外公開版</div>

      <div class="info">📍 地點：佛光大學 海雲館</div>
      <div class="info">🧭 座標：24.7926, 121.7201</div>
      <div class="info">⏰ 目前時間：<span id="time">讀取中...</span></div>

      <button class="btn" onclick="checkIn()">立即打卡</button>

      <div class="log" id="log"></div>
    </div>

    <footer>
      © 海雲館｜值班紀錄系統（Demo）
    </footer>
  </div>

  <script>
    function updateTime() {
      const now = new Date();
      const timeString = now.toLocaleString('zh-TW', { hour12: false });
      document.getElementById('time').innerText = timeString;
    }

    function checkIn() {
      const now = new Date().toLocaleString('zh-TW', { hour12: false });
      document.getElementById('log').innerHTML = 
        "✅ 打卡成功<br>🕒 時間：" + now + "<br>📍 地點：佛光大學 海雲館（24.7926, 121.7201）";
    }

    updateTime();
    setInterval(updateTime, 1000);
  </script>
</body>
</html>
