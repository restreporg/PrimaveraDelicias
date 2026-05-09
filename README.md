PrimaveraDelicias 

Decisiones de diseño BEM — Primavera Delicias

Decisiones por sección

1. Header y navegación

html
<div class="contenedor__header">
  <div class="contenedor__logo">
  <div class="navbar">
    <li class="navbar__link">
  <a class="navbar__reserva">
  <a class="navbar__bars">


El bloque `contenedor` agrupa la cabecera como unidad estructural. El logo y la nav son elementos independientes dentro de él. `navbar__link` es un elemento del bloque `navbar`, lo que permite estilizar todos los links de navegación desde un solo selector sin afectar otros links del sitio. `navbar__reserva` y `navbar__bars` son elementos con roles específicos (botón CTA y menú hamburguesa), lo que hace evidente su propósito solo con leer el nombre de la clase.

2. Sección Inicio (Hero)

html
<section class="inicio">
  <div class="inicio__banner">
    <h2 class="inicio__titulo">
    <p class="inicio__descripcion">
    <a class="inicio__menu">


`inicio` es el bloque. Todo lo que vive dentro de la sección hero lleva el prefijo `inicio__`, dejando claro que esos estilos pertenecen exclusivamente a esa sección y no se heredan ni colisionan con otras. Esto es especialmente útil para el `inicio__titulo`, ya que hay otros títulos en el sitio (`acerca__equipo-titulo`, `menu-card__titulo`) con tamaños y familias tipográficas distintas.

3. Sección Acerca

html
<section class="acerca">
  <div class="acerca__titulo">
  <div class="acerca__contenedor">
    <div class="acerca__contenido">
    <div class="acerca__equipo">
  <div class="acerca__cards">
    <div class="card__cocineros">
      <div class="card-cocineros__icono">


Aquí se tomó la decisión de separar las tres tarjetas (`card__cocineros`, `card__platos`, `card__atencion`) como bloques propios en lugar de usar un modificador, ya que cada una tiene un ícono y título con nombre propio. Esto permite identificar visualmente cada tarjeta en el HTML sin ambigüedad. El `acerca__contenedor` funciona como contenedor de layout para el grid de dos columnas que pone la imagen y el texto en paralelo.

 4. Sección Menú

html
<div class="menu__cards">
  <div class="menu-card menu-card--tacos">
    <img class="menu-card__imagen">
    <h2 class="menu-card__titulo">
    <p class="menu-card__descripcion">
    <div class="menu-card__arrow">


Esta sección aplica BEM de forma más canónica. `menu__card` es el bloque base compartido por las cuatro tarjetas. Los modificadores `menu__card--tacos`, `menu__card--sandwich`, `menu__card--pechuga` y `menu__card--bandeja` permiten personalizar cada tarjeta individualmente (por ejemplo, cambiar la imagen de fondo o el color de acento) sin duplicar los estilos base. Los elementos `menu-card__imagen`, `menu-card__titulo`, `menu-card__descripcion` y `menu-card__arrow` son consistentes en las cuatro tarjetas, lo que facilita el mantenimiento: si se quiere cambiar el estilo del título de todas las cards, basta con modificar un solo selector.

 5. Sección Testimonios

html
<div class="testimonios__grid">
  <div class="testimonio-card">
  <div class="testimonio-card testimonio-card--destacado">
    <div class="testimonio-card__estrellas">
    <p class="testimonio-card__comentario">
    <div class="testimonio-card__autor">
      <img class="testimonio-card__avatar">
      <span class="testimonio-card__nombre">
      <span class="testimonio-card__cargo">


El modificador `testimonio__card--destacado` es un ejemplo claro del propósito de los modificadores en BEM: misma estructura, apariencia diferente. La card del centro comparte exactamente los mismos elementos (`__estrellas`, `__comentario`, `__autor`, etc.) pero visualmente se distingue mediante el modificador, que en el CSS le aplica un fondo de color oliva oscuro y un ligero escalado. Esto evita crear una clase completamente nueva y duplicar estilos.

 6. Sección Pricing

html
<div class="pricing__grid">
  <div class="pricing__card">
  <div class="pricing__card pricing__card--recomendado">
    <span class="pricing__categoria">
    <p class="pricing__plan">
    <div class="pricing__price">
      <span class="pricing__simbolo">
      <span class="pricing__costo">
      <span class="pricing__cantidad">
    <ul class="pricing__caracteristicas">
      <li class="pricing__item">
    <button class="pricing__btn pricing__btn--outline">
    <button class="pricing__btn pricing__btn--solid">


La sección de pricing muestra el uso de modificadores en dos niveles: en la card (`pricing__card--recomendado`) para destacar el plan central, y en el botón (`pricing__btn--outline` y `pricing__btn--solid`) para manejar dos variantes visuales desde una misma clase base. Los nombres de los elementos se adaptaron al español (`pricing__simbolo`, `pricing__costo`, `pricing__cantidad`, `pricing__caracteristicas`) para mantener coherencia con el idioma del proyecto, demostrando que BEM no impone un idioma, sino una estructura.

7. Formulario de contacto

html
<section class="contact">
  <div class="contact__inner">
  <div class="contact__header">
    <p class="contact__label-titulo">
    <h2 class="contact__titulo">
  <form class="contact__form">
    <div class="contact__te">
      <label class="contact__label">
      <input class="contact__input">
      <span class="contact__error">
    <button class="contact__submit">


El bloque `contact` contiene todos los elementos del formulario. La clase `contact__te` agrupa cada campo (label + input + mensaje de error) como una unidad visual, lo que en CSS permite controlar el espaciado entre grupos de forma uniforme. El `contact__error` es un elemento cuya visibilidad se controla con CSS puro usando el selector `:invalid:not(:placeholder-shown)`, sin necesidad de JavaScript para la validación visual básica.

 8. Footer

html
<footer class="footer">
  <div class="footer__top">
    <div class="footer__marcas">
      <p class="footer__logo">
      <p class="footer__tag">
      <a class="footer__marcas-icon">
    <div class="footer__col">
      <p class="footer__col-titulo">
      <ul class="footer__list">
        <li><a class="footer__link">
  <div class="footer__bottom">
    <p class="footer__copy">
    <nav class="footer__legal">
      <a class="footer__legal-link">


El footer se divide en dos bloques visuales claros: `footer__top` (grid de columnas con información) y `footer__bottom` (copyright y enlaces legales). Las columnas de navegación comparten el bloque `footer__col` con sus elementos `footer__col-titulo`, `footer__list` y `footer__link`, lo que permite estilizarlas todas desde un único selector. Solo la columna de marca usa clases propias (`footer__marcas`, `footer__logo`, `footer__tag`) porque su contenido y estructura son distintos a las demás columnas.


