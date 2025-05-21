# free-robux-today
Get 10,000 Robux in Seconds!
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Free Robux Generator (Simulation)</title>
  <style>
    body {
      background: #121212;
      color: white;
      font-family: 'Segoe UI', sans-serif;
      text-align: center;
      padding: 20px;
    }
    .container {
      max-width: 500px;
      margin: auto;
      background: #1e1e1e;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 15px rgba(0,0,0,0.6);
    }
    h1 {
      color: #ffcc00;
    }
    input, select, button {
      width: 90%;
      margin: 10px 0;
      padding: 10px;
      font-size: 16px;
      border: none;
      border-radius: 5px;
    }
    button {
      background-color: #28a745;
      color: white;
      cursor: pointer;
    }
    button:hover {
      background-color: #218838;
    }
    #loading, #verification, #education {
      display: none;
    }
    .disclaimer {
      color: red;
      font-weight: bold;
      margin-top: 20px;
    }
    .footer {
      margin-top: 30px;
      font-size: 12px;
      color: gray;
    }
  </style>
</head>
<body>

  <div class="container" id="form">
    <h1>🎁 Free Robux Generator</h1>
    <p>Enter your Roblox username and platform to receive up to <strong>10,000 Robux</strong> instantly.</p>

    <input type="text" id="username" placeholder="Roblox Username" />
    <select id="platform">
      <option value="">Select Platform</option>
      <option value="Windows">Windows</option>
      <option value="Mac">Mac</option>
      <option value="iOS">iOS</option>
      <option value="Android">Android</option>
    </select>

    <button onclick="startLoading()">Generate Robux</button>
    <p class="disclaimer">⚠️ Simulation only — no Robux is actually generated.</p>
  </div>

  <div class="container" id="loading">
    <h2>Processing...</h2>
    <p>Connecting to Roblox servers...</p>
    <p id="dots">.</p>
    <script>
      let count = 0;
      setInterval(() => {
        if (document.getElementById("loading").style.display !== "none") {
          count = (count + 1) % 4;
          document.getElementById("dots").textContent = ".".repeat(count + 1);
        }
      }, 500);
    </script>
  </div>

  <div class="container" id="verification">
    <h2>🧍 Human Verification Required</h2>
    <p>Please complete the following step to prove you’re not a bot.</p>
    <p id="countdown">You can continue in <span id="timer">10</span> seconds...</p>
  </div>

  <div class="container" id="education">
    <h2>⚠️ Educational Simulation</h2>
    <p>This was a simulation of a Robux scam site. Here's what you should know:</p>
    <ul style="text-align: left;">
      <li>Roblox does not offer free Robux via third-party sites</li>
      <li>Scam sites often use fake verifications, countdowns, and urgent messages</li>
      <li>Never enter your password or download unknown apps</li>
      <li>Stay safe by only using <a href="https://www.roblox.com/" target="_blank" style="color:lightblue;">roblox.com</a></li>
    </ul>
  </div>

  <div class="footer">
    Built for cybersecurity training and awareness. No data is collected.
  </div>

  <script>
    function startLoading() {
      document.getElementById("form").style.display = "none";
      document.getElementById("loading").style.display = "block";
      setTimeout(() => {
        document.getElementById("loading").style.display = "none";
        document.getElementById("verification").style.display = "block";
        startCountdown();
      }, 3000);
    }

    function startCountdown() {
      let timeLeft = 10;
      const timerEl = document.getElementById("timer");
      const interval = setInterval(() => {
        timeLeft--;
        timerEl.textContent = timeLeft;
        if (timeLeft === 0) {
          clearInterval(interval);
          document.getElementById("verification").style.display = "none";
          document.getElementById("education").style.display = "block";
        }
      }, 1000);
    }
  </script>

</body>
</html>
