<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Menú de Investigación</title>

    <style>
        body {
            font-family: 'Segoe UI', Arial, sans-serif;
            background-color: #eef6f3;
            margin: 0;
        }

        header {
            background: linear-gradient(90deg, #6a5acd, #2ecc71);
            color: white;
            padding: 25px;
            text-align: center;
        }

        .perfil {
            text-align: center;
            margin: 25px;
        }

        .perfil img {
            width: 160px;
            height: 160px;
            border-radius: 50%;
            border: 5px solid #2ecc71;
            object-fit: cover;
        }

        nav {
            background-color: #6a5acd;
            padding: 12px;
            text-align: center;
        }

        nav button {
            background-color: white;
            color: #6a5acd;
            border: none;
            padding: 10px 18px;
            margin: 5px;
            border-radius: 20px;
            font-size: 15px;
            cursor: pointer;
            transition: 0.3s;
        }

        nav button:hover {
            background-color: #2ecc71;
            color: white;
        }

        .contenido {
            display: none;
            padding: 25px;
        }

        .activo {
            display: block;
        }

        h2 {
            color: #6a5acd;
        }

        iframe {
            width: 100%;
            height: 500px;
            border-radius: 10px;
            border: 2px solid #2ecc71;
        }

        input[type="file"] {
            padding: 10px;
        }
    </style>

    <script>
        function mostrarSeccion(id) {
            const secciones = document.querySelectorAll('.contenido');
            secciones.forEach(s => s.classList.remove('activo'));
            document.getElementById(id).classList.add('activo');
        }

        function cargarPDF(event) {
            const archivo = event.target.files[0];
            const visor = document.getElementById("visorPDF");
            visor.src = URL.createObjectURL(archivo);
        }
    </script>
</head>

<body>

<header>
    <h1>Menú de Investigación</h1>
    <h3>Sasami Pilaquinga </h3>
</header>

<div class="perfil">
    <img src="foto.jpg" alt="Foto de perfil">
    <p>Foto de perfil</p>
</div>

<nav>
    <button onclick="mostrarSeccion('redes')">Redes</button>
    <button onclick="mostrarSeccion('soporte')">Soporte</button>
    <button onclick="mostrarSeccion('analisis')">Análisis</button>
</nav>

<div id="redes" class="contenido activo">
    <h2>Redes</h2>
    <p>Información sobre redes.</p>
</div>

<div id="soporte" class="contenido">
    <h2>Soporte</h2>
    <p>Información sobre soporte.</p>
</div>

<div id="analisis" class="contenido">
    <h2>Análisis</h2>
    <p>Sube tu archivo PDF:</p>
    <input type="file" accept="application/pdf" onchange="cargarPDF(event)">
    <br><br>
    <iframe id="visorPDF"></iframe>
</div>

</body>
</html>
