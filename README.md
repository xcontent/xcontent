<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>xcontent.digital – Em breve</title>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Space Grotesk', sans-serif;
    }

    body {
      background: #0e0e0e;
      color: #ffffff;
      overflow-x: hidden;
    }

    .hero {
      position: relative;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 2rem;
      text-align: center;
      background-image: url('https://images.unsplash.com/photo-1621609770332-8be9f6dc63f4?auto=format&fit=crop&w=1950&q=80');
      background-size: cover;
      background-position: center;
    }

    .overlay {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.6);
      z-index: 0;
    }

    .hero h1 {
      font-size: 3rem;
      max-width: 800px;
      margin-bottom: 1rem;
      z-index: 1;
      animation: pulse 2s infinite;
    }

    .hero p {
      font-size: 1.25rem;
      max-width: 600px;
      margin-bottom: 2rem;
      line-height: 1.6;
      z-index: 1;
    }

    .countdown {
      font-size: 1.5rem;
      margin-bottom: 2rem;
      z-index: 1;
      color: #ff0055;
    }

    .form-container {
      background-color: rgba(255, 255, 255, 0.05);
      padding: 2rem;
      border-radius: 1rem;
      backdrop-filter: blur(8px);
      width: 100%;
      max-width: 500px;
      z-index: 1;
    }

    form {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    input {
      padding: 0.75rem 1rem;
      border: none;
      border-radius: 0.5rem;
      font-size: 1rem;
      background-color: #1e1e1e;
      color: #fff;
    }

    button {
      padding: 0.75rem;
      background-color: #ff0055;
      color: white;
      border: none;
      border-radius: 0.5rem;
      font-size: 1.1rem;
      cursor: pointer;
      transition: background 0.3s ease;
    }

    button:hover {
      background-color: #ff3366;
    }

    footer {
      text-align: center;
      padding: 1rem;
      font-size: 0.85rem;
      background-color: #0a0a0a;
      color: #888;
    }

    .socials {
      margin-top: 1rem;
      z-index: 1;
    }

    .socials a {
      color: #fff;
      margin: 0 0.5rem;
      font-size: 1.5rem;
      text-decoration: none;
      transition: color 0.2s;
    }

    .socials a:hover {
      color: #ff0055;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.6; }
    }

    @media screen and (max-width: 600px) {
      .hero h1 {
        font-size: 2rem;
      }
      .hero p {
        font-size: 1rem;
      }
      .countdown {
        font-size: 1.2rem;
      }
    }
  </style>
</head>
<body>
  <section class="hero">
    <div class="overlay"></div>
    <h1>Pausa estratégica. Upgrade em andamento.</h1>
    <p>Estamos preparando a nova experiência de streaming mais ousada do Brasil. Mais conteúdo. Mais impacto. Mais xcontent.digital.<br />
    Cadastre-se e seja avisado em primeira mão.</p>

    <div class="countdown" id="countdown">Faltam: -- dias --:--:--</div>

    <div class="form-container">
      <form action="https://formsubmit.co/wil@xcontent.digital" method="POST">
        <input type="text" name="nome" placeholder="Nome" required />
        <input type="email" name="email" placeholder="E-mail" required />
        <input type="tel" name="telefone" placeholder="Telefone (opcional)" />
        <button type="submit">Quero ser avisado!</button>
        <input type="hidden" name="_captcha" value="false">
        <input type="hidden" name="_next" value="https://www.xcontent.digital/obrigado.html">
      </form>
    </div>

    <div class="socials">
      <a href="https://www.instagram.com/xcontent_/" target="_blank" title="Instagram">📸</a>
      <a href="https://www.linkedin.com/company/xcontent/" target="_blank" title="LinkedIn">💼</a>
      <a href="https://www.youtube.com/@Xcontent" target="_blank" title="YouTube">▶️</a>
    </div>
  </section>

  <footer>
    © 2025 xcontent.digital • Todos os direitos reservados.
  </footer>

  <script>
    const countdown = document.getElementById('countdown');
    const targetDate = new Date('2025-05-10T00:00:00');

    function updateCountdown() {
      const now = new Date();
      const diff = targetDate - now;

      if (diff <= 0) {
        countdown.textContent = 'Estamos no ar!';
        return;
      }

      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const minutes = Math.floor((diff / (1000 * 60)) % 60);
      const seconds = Math.floor((diff / 1000) % 60);

      countdown.textContent = `Faltam: ${days} dias ${hours.toString().padStart(2,'0')}:${minutes.toString().padStart(2,'0')}:${seconds.toString().padStart(2,'0')}`;
    }

    setInterval(updateCountdown, 1000);
  </script>
</body>
</html>
