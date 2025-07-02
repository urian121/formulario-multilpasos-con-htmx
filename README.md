# 📝 Formulario Multipasos con HTML y HTMX

Un ejemplo práctico de cómo crear un formulario multipasos moderno y responsivo utilizando solo HTML, CSS y HTMX, sin necesidad de frameworks JavaScript complejos.

## 🚀 Características

- **Formulario de 3 pasos**: Localización, Información de contacto y Revisión
- **Navegación fluida**: Botones de "Atrás" y "Siguiente" con estado dinámico
- **Barra de progreso**: Indicador visual del progreso del formulario
- **Diseño responsivo**: Utiliza Bootstrap 5 para una experiencia móvil perfecta
- **Sin JavaScript complejo**: Solo HTMX para la interactividad
- **Footer fijo**: Navegación siempre visible en la parte inferior

## 🛠️ Tecnologías Utilizadas

- **HTML5**: Estructura semántica del formulario
- **HTMX**: Para la carga dinámica de contenido sin recargar la página
- **Bootstrap 5**: Framework CSS para el diseño responsivo
- **CSS3**: Estilos personalizados para la experiencia de usuario

## 📁 Estructura del Proyecto

```
formulario-multilpasos-con-htmx/
├── index.html          # Página principal con la lógica de navegación
├── step1.html          # Primer paso: Información de localización
├── step2.html          # Segundo paso: Información de contacto
├── step3.html          # Tercer paso: Revisión y envío
├── home.css            # Estilos personalizados
```

## 🎯 Cómo Funciona

### 1. **Carga Inicial**
- Al cargar `index.html`, HTMX automáticamente carga el contenido de `step1.html`
- Se muestra la barra de progreso al 33% (primer paso)

### 2. **Navegación entre Pasos**
- **Botón "Siguiente"**: Incrementa el paso actual y carga el siguiente archivo HTML
- **Botón "Atrás"**: Decrementa el paso actual y carga el paso anterior
- **Estado dinámico**: Los botones se habilitan/deshabilitan según el paso actual

### 3. **Barra de Progreso**
- Se actualiza automáticamente: 33% → 66% → 100%
- Proporciona feedback visual del progreso del usuario

### 4. **Envío del Formulario**
- En el último paso, el botón cambia a "Enviar formulario"
- Actualmente muestra una alerta (puedes personalizar la lógica de envío)

## 🚀 Cómo Usar

1. **Clona o descarga** el proyecto
2. **Abre `index.html`** en tu navegador
3. **¡Listo!** El formulario multipasos funcionará inmediatamente

No necesitas un servidor web, ya que HTMX funciona perfectamente con archivos locales.

## 💡 Conceptos Clave de HTMX

### Atributos HTMX Utilizados

- `hx-get`: Especifica la URL del contenido a cargar
- `hx-trigger`: Define cuándo se ejecuta la petición (ej: "load")
- `hx-swap`: Especifica cómo insertar el contenido recibido

### Ejemplo de Implementación

```html
<div id="formContainer" 
     hx-get="step1.html" 
     hx-trigger="load"
     hx-swap="innerHTML">
</div>
```

## 🎨 Personalización

### Agregar Nuevos Pasos

1. Crea un nuevo archivo HTML (ej: `step4.html`)
2. Actualiza la lógica JavaScript en `index.html`:
   - Incrementa el número máximo de pasos
   - Ajusta los porcentajes de la barra de progreso

### Modificar Estilos

- Edita `home.css` para personalizar colores, espaciados y animaciones
- Los estilos de Bootstrap se pueden sobrescribir según tus necesidades

### Agregar Validación

- Implementa validación HTML5 con atributos como `required`, `pattern`, etc.
- Usa JavaScript para validación más compleja antes de permitir la navegación

## 🌟 Ventajas de este Enfoque

- **Simplicidad**: No necesitas aprender frameworks complejos
- **Rendimiento**: Carga rápida y eficiente
- **Mantenibilidad**: Código limpio y fácil de entender
- **Escalabilidad**: Fácil de extender con nuevas funcionalidades
- **Accesibilidad**: HTML semántico y navegación por teclado

