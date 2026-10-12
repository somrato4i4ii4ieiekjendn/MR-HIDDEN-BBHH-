<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MR-HIDDEN | CYBER 17</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #020611;
  color: white;
  font-family: Arial, sans-serif;
  overflow-x: hidden;
}

.scene {
  min-height: 100vh;
  position: relative;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 30px 15px;
  background:
    radial-gradient(ellipse at center, #073b70 0%, #031326 45%, #01030a 100%);
}

.grid {
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(#00aaff18 1px, transparent 1px),
    linear-gradient(90deg, #00aaff18 1px, transparent 1px);
  background-size: 35px 35px;
  transform: perspective(400px) rotateX(55deg) scale(1.8);
  transform-origin: bottom;
  animation: gridmove 8s linear infinite;
}

@keyframes gridmove {
  from { background-position: 0 0; }
  to { background-position: 0 70px; }
}

.orb {
  position: absolute;
  width: 240px;
  height: 240px;
  border-radius: 50%;
  background: #008cff30;
  filter: blur(65px);
  animation: pulse 3s ease-in-out infinite alternate;
}

@keyframes pulse {
  to { transform: scale(1.5); opacity: .4; }
}

header {
  z-index: 2;
  text-align: center;
  animation: appear 1.5s ease both;
}

.crown {
  font-size: 42px;
  color: #ffd45c;
  text-shadow: 0 0 25px #ffb300;
}

h1 {
  font-size: clamp(34px, 8vw, 75px);
  letter-spacing: 3px;
  font-weight: 900;
  text-shadow: 0 0 20px #00aaff;
}

h1 span {
  color: #ffc64a;
}

.subtitle {
  color: #65dfff;
  letter-spacing: 4px;
  margin-top: 10px;
  font-size: clamp(12px, 3vw, 18px);
}

.tagline {
  margin-top: 14px;
  color: #ffc64a;
  letter-spacing: 5px;
  font-size: 12px;
}

.crowd {
  display: flex;
  justify-content: center;
  align-items: end;
  gap: 8px;
  height: 145px;
  width: 100%;
  max-width: 700px;
  margin-top: 30px;
  z-index: 1;
}

.person {
  width: clamp(24px, 5vw, 48px);
  height: 85px;
  background: linear-gradient(#102e4d, #02050b);
  border-radius: 45% 45% 5px 5px;
  position: relative;
  box-shadow: 0 0 12px #008cff40;
  animation: rise 2s ease-in-out infinite alternate;
}

.person:nth-child(even) {
  height: 115px;
  animation-delay: .4s;
}

.person::before {
  content: "";
  position: absolute;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background: #071321;
  border: 2px solid #087fc1;
  top: -24px;
  left: 50%;
  transform: translateX(-50%);
}

@keyframes rise {
  to { transform: translateY(-6px); }
}

.phones {
  position: absolute;
  inset: 0;
  pointer-events: none;
}

.phone {
  position: absolute;
  width: 62px;
  height: 105px;
  border: 3px solid #68839f;
  border-radius: 12px;
  background: #020a18;
  box-shadow: 0 0 20px #008cff80;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  font-size: 11px;
  font-weight: bold;
  color: #00d9ff;
  animation: phonefloat 3s ease-in-out infinite alternate;
}

.phone:nth-child(1) { left: 5%; top: 40%; }
.phone:nth-child(2) { right: 5%; top: 42%; animation-delay: .5s; }
.phone:nth-child(3) { left: 18%; top: 55%; animation-delay: 1s; }
.phone:nth-child(4) { right: 18%; top: 55%; animation-delay: 1.5s; }

@keyframes phonefloat {
  to { transform: translateY(-12px) rotate(3deg); }
}

.laptop {
  width: min(88vw, 560px);
  z-index: 3;
  margin-top: -10px;
  animation: appear 2s ease both;
}

.screen {
  min-height: 220px;
  border: 7px solid #52677e;
  border-bottom-width: 12px;
  border-radius: 15px 15px 5px 5px;
  background:
    radial-gradient(circle at center, #07518c, #031022 75%);
  box-shadow: 0 0 35px #008cff90, inset 0 0 35px #0077ff30;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 15px;
}

.screen .logo {
  font-size: clamp(28px, 7vw, 48px);
  font-weight: 900;
  color: #f9c84b;
  text-shadow: 0 0 18px #ffb900;
}

.screen .shield {
  font-size: 52px;
  filter: drop-shadow(0 0 15px #00c8ff);
}

.screen p {
  color: #72e8ff;
  letter-spacing: 3px;
  margin-top: 8px;
  font-size: 12px;
}

.base {
  height: 16px;
  background: linear-gradient(#b5c8dc, #35475b 55%, #111a29);
  clip-path: polygon(8% 0, 92% 0, 100% 100%, 0 100%);
  border-radius: 0 0 12px 12px;
}

.info {
  z-index: 3;
  text-align: center;
  margin-top: 25px;
  line-height: 2;
  color: #9dc8e9;
  font-size: 12px;
  letter-spacing: 2px;
}

.info strong {
  color: #ffc64a;
}

.button {
  z-index: 3;
  margin-top: 22px;
  padding: 13px 25px;
  border: 1px solid #00cfff;
  background: #00365b80;
  color: white;
  border-radius: 5px;
  letter-spacing: 3px;
  cursor: pointer;
  box-shadow: 0 0 20px #008cff40;
}

.button:hover {
  background: #007bb8;
}

footer {
  z-index: 3;
  color: #587e9e;
  font-size: 10px;
  letter-spacing: 3px;
  margin-top: 28px;
  text-align: center;
}

.scanline {
  position: absolute;
  inset: 0;
  pointer-events: none;
  background: linear-gradient(
    transparent 50%,
    #00b7ff08 50%
  );
  background-size: 100% 4px;
}

@keyframes appear {
  from { opacity: 0; transform: translateY(25px); }
  to { opacity: 1; transform: translateY(0); }
}

@media (max-width: 500px) {
  .phone {
    width: 43px;
    height: 78px;
    font-size: 8px;
  }

  .crowd { height: 105px; }
  .person:nth-child(even) { height: 85px; }
  .person { height: 65px; }
  .screen { min-height: 190px; }
}
</style>
</head>

<body>
<div class="scene">
  <div class="grid"></div>
  <div class="orb"></div>
  <div class="scanline"></div>

  <header>
    <div class="crown">♛</div>
    <h1>MR-<span>HIDDEN</span></h1>
    <div class="subtitle">CYBER 17</div>
    <div class="tagline">LEARN • DEFEND • SECURE</div>
  </header>

  <div class="phones">
    <div class="phone">♛<br>CYBER<br>17</div>
    <div class="phone">♛<br>CYBER<br>17</div>
    <div class="phone">♛<br>CYBER<br>17</div>
    <div class="phone">♛<br>CYBER<br>17</div>
  </div>

  <div class="crowd" id="crowd"></div>

  <div class="laptop">
    <div class="screen">
      <div class="shield">🛡️</div>
      <div class="logo">CYBER 17</div>
      <p>MR-HIDDEN</p>
      <p>BANGLADESH • DIGITAL SECURITY</p>
    </div>
    <div class="base"></div>
  </div>

  <div class="info">
    <strong>MR-HIDDEN | CYBER 17</strong><br>
    CYBERSECURITY • DEVELOPMENT • AWARENESS
  </div>

  <button class="button" onclick="replay()">REPLAY ANIMATION ↻</button>

  <footer>
    THINK SMART • STAY SECURE<br>
    © <span id="year"></span> MR-HIDDEN
  </footer>
</div>

<script>
const crowd = document.getElementById("crowd");

for (let i = 0; i < 17; i++) {
  const person = document.createElement("div");
  person.className = "person";
  person.style.animationDelay = (i * 0.12) + "s";
  crowd.appendChild(person);
}

document.getElementById("year").textContent =
  new Date().getFullYear();

function replay() {
  document.querySelectorAll(
    "header, .laptop, .person, .phone"
  ).forEach((element) => {
    element.style.animation = "none";
    void element.offsetWidth;
    element.style.animation = "";
  });
}
</script>
</body>
</html>
