# Ex.08 Design of Interactive Image Gallery
# Date:
# AIM:
To design a web application for an inteactive image gallery with minimum five images.

# DESIGN STEPS:
## Step 1:
Clone the github repository and create Django admin interface.

## Step 2:
Change settings.py file to allow request from all hosts.

## Step 3:
Use CSS for positioning and styling.

## Step 4:
Write JavaScript program for implementing interactivity.

## Step 5:
Validate the HTML and CSS code.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Image Gallery</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #f06, #4a90e2);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }

        h1 {
            font-size: 3em;
            color: white;
            font-weight: bold;
            margin-bottom: 20px;
            animation: fadeIn 2s ease-in-out;
        }

        @keyframes fadeIn {
            0% {
                opacity: 0;
                transform: translateY(-20px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .gallery {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            grid-gap: 15px;
            width: 80%;
            max-width: 1000px;
        }

        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .gallery-item:hover {
            transform: scale(1.05);
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease, filter 0.3s ease;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
            filter: brightness(0.8);
        }

        .overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .gallery-item:hover .overlay {
            opacity: 1;
        }

        .full-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.9);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 10;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s ease, visibility 0.3s ease;
        }

        .full-screen img {
            max-width: 90%;
            max-height: 90%;
            border-radius: 10px;
        }

        .full-screen.active {
            opacity: 1;
            visibility: visible;
        }

        .close-btn {
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 2em;
            color: white;
            cursor: pointer;
            background: none;
            border: none;
        }
    </style>
</head>
<body>
    <h1>Image Gallery</h1>
    <h2>HEROINS</h2>
    <div class="gallery" id="gallery">
       
    </div>

    <div class="full-screen" id="fullScreen">
        <button class="close-btn" id="closeBtn">&times;</button>
        <img id="fullScreenImg" src="" alt="Full View">
    </div>

    <script>
        const gallery = document.getElementById('gallery');
        const fullScreen = document.getElementById('fullScreen');
        const fullScreenImg = document.getElementById('fullScreenImg');
        const closeBtn = document.getElementById('closeBtn');

    
        const images = [
            
            
            
            'OIP (1).jpeg',
            'OIP (2).jpeg',
            'OIP (3).jpeg',
            'OIP (4).jpeg',
            'th (1).jpeg',
            'OIP.jpeg',
            'th.jpeg',
            'OIP (5).jpeg',
            
        ];

        
        images.forEach((src, index) => {
            const item = document.createElement('div');
            item.classList.add('gallery-item');

            const img = document.createElement('img');
            img.src = src;
            img.alt = `Image ${index + 1}`;

            const overlay = document.createElement('div');
            overlay.classList.add('overlay');
            overlay.innerText = `Image ${index + 1}`;

            item.appendChild(img);
            item.appendChild(overlay);
            gallery.appendChild(item);

            item.addEventListener('click', () => {
                fullScreenImg.src = src;
                fullScreen.classList.add('active');
            });
        });

        
        closeBtn.addEventListener('click', () => {
            fullScreen.classList.remove('active');
        });

        
        fullScreen.addEventListener('click', (e) => {
            if (e.target === fullScreen || e.target === closeBtn) {
                fullScreen.classList.remove('active');
            }
        });
    </script>
</body>
</html>
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/e970f58a-77e2-4ebb-92ee-b1ddc050c7da)

![image](https://github.com/user-attachments/assets/adac8ddc-1b86-4e35-920f-96a23a4712ef)

![image](https://github.com/user-attachments/assets/d3c84dee-f22e-435a-ad32-ddf26c914d1e)

![image](https://github.com/user-attachments/assets/1c52f142-c469-400d-b2b9-691d98b5a922)

![image](https://github.com/user-attachments/assets/6511ae33-3f7c-4628-9041-4c8ef6711808)

![image](https://github.com/user-attachments/assets/ad078668-1d43-4207-b00c-2994e224aa68)

![image](https://github.com/user-attachments/assets/797191a3-389b-4730-b7c0-1b670fa29899)

![image](https://github.com/user-attachments/assets/41e187b0-df15-46e1-a951-b233f70fc783)

![image](https://github.com/user-attachments/assets/b7ff5d81-841f-49d0-af6f-c87f065d325a)




    











# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
