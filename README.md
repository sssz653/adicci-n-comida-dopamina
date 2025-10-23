<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Folklore Argentino - Tradición y Modernidad</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Poppins:wght@300;400;600;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #74b9ff 0%, #ffffff 50%, #ffeaa7 100%);
            color: #2d3436;
            overflow-x: hidden;
        }
        
        header {
            position: relative;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: linear-gradient(135deg, rgba(116, 185, 255, 0.9), rgba(255, 234, 167, 0.9)), 
                        url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100"><text x="10" y="50" font-size="40">🎸</text></svg>');
            padding: 2rem;
            border-bottom: 8px solid #0984e3;
        }
        
        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 900px;
        }
        
        .hero-content h1 {
            font-family: 'Bebas Neue', cursive;
            font-size: clamp(4rem, 10vw, 8rem);
            font-weight: 700;
            color: #87CEEB;
            text-shadow: 4px 4px 0px #FFFFFF, 8px 8px 0px #e17055;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease;
            letter-spacing: 3px;
        }
        
        .hero-content p {
            font-size: clamp(1.3rem, 3vw, 2rem);
            color: #2d3436;
            font-weight: 600;
            margin-bottom: 2rem;
            animation: fadeInUp 1.2s ease;
            text-shadow: 2px 2px 4px rgba(255,255,255,0.8);
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .scroll-indicator {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
            font-size: 2rem;
            color: #0984e3;
        }
        
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateX(-50%) translateY(0); }
            40% { transform: translateX(-50%) translateY(-20px); }
            60% { transform: translateX(-50%) translateY(-10px); }
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 4rem 2rem;
        }
        
        .section {
            margin: 6rem 0;
            opacity: 0;
            animation: fadeIn 0.8s ease forwards;
        }
        
        @keyframes fadeIn {
            to { opacity: 1; }
        }
        
        .section-title {
            font-family: 'Bebas Neue', cursive;
            font-size: clamp(2.5rem, 6vw, 5rem);
            font-weight: 700;
            margin-bottom: 3rem;
            color: #0984e3;
            text-align: center;
            text-shadow: 3px 3px 0px #fdcb6e;
            letter-spacing: 2px;
        }
        
        .content-with-image {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
            margin-bottom: 4rem;
            background: white;
            border-radius: 20px;
            padding: 2rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            border: 4px solid #74b9ff;
        }
        
        .content-with-image.reverse {
            grid-template-columns: 1fr 1fr;
        }
        
        .content-with-image.reverse .text-content {
            order: 2;
        }
        
        .content-with-image.reverse .image-content {
            order: 1;
        }
        
        .text-content h3 {
            color: #0984e3;
            font-size: 2.2rem;
            margin-bottom: 1.5rem;
            font-weight: 700;
        }
        
        .text-content p {
            line-height: 1.8;
            color: #2d3436;
            margin-bottom: 1rem;
            font-weight: 400;
            font-size: 1.05rem;
        }
        
        .image-content img {
            width: 100%;
            height: 400px;
            object-fit: cover;
            border-radius: 15px;
            box-shadow: 0 8px 20px rgba(0,0,0,0.2);
            border: 3px solid #fdcb6e;
        }
        
        .ritmos-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }
        
        .ritmo-card {
            background: white;
            border-radius: 20px;
            padding: 2rem;
            border: 4px solid #74b9ff;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .ritmo-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, #74b9ff, #fdcb6e, #74b9ff);
        }
        
        .ritmo-card:hover {
            transform: translateY(-10px) rotate(2deg);
            border-color: #fdcb6e;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
        }
        
        .ritmo-card h4 {
            font-size: 1.8rem;
            color: #0984e3;
            margin-bottom: 1rem;
            font-weight: 700;
        }
        
        .ritmo-card p {
            color: #636e72;
            font-weight: 400;
            line-height: 1.6;
        }
        
        .videos-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 3rem;
            margin-top: 3rem;
        }
        
        .video-card {
            background: white;
            border-radius: 25px;
            overflow: hidden;
            border: 4px solid #74b9ff;
            transition: all 0.4s ease;
            position: relative;
            box-shadow: 0 8px 25px rgba(0,0,0,0.1);
        }
        
        .video-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.2);
            border-color: #fdcb6e;
        }
        
        .video-wrapper {
            position: relative;
            padding-bottom: 56.25%;
            height: 0;
            overflow: hidden;
            background: #000;
        }
        
        .video-wrapper iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
        
        .video-info {
            padding: 1.5rem;
        }
        
        .video-info h4 {
            font-size: 1.4rem;
            margin-bottom: 0.5rem;
            color: #0984e3;
            font-weight: 700;
        }
        
        .youtube-btn {
            display: inline-block;
            background: linear-gradient(135deg, #e74c3c, #c0392b);
            color: white;
            padding: 0.7rem 1.8rem;
            border-radius: 25px;
            text-decoration: none;
            font-size: 0.95rem;
            font-weight: 700;
            margin-top: 1rem;
            transition: all 0.3s ease;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(231, 76, 60, 0.3);
        }
        
        .youtube-btn:hover {
            transform: scale(1.08);
            box-shadow: 0 6px 20px rgba(231, 76, 60, 0.5);
        }
        
        .video-info p {
            color: #636e72;
            font-size: 0.95rem;
            line-height: 1.6;
        }
        
        .artist-tag {
            display: inline-block;
            background: linear-gradient(135deg, #0984e3, #74b9ff);
            color: white;
            padding: 0.4rem 1.2rem;
            border-radius: 20px;
            font-size: 0.85rem;
            margin-top: 0.5rem;
            font-weight: 700;
            box-shadow: 0 3px 8px rgba(9, 132, 227, 0.3);
        }
        
        footer {
            background: linear-gradient(135deg, #0984e3, #74b9ff);
            padding: 3rem 2rem;
            text-align: center;
            border-top: 8px solid #fdcb6e;
            margin-top: 6rem;
        }
        
        footer p {
            color: white;
            font-size: 1.2rem;
            margin: 0.5rem 0;
            font-weight: 600;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }
        
        @media (max-width: 768px) {
            .container {
                padding: 2rem 1rem;
            }
            
            .content-with-image,
            .content-with-image.reverse {
                grid-template-columns: 1fr;
            }
            
            .content-with-image.reverse .text-content,
            .content-with-image.reverse .image-content {
                order: unset;
            }
            
            .videos-grid {
                grid-template-columns: 1fr;
            }
            
            .ritmos-grid {
                grid-template-columns: 1fr;
            }
            
            .image-content img {
                height: 300px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="hero-content">
            <h1>FOLKLORE ARGENTINO</h1>
            <p>🎵 Tradición, Pasión y Cultura 🎵</p>
        </div>
        <div class="scroll-indicator">↓</div>
    </header>
    
    <div class="container">
        <section class="section">
            <h2 class="section-title">Nuestra Historia</h2>
            
            <div class="content-with-image">
                <div class="text-content">
                    <h3>Los Orígenes</h3>
                    <p>
                        El folklore argentino es el latido del alma de nuestra tierra. Nació de la fusión perfecta entre 
                        las culturas indígenas precolombinas, la herencia española colonial y las influencias africanas, 
                        creando una identidad musical única que se arraigó especialmente en las provincias del norte y 
                        el interior del país.
                    </p>
                    <p>
                        Durante el siglo XIX, las guitarras, bombos y charangos comenzaron a contar historias de amor, 
                        trabajo y naturaleza, mientras que cada región desarrollaba sus propios ritmos distintivos. 
                        El folklore se convirtió en el idioma universal de los gauchos, campesinos y trabajadores.
                    </p>
                </div>
                <div class="image-content">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8f/Baile_de_la_zamba.jpg/800px-Baile_de_la_zamba.jpg" alt="Pareja bailando folklore argentino">
                </div>
            </div>
            
            <div class="content-with-image reverse">
                <div class="text-content">
                    <h3>La Era de Oro</h3>
                    <p>
                        El siglo XX trajo consigo el "boom del folklore" en las décadas de 1950 y 1960. Gigantes como 
                        Atahualpa Yupanqui, Mercedes Sosa, Los Chalchaleros y Eduardo Falú transformaron el folklore en 
                        un fenómeno nacional e internacional. El Festival de Cosquín, iniciado en 1961, se convirtió en 
                        la catedral del folklore argentino.
                    </p>
                    <p>
                        Los grupos folklóricos recorrían el país llevando la música de pueblo en pueblo, manteniendo viva 
                        la tradición y conectando generaciones a través de la música.
                    </p>
                </div>
                <div class="image-content">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a3/Guitarrista_de_folklore_argentino.jpg/800px-Guitarrista_de_folklore_argentino.jpg" alt="Grupo folklórico Los de Salta">
                </div>
            </div>
            
            <div class="content-with-image">
                <div class="text-content">
                    <h3>El Folklore Hoy</h3>
                    <p>
                        Una nueva generación de artistas mantiene viva la tradición mientras la reinventa. Abel Pintos 
                        lidera esta renovación, llevando el folklore a estadios completos y fusionándolo con sonidos 
                         contemporáneos. Junto a Soledad, Los Nocheros, Luciano Pereyra y muchos más, el folklore argentino 
                        sigue evolucionando sin perder su esencia.
                    </p>
                    <p>
                        El folklore sigue siendo el corazón cultural de Argentina, celebrado en festivales, peñas y plazas 
                        de todo el país, donde las nuevas generaciones aprenden y celebran sus raíces.
                    </p>
                </div>
                <div class="image-content">
                    <img src="https://media.claude.ai/image/1" alt="Portada revista Folklore - Los de Salta">
                </div>
            </div>
        </section>
        
        <section class="section">
            <h2 class="section-title">Ritmos Tradicionales</h2>
            <div class="ritmos-grid">
                <div class="ritmo-card">
                    <h4>🎵 Zamba</h4>
                    <p>La danza más elegante y romántica del folklore argentino, con movimientos suaves y pañuelos que cuentan historias de amor.</p>
                </div>
                <div class="ritmo-card">
                    <h4>🎵 Chacarera</h4>
                    <p>Ritmo alegre y saltarín de Santiago del Estero, perfecto para el zapateo y la celebración.</p>
                </div>
                <div class="ritmo-card">
                    <h4>🎵 Vidala</h4>
                    <p>Canción melancólica que expresa el sentimiento profundo de los Andes argentinos.</p>
                </div>
                <div class="ritmo-card">
                    <h4>🎵 Gato</h4>
                    <p>Una de las danzas más antiguas, vivaz y picaresca, llena de energía y tradición.</p>
                </div>
                <div class="ritmo-card">
                    <h4>🎵 Carnavalito</h4>
                    <p>Ritmo festivo del noroeste que se baila en rondas durante las celebraciones carnavalescas.</p>
                </div>
                <div class="ritmo-card">
                    <h4>🎵 Cueca</h4>
                    <p>Danza de conquista amorosa donde el pañuelo y el zapateo juegan un papel protagónico.</p>
                </div>
            </div>
        </section>
        
        <section class="section">
            <h2 class="section-title">Folklore en Vivo</h2>
            <div class="videos-grid">
                <div class="video-card">
                    <div class="video-wrapper">
                        <iframe 
                            src="https://www.youtube.com/embed/ossZ44Zr3H4" 
                            frameborder="0" 
                            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                            allowfullscreen>
                        </iframe>
                    </div>
                    <div class="video-info">
                        <h4>Tanto Amor</h4>
                        <p>Una hermosa balada folklórica que muestra el lado más romántico y emotivo de Abel Pintos, con una interpretación que llega directo al corazón.</p>
                        <span class="artist-tag">Abel Pintos</span>
                        <br>
                        <a href="https://www.youtube.com/watch?v=ossZ44Zr3H4&list=PLJ90NpvfCuyr5N5xlM3EOuLyjZc_oxfkj" target="_blank" class="youtube-btn">▶ Ver en YouTube</a>
                    </div>
                </div>
                
                <div class="video-card">
                    <div class="video-wrapper">
                        <iframe 
                            src="https://www.youtube.com/embed/b6bTbteh4yc" 
                            frameborder="0" 
                            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                            allowfullscreen>
                        </iframe>
                    </div>
                    <div class="video-info">
                        <h4>Zamba y Acuarela</h4>
                        <p>Raly Barrionuevo presenta una obra maestra que fusiona la zamba tradicional con pinceladas poéticas, creando una experiencia musical única.</p>
                        <span class="artist-tag">Raly Barrionuevo</span>
                        <br>
                        <a href="https://www.youtube.com/watch?v=b6bTbteh4yc&list=PLJ90NpvfCuyr5N5xlM3EOuLyjZc_oxfkj&index=6" target="_blank" class="youtube-btn">▶ Ver en YouTube</a>
                    </div>
                </div>
                
                <div class="video-card">
                    <div class="video-wrapper">
                        <iframe 
                            src="https://www.youtube.com/embed/0mC0cUEuLKk" 
                            frameborder="0" 
                            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                            allowfullscreen>
                        </iframe>
                    </div>
                    <div class="video-info">
                        <h4>Mia</h4>
                        <p>Jorge Rojas entrega una interpretación apasionada y visceral de este tema que se convirtió en un himno del folklore moderno.</p>
                        <span class="artist-tag">Jorge Rojas</span>
                        <br>
                        <a href="https://www.youtube.com/watch?v=0mC0cUEuLKk&list=PLJ90NpvfCuyr5N5xlM3EOuLyjZc_oxfkj&index=9" target="_blank" class="youtube-btn">▶ Ver en YouTube</a>
                    </div>
                </div>
                
                <div class="video-card">
                    <div class="video-wrapper">
                        <iframe 
                            src="https://www.youtube.com/embed/LXzZr3OkV1k" 
                            frameborder="0" 
                            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                            allowfullscreen>
                        </iframe>
                    </div>
                    <div class="video-info">
                        <h4>La Niña de los Andamios</h4>
                        <p>Una conmovedora historia narrada por Raly Barrionuevo que refleja la realidad social con una profunda sensibilidad poética.</p>
                        <span class="artist-tag">Raly Barrionuevo</span>
                        <br>
                        <a href="https://www.youtube.com/watch?v=LXzZr3OkV1k&list=PLJ90NpvfCuyr5N5xlM3EOuLyjZc_oxfkj&index=12" target="_blank" class="youtube-btn">▶ Ver en YouTube</a>
                    </div>
                </div>
                
                <div class="video-card">
                    <div class="video-wrapper">
                        <iframe 
                            src="https://www.youtube.com/embed/i7Y2o-0s9Jk" 
                            frameborder="0" 
                            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                            allowfullscreen>
                        </iframe>
                    </div>
                    <div class="video-info">
                        <h4>Canción de las Cantinas</h4>
                        <p>Los Nocheros ofrecen un clásico de su repertorio, lleno de energía y el inconfundible sonido del cuarteto salteño.</p>
                        <span class="artist-tag">Los Nocheros</span>
                        <br>
                        <a href="https://www.youtube.com/watch?v=i7Y2o-0s9Jk" target="_blank" class="youtube-btn">▶ Ver en YouTube</a>
                    </div>
                </div>

                <div class="video-card">
                    <div class="video-wrapper">
                        <iframe 
                            src="https://www.youtube.com/embed/m7s_s8l11p8" 
                            frameborder="0" 
                            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                            allowfullscreen>
                        </iframe>
                    </div>
                    <div class="video-info">
                        <h4>Luna Cautiva (Cosquín)</h4>
                        <p>Una poderosa interpretación en el Festival de Cosquín, que captura la magia y el sentimiento del folklore en su máxima expresión.</p>
                        <span class="artist-tag">El Chaqueño Palavecino</span>
                        <br>
                        <a href="https://www.youtube.com/watch?v=m7s_s8l11p8" target="_blank" class="youtube-btn">▶ Ver en YouTube</a>
                    </div>
                </div>

            </div>
        </section>
        
        <footer>
            <p>© 2025 | Folklore Argentino - Tradición y Pasión</p>
            <p>Diseñado con 🧉 y Zamba</p>
        </footer>
    </div>
</body>
</html>
