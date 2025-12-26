# Workshop Abre tu Ciencia

Sitio web para el workshop "Open Science in a Nutshell: Tools, Theory, and Practice for Reproducible Research" organizado en la Escuela de Gobierno, Pontificia Universidad Católica de Chile.

## Estructura del Sitio

### Páginas Principales

- **Inicio** (`index.qmd`): Página principal con animación Vanta.NET de fondo
- **Colaboradores** (`colaboradores.qmd`): Presentación del equipo organizador con imágenes circulares
- **Invitados** (`invitados.qmd`): Presentación de los expertos invitados con imágenes circulares (3 por fila)
- **Programa** (`programa.qmd`): Integración con Google Sheets para mostrar la agenda y mapa de ubicación
- **Lugar** (`map.qmd`): Mapa interactivo con la ubicación del evento
- **Contenido** (`preworkshop.qmd`): Página de entrada al contenido del programa con sidebar de navegación

### Páginas del Programa

Todas las páginas del programa incluyen un sidebar fijo a la izquierda con navegación y scroll automático al elemento activo:

**Pre-Workshop:**
- `preworkshop.qmd`: Sesión pre-workshop

**Día 1 - 22 de Enero:**
- `programa-dia1-bienvenida.qmd`: Bienvenida
- `programa-dia1-conferencia1.qmd`: Conferencia: ¿Por qué importa la Ciencia Abierta?
- `programa-dia1-conferencia2.qmd`: Conferencia: Buenas prácticas de Ciencia Abierta
- `programa-dia1-panel.qmd`: Panel: Dimensiones éticas e institucionales
- `programa-dia1-lab1.qmd`: Laboratorio 1: Pre-registros
- `programa-dia1-lab2.qmd`: Laboratorio 2: R y {targets}
- `programa-dia1-lab3.qmd`: Laboratorio 3: Quarto

**Día 2 - 23 de Enero:**
- `programa-dia2-conferencia1.qmd`: Conferencia: Protocolos y datos abiertos
- `programa-dia2-conferencia2.qmd`: Conferencia: IA y reproducibilidad científica
- `programa-dia2-panel.qmd`: Panel: Flujos reproducibles
- `programa-dia2-lab4.qmd`: Laboratorio 4: Git y GitHub
- `programa-dia2-lab5.qmd`: Laboratorio 5: Cursor e IA para Ciencia Abierta
- `programa-conferencia-internacional.qmd`: Conferencia Internacional

### Archivos de Configuración y Estilos

- `_quarto.yml`: Configuración global del sitio Quarto
- `_sidebar-programa.html`: HTML parcial para el sidebar de navegación (incluido antes del contenido)
- `_sidebar-programa-close.html`: HTML parcial de cierre del sidebar con JavaScript para marcado activo y scroll automático
- `programa-dia.scss`: Estilos SCSS para el formato de ponentes en las páginas del programa
- `custom.scss`: Estilos personalizados globales
- `styles.css`: Estilos CSS adicionales

## Tecnologías

- **Quarto**: Sistema de publicación científica y técnica
- **Markdown (.qmd)**: Archivos fuente en formato Quarto Markdown
- **CSS3/SCSS**: Estilos personalizados con tipografía Lato (tipografía por defecto de Quarto)
- **JavaScript**: 
  - Animación Vanta.NET para la página de inicio
  - Navegación y scroll automático del sidebar
  - Botón de traducción de idioma (Google Translate)
  - Animaciones de transición entre páginas
- **Google Sheets**: Integración para el programa del workshop
- **Google Maps**: Mapa interactivo con la ubicación del evento
- **Google Translate**: Widget de traducción inglés/español integrado en el navbar

## Requisitos

- [Quarto](https://quarto.org/docs/get-started/) instalado en tu sistema

## Desarrollo Local

Para renderizar y previsualizar el sitio localmente:

```bash
# Renderizar el sitio
quarto render

# Previsualizar el sitio (se abrirá en el navegador)
quarto preview
```

El sitio se renderizará en la carpeta `docs/`.

## Despliegue

### GitHub Pages

El sitio está configurado para renderizarse y desplegarse automáticamente en GitHub Pages mediante GitHub Actions.

1. Ve a la configuración del repositorio en GitHub
2. Navega a **Settings** > **Pages**
3. En **Source**, selecciona **GitHub Actions**
4. Cada push a la rama `main` renderizará el sitio con Quarto y lo desplegará automáticamente

### Netlify

Para desplegar en Netlify:

#### Paso 1: Obtener el Token de Netlify

1. Inicia sesión en [Netlify](https://www.netlify.com/)
2. Ve a tu perfil (click en tu avatar en la esquina superior derecha)
3. Selecciona **User settings**
4. En el menú lateral, ve a **Applications**
5. Haz click en **New access token**
6. Dale un nombre descriptivo (ej: "abre-tu-ciencia-deploy")
7. Copia el token generado (solo se muestra una vez, guárdalo de forma segura)

#### Paso 2: Configurar el Token en GitHub

1. En tu repositorio de GitHub, ve a **Settings** > **Secrets and variables** > **Actions**
2. Click en **New repository secret**
3. Nombre: `NETLIFY_AUTH_TOKEN`
4. Valor: Pega el token que copiaste en el paso anterior
5. Click en **Add secret**

#### Paso 3: Obtener el Site ID de Netlify

1. En Netlify, crea un nuevo sitio o selecciona uno existente
2. Ve a **Site settings** > **General**
3. En la sección **Site details**, copia el **Site ID**

#### Paso 4: Agregar el Site ID a GitHub Secrets

1. En GitHub, ve a **Settings** > **Secrets and variables** > **Actions**
2. Click en **New repository secret**
3. Nombre: `NETLIFY_SITE_ID`
4. Valor: Pega el Site ID que copiaste
5. Click en **Add secret**

#### Paso 5: Conectar el Repositorio en Netlify

1. En Netlify, ve a **Add new site** > **Import an existing project**
2. Selecciona **GitHub** como proveedor
3. Autoriza Netlify si es necesario
4. Selecciona el repositorio `abre-tu-ciencia`
5. Configuración de build:
   - **Build command**: `quarto render`
   - **Publish directory**: `docs`
6. Click en **Deploy site**

**Nota:** Netlify necesita tener Quarto instalado. Puedes usar el buildpack de Quarto o configurar un script de build que instale Quarto.

#### Paso 6: Configurar el Dominio (Opcional)

1. En Netlify, ve a **Site settings** > **Domain management**
2. Puedes usar el dominio generado automáticamente o agregar un dominio personalizado

## Características Principales

- **Sidebar de navegación fijo**: Menú lateral fijo en todas las páginas del programa con scroll automático al elemento activo
- **Traducción de idioma**: Botón de cambio de idioma (español/inglés) integrado en el navbar usando Google Translate
- **Formato de ponentes**: Estilos consistentes para mostrar información de ponentes con imágenes circulares y layout horizontal
- **Animaciones**: Transiciones suaves entre páginas y animación de fondo en la página de inicio
- **Diseño responsive**: Adaptación automática para dispositivos móviles y tablets

## Licencia

Ver archivo LICENSE para más detalles.
