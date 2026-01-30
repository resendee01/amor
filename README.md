<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<title>Nós Dois 💕</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Poppins&display=swap" rel="stylesheet">

<style>
body {
    margin: 0;
    font-family: 'Poppins', sans-serif;
    background: linear-gradient(to bottom, #ff9a9e, #fad0c4);
    overflow-x: hidden;
    color: #fff;
}

.container {
    padding: 30px 15px;
    text-align: center;
}

h1 {
    font-family: 'Pacifico', cursive;
    font-size: 2.5em;
    animation: fadeIn 2s;
}

.subtitle {
    margin-top: 10px;
    font-size: 1.1em;
    opacity: 0.9;
}

.timer-box {
    background: rgba(255,255,255,0.2);
    backdrop-filter: blur(10px);
    padding: 20px;
    margin: 25px auto;
    border-radius: 15px;
    width: 90%;
    max-width: 400px;
    font-size: 1.3em;
}

.gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(120px,1fr));
    gap: 12px;
    margin-top: 20px;
}

.gallery img {
    width: 100%;
    border-radius: 15px;
    transition: 0.3s;
    box-shadow: 0 5px 15px rgba(0,0,0,0.2);
}

.gallery img:hover {
    transform: scale(1.05);
}

.music {
    margin-top: 30px;
}

audio {
    width: 90%;
    max-width: 350px;
}

/* CORAÇÕES */

.heart {
    position: fixed;
    bottom: -10px;
    font-size: 20px;
    animation: floatUp 6s linear infinite;
}

@keyframes floatUp {
    from {
        transform: translateY(0);
        opacity: 1;
    }
    to {
        transform: translateY(-100vh);
        opacity: 0;
    }
}

/* ANIMAÇÃO */

@keyframes fadeIn {
    from {opacity:0; transform: translateY(20px);}
    to {opacity:1; transform: translateY(0);}
}

.footer {
    margin: 40px 0 20px;
    font-size: 0.9em;
    opacity: 0.8;
}
</style>
</head>

<body>

<div class="container">

<h1>❤️ Nossa História ❤️</h1>

<p class="subtitle">Cada segundo ao seu lado é especial</p>

<div class="timer-box">
<p>Estamos juntos há:</p>
<div id="timer"></div>
</div>

<h2>Nossos Momentos 📸</h2>

<div class="gallery">
    <img src="foto1.jpg">
    <img src="foto2.jpg">
    <img src="foto3.jpg">
</div>

<div class="music">
<h2>Nossa Música 🎶</h2>

<audio autoplay loop controls>
    <source src="musica.mp3" type="audio/mpeg">
</audio>
</div>

<div class="footer">
Feito com amor 💕
</div>

</div>

<script>

// DATA DO NAMORO (MUDE AQUI)
const inicio = new Date("2023-02-14T00:00:00");

function atualizarTempo() {
    const agora = new Date();
    const diferenca = agora - inicio;

    const segundos = Math.floor(diferenca / 1000);
    const minutos = Math.floor(segundos / 60);
    const horas = Math.floor(minutos / 60);
    const dias = Math.floor(horas / 24);

    const h = horas % 24;
    const m = minutos % 60;
    const s = segundos % 60;

    document.getElementById("timer").innerHTML =
        `${dias} dias<br>${h} horas ${m} minutos ${s} segundos`;
}

setInterval(atualizarTempo, 1000);
atualizarTempo();

// CORAÇÕES FLUTUANDO

function criarCoracao() {
    const coracao = document.createElement("div");
    coracao.classList.add("heart");
    coracao.innerHTML = "💗";
    coracao.style.left = Math.random() * 100 + "vw";
    coracao.style.fontSize = (Math.random() * 20 + 10) + "px";
    document.body.appendChild(coracao);

    setTimeout(() => {
        coracao.remove();
    }, 6000);
}

setInterval(criarCoracao, 500);

</script>

</body>
</html>