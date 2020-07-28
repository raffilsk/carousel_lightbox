# Carousel 

Recurso para exibição de imagens criado em carousel (carrossel).

Com esta ferramenta as imagens são exibidas de forma amigável com rolagem horizontal suaves e que auto-completa a transição com quando uma imagem estiver em maior proporção na view de exibição.

Para visualizar a aplicação acesse: [Click Aqui!](raffilsk.dev/project?id=3)

### Techs

-Html
-Css
-JavaScrip

#### HTML
```
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Carousel</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="items-wrapper">
    <div class="items">
      <div class="item"><img src="images/guitar_001.jpg"></div>
      <div class="item"><img src="images/guitar_002.jpg"></div>
      <div class="item"><img src="images/guitar_003.jpg"></div>
      <div class="item"><img src="images/guitar_004.jpg"></div>
      <div class="item"><img src="images/guitar_005.jpg"></div>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>
```

#### CSS
```
*{
margin: 0px;
padding: 0px;
box-sizing: border-box;
}
::-webkit-scrollbar {
  height: 2px;  
}
::-webkit-scrollbar-thumb {
  background: #888;
}
body{
  background-color: #111;
  display: grid;
  place-items: center;
  height: 100vh;
}
.items-wrapper {
  width: 50vw;
}
.items {
  display: flex;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  scroll-behavior: smooth;  
}
.item {
  flex: none;
  width: 100%;
  height: 400px;
  scroll-snap-align: start;
  pointer-events: none;
}
img{
  width: 100%;
  height: 100%;
  object-fit: cover;
}

@media only screen and (max-width: 800px){
  .items-wrapper {
    width: 100vw;
  }
}
```

#### JavaScript
```
document.querySelector(".items")
.addEventListener("wheel", event =>{
  if(event.deltaY > 0) {
    event.target.scrollBy(300, 0)
  }else{
    event.target.scrollBy(-300, 0)
  }
})
```


