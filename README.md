# Repuestos Obsoletos — Catálogo Web

Sitio estático para publicar en **GitHub Pages**.

## Estructura del proyecto

```
repuestos-obsoletos/
├── index.html          ← Página principal con las familias
├── filtros.html        ← Catálogo de filtros
├── css/
│   └── style.css
├── data/
│   ├── filtros.json    ← Datos de filtros (editar acá)
│   └── ...             ← Agregar un JSON por familia nueva
└── img/
    ├── filtros/        ← Fotos de filtros (nombre = código de pieza)
    └── ...
```

## Publicar en GitHub Pages

1. Crear repo en GitHub (puede ser privado o público)
2. Subir todos los archivos
3. Ir a **Settings → Pages → Branch: main → / (root)**
4. Listo: `https://tuusuario.github.io/repuestos-obsoletos/`

## Cómo actualizar los datos

### Editar filtros
Abrí `data/filtros.json` y agregá o modificá entradas:

```json
[
  {
    "codigo": "FIL-001",
    "cantidad": 12,
    "precio": 4500,
    "aplicabilidad": "Peugeot 405 1.8 1992-1997",
    "foto": "img/filtros/FIL-001.jpg"
  }
]
```

- `codigo`: código de pieza (debe coincidir con el nombre del archivo de foto)
- `cantidad`: unidades disponibles
- `precio`: precio en pesos (solo el número)
- `aplicabilidad`: descripción del vehículo
- `foto`: ruta relativa a la imagen

### Agregar fotos
Copiá las fotos en `img/filtros/` con el nombre `CODIGO.jpg` (o .png, .webp).

### Agregar una nueva familia (ej: Juntas)

1. Crear `data/juntas.json` (igual formato que filtros.json)
2. Crear `img/juntas/` con las fotos
3. Copiar `filtros.html` → `juntas.html` y cambiar las referencias
4. En `index.html`, activar la tarjeta "JUNTAS" (quitar `coming-soon`, agregar `href`)

## WhatsApp
En `filtros.html` (línea 4 del script), cambiar el número:

```js
const WHATSAPP_NUMBER = '5492615550000'; // ← Código país + área + número sin guiones
```
Ejemplo Mendoza: `5492615` + los 6 dígitos del número.
