<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Tuto Presidente</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(135deg, #ff0000, #ffffff, #0000ff);
      background-size: 600% 600%;
      animation: gradientShift 15s ease infinite;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    @keyframes gradientShift {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    .container {
      text-align: center;
      background-color: rgba(255, 255, 255, 0.95);
      padding: 40px;
      border-radius: 20px;
      box-shadow: 0 0 30px rgba(0,0,0,0.3);
      animation: fadeIn 2s ease-out;
      max-width: 750px;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(-20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    h1 {
      font-size: 3em;
      color: #ff0000;
      margin-bottom: 10px;
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.05); }
      100% { transform: scale(1); }
    }

    p {
      font-size: 1.3em;
      color: #0000ff;
      margin-bottom: 20px;
    }

    .cta-button {
      padding: 15px 30px;
      font-size: 1.2em;
      background-color: #ff0000;
      color: white;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: background-color 0.3s ease, transform 0.3s ease;
      margin-bottom: 10px;
    }

    .cta-button:hover {
      background-color: #0000ff;
      transform: scale(1.05);
    }

    .link-button {
      display: inline-block;
      margin-top: 15px;
      padding: 12px 25px;
      font-size: 1.2em;
      background-color: #0000ff;
      color: white;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      text-decoration: none;
      transition: background-color 0.3s ease, transform 0.3s ease;
    }

    .link-button:hover {
      background-color: #ff0000;
      transform: scale(1.05);
    }

    .campaign-image {
      width: 100%;
      max-height: 300px;
      object-fit: cover;
      border-radius: 15px;
      margin-top: 20px;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
      display: none;
      animation: fadeInImage 1s ease-out;
    }

    @keyframes fadeInImage {
      from { opacity: 0; transform: scale(0.95); }
      to { opacity: 1; transform: scale(1); }
    }

    .credibility {
      margin-top: 30px;
      font-size: 1.1em;
      color: #333;
      background-color: #f0f8ff;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    .credibility strong {
      color: #ff0000;
    }

    .contador {
      margin-top: 25px;
      font-size: 1.4em;
      font-weight: bold;
      color: #000;
      background: #ffffff;
      padding: 15px 25px;
      border-radius: 10px;
      display: inline-block;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
      animation: heartbeat 1.5s infinite;
    }

    @keyframes heartbeat {
      0% { transform: scale(1); color: #000; }
      25% { transform: scale(1.05); color: #ff0000; }
      50% { transform: scale(1); color: #0000ff; }
      75% { transform: scale(1.05); color: #ff0000; }
      100% { transform: scale(1); color: #000; }
    }

    .highlight {
      color: #ff0000;
      font-weight: bold;
    }

    footer {
      margin-top: 30px;
      font-size: 1.2em;
      color: #0000ff;
      font-style: italic;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Tuto Presidente</h1>
    <p>¡Un líder con visión, coraje y compromiso!</p>

    <!-- Botón para mostrar imagen -->
    <button class="cta-button" onclick="mostrarImagen()">Súmate al cambio</button>

    <!-- Botón ▶️ original para abrir enlace -->
    <button class="link-button" onclick="abrirVideo()">▶️ Escucha más</button>

    <!-- Botón separado para controlar audio -->
    <button class="cta-button" id="botonAudio" onclick="toggleAudio()">▶️ Reproducir / Pausar audio</button>

    <!-- Imagen de campaña -->
    <img src="jpt.jpeg" alt="Imagen de campaña" class="campaign-image" id="imagenCampaña">

    <!-- Audio automático -->
    <audio id="audioCampaña" src="TUTOAUDIO .mp3" autoplay loop></audio>

    <div class="credibility">
      <p><strong>Tuto</strong> no es solo una promesa, es una trayectoria. Con años de servicio público, compromiso con la democracia y cercanía con la gente, representa la experiencia que Bolivia necesita.</p>
      <p>Junto a <strong>JP - Jóvenes Profesionales por Oruro</strong>, un equipo dinámico y comprometido con el desarrollo regional, trabajan por una visión moderna, ética y progresista para el país.</p>
      <p><strong>JP</strong> representa la energía, la innovación y el talento de una nueva generación que busca transformar Oruro y Bolivia con transparencia y pasión por el servicio público.</p>
      <p><strong>En 2025, vota con esperanza, vota por Tuto.</strong></p>
    </div>

    <!-- Contador -->
    <div class="contador" id="contador">
      ⏳ Calculando tiempo restante...
    </div>

    <footer>
      <p>Apoya el cambio, apoya a <span class="highlight">Jóvenes Profesionales por Oruro</span>.</p>
    </footer>
  </div>

  <script>
    // Mostrar imagen al hacer clic
    function mostrarImagen() {
      const imagen = document.getElementById('imagenCampaña');
      imagen.style.display = 'block';
    }

    // Abrir enlace en nueva pestaña
    function abrirVideo() {
      window.open("/SumateCambio.html", "_blank");
    }

    // Control de audio con botón independiente
    function toggleAudio() {
      const audio = document.getElementById('audioCampaña');
      const boton = document.getElementById('botonAudio');
      if (audio.paused) {
        audio.play();
        boton.innerHTML = '⏸ Pausar audio';
      } else {
        audio.pause();
        boton.innerHTML = '▶️ Reproducir audio';
      }
    }

    // Activar audio automáticamente a volumen máximo
    window.addEventListener('load', () => {
      const audio = document.getElementById('audioCampaña');
      audio.volume = 1.0;
      audio.muted = false;
      audio.play().catch(() => {
        console.log("El navegador requiere interacción para reproducir audio.");
      });
    });

    // Contador hacia el 19 de octubre de 2025
    const fechaObjetivo = new Date("Oct 19, 2025 00:00:00").getTime();
    const intervalo = setInterval(() => {
      const ahora = new Date().getTime();
      const distancia = fechaObjetivo - ahora;

      const dias = Math.floor(distancia / (1000 * 60 * 60 * 24));
      const horas = Math.floor((distancia % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutos = Math.floor((distancia % (1000 * 60 * 60)) / (1000 * 60));
      const segundos = Math.floor((distancia % (1000 * 60)) / 1000);

      document.getElementById("contador").innerHTML = 
        `⏳ Faltan <strong>${dias}</strong> días, <strong>${horas}</strong> h, <strong>${minutos}</strong> min y <strong>${segundos}</strong> seg para el 19 de octubre de 2025`;

      if (distancia < 0) {
        clearInterval(intervalo);
        document.getElementById("contador").innerHTML = "🗳️ ¡Hoy es el gran día! 19 de octubre de 2025 🇧🇴";
      }
    }, 1000);
  </script>
</body>
</html>
