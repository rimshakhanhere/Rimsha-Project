<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Solar System</title>
<style>
    body {
        margin: 0;
        height: 100vh;
        background: radial-gradient(ellipse at center, #0b0f2a 0%, #000000 100%);
        display: flex;
        align-items: center;
        justify-content: center;
        overflow: hidden;
        font-family: Arial, sans-serif;
    }

    .solar-system {
        position: relative;
        width: 600px;
        height: 600px;
    }

    /* Sun */
    .sun {
        position: absolute;
        top: 50%;
        left: 50%;
        width: 60px;
        height: 60px;
        background: radial-gradient(circle at 30% 30%, #fff7cc, #ffcc33 60%, #ff8800);
        border-radius: 50%;
        transform: translate(-50%, -50%);
        box-shadow: 0 0 40px 15px rgba(255, 170, 0, 0.6);
        z-index: 10;
    }

    /* Orbit rings */
    .orbit {
        position: absolute;
        top: 50%;
        left: 50%;
        border: 1px solid rgba(255, 255, 255, 0.15);
        border-radius: 50%;
        transform: translate(-50%, -50%);
    }

    /* Planet wrapper spins around the sun */
    .planet-wrapper {
        position: absolute;
        top: 50%;
        left: 50%;
        width: 100%;
        height: 100%;
        transform: translate(-50%, -50%);
        animation: spin linear infinite;
    }

    .planet {
        position: absolute;
        top: 0;
        left: 50%;
        border-radius: 50%;
        transform: translate(-50%, -50%);
    }

    .planet-label {
        position: absolute;
        top: -18px;
        left: 50%;
        transform: translateX(-50%);
        font-size: 10px;
        color: rgba(255,255,255,0.6);
        white-space: nowrap;
    }

    @keyframes spin {
        from { transform: translate(-50%, -50%) rotate(0deg); }
        to   { transform: translate(-50%, -50%) rotate(360deg); }
    }

    /* Individual planet sizes, orbit radii, colors, and speeds */
    .orbit.mercury, .planet-wrapper.mercury { width: 90px; height: 90px; }
    .planet.mercury { width: 6px; height: 6px; background: #b5b5b5; }
    .planet-wrapper.mercury { animation-duration: 3s; }

    .orbit.venus, .planet-wrapper.venus { width: 130px; height: 130px; }
    .planet.venus { width: 10px; height: 10px; background: #e0c16c; }
    .planet-wrapper.venus { animation-duration: 6s; }

    .orbit.earth, .planet-wrapper.earth { width: 180px; height: 180px; }
    .planet.earth { width: 11px; height: 11px; background: #4d90fe; }
    .planet-wrapper.earth { animation-duration: 9s; }

    .orbit.mars, .planet-wrapper.mars { width: 230px; height: 230px; }
    .planet.mars { width: 8px; height: 8px; background: #d1552c; }
    .planet-wrapper.mars { animation-duration: 14s; }

    .orbit.jupiter, .planet-wrapper.jupiter { width: 320px; height: 320px; }
    .planet.jupiter { width: 22px; height: 22px; background: #d9a066; }
    .planet-wrapper.jupiter { animation-duration: 22s; }

    .orbit.saturn, .planet-wrapper.saturn { width: 410px; height: 410px; }
    .planet.saturn { width: 18px; height: 18px; background: #e8d3a0; }
    .planet-wrapper.saturn { animation-duration: 30s; }

    .orbit.uranus, .planet-wrapper.uranus { width: 490px; height: 490px; }
    .planet.uranus { width: 14px; height: 14px; background: #9fe0e0; }
    .planet-wrapper.uranus { animation-duration: 40s; }

    .orbit.neptune, .planet-wrapper.neptune { width: 570px; height: 570px; }
    .planet.neptune { width: 14px; height: 14px; background: #4166f5; }
    .planet-wrapper.neptune { animation-duration: 50s; }

    /* Twinkling stars in background */
    .stars {
        position: fixed;
        top: 0; left: 0;
        width: 100%; height: 100%;
        z-index: -1;
    }
    .star {
        position: absolute;
        width: 2px; height: 2px;
        background: white;
        border-radius: 50%;
        opacity: 0.6;
        animation: twinkle 3s infinite ease-in-out;
    }
    @keyframes twinkle {
        0%, 100% { opacity: 0.2; }
        50% { opacity: 1; }
    }
</style>
</head>
<body>

<div class="stars" id="stars"></div>

<div class="solar-system">
    <div class="sun"></div>

    <div class="orbit mercury"></div>
    <div class="planet-wrapper mercury"><div class="planet mercury"><span class="planet-label">Mercury</span></div></div>

    <div class="orbit venus"></div>
    <div class="planet-wrapper venus"><div class="planet venus"><span class="planet-label">Venus</span></div></div>

    <div class="orbit earth"></div>
    <div class="planet-wrapper earth"><div class="planet earth"><span class="planet-label">Earth</span></div></div>

    <div class="orbit mars"></div>
    <div class="planet-wrapper mars"><div class="planet mars"><span class="planet-label">Mars</span></div></div>

    <div class="orbit jupiter"></div>
    <div class="planet-wrapper jupiter"><div class="planet jupiter"><span class="planet-label">Jupiter</span></div></div>

    <div class="orbit saturn"></div>
    <div class="planet-wrapper saturn"><div class="planet saturn"><span class="planet-label">Saturn</span></div></div>

    <div class="orbit uranus"></div>
    <div class="planet-wrapper uranus"><div class="planet uranus"><span class="planet-label">Uranus</span></div></div>

    <div class="orbit neptune"></div>
    <div class="planet-wrapper neptune"><div class="planet neptune"><span class="planet-label">Neptune</span></div></div>
</div>

<script>
    // Generate random twinkling stars
    const starsContainer = document.getElementById('stars');
    for (let i = 0; i < 150; i++) {
        const star = document.createElement('div');
        star.className = 'star';
        star.style.top = Math.random() * 100 + '%';
        star.style.left = Math.random() * 100 + '%';
        star.style.animationDelay = Math.random() * 3 + 's';
        starsContainer.appendChild(star);
    }
</script>

</body>
</html>
