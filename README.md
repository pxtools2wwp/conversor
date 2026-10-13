# Conversor PxTools → WorkWithPlus

Aplicación de escritorio para Windows que convierte estructuras XML de
**GeneXus X Evolution 1 (PxTools)** al formato de **GeneXus 18 + WorkWithPlus**.

Destino soportado: **GeneXus 18 U9 · WorkWithPlus 15 U2.11**

## Descargar

👉 **[Descargar ConversorPxToolsWWP.exe](https://github.com/pxtools2wwp/conversor/releases/latest/download/ConversorPxToolsWWP.exe)**

Ese enlace entrega siempre la versión más reciente, así que sirve para siempre.

Es un solo archivo, `ConversorPxToolsWWP.exe`. No requiere instalar Python ni nada más:
se copia y se ejecuta.

La primera vez Windows puede mostrar *"Windows protegió tu PC"* porque el archivo no
está firmado digitalmente. Clic en **Más información → Ejecutar de todas formas**.

## Actualizaciones

La aplicación consulta sola si hay una versión nueva cada vez que se abre. Si la hay,
pregunta antes de actualizar: nunca lo hace en silencio. También está
**Ayuda → Buscar actualizaciones**.

Si la red de la empresa bloquea GitHub, el chequeo falla sin molestar y siempre se
puede descargar a mano desde el enlace de arriba.

## Cómo se usa

La ventana tiene una pestaña por cada tipo de nodo que se copia desde GeneXus:

| Pestaña | Se copia en GX X Ev1 | Se pega en GX18 |
|---|---|---|
| Forma 1 · Selection completo | nodo `Selection` | `TableMain` |
| Forma 2 · Sección Grilla | nodo `Attributes` | `TableMain` |
| Forma 3 · Sección Filtros | `Filter › Attributes` | `TableMain` |
| Forma 4 · Botones / Acciones | nodo `Action` | `Grid` si *In Grid=True*, si no `TableMain` |

Pasos, siempre los mismos: **1 Pegar entrada → 2 Convertir → 3 Copiar salida**.
Cada pestaña trae las capturas con el nodo exacto de origen y de destino.

Lo que la aplicación no puede resolver sola aparece como advertencia. La más frecuente:
PxTools exporta el objeto llamado por un botón sin el GUID de la KB, así que después de
pegar hay que reasignar ese objeto en GeneXus 18.

## Reportar un error o sugerir una mejora

Desde la pestaña **Reportar** de la aplicación: arma el reporte con el XML que falló y
los datos técnicos, y lo abre en Gmail listo para enviar.

También se puede escribir a **pxtools2wwp@gmail.com**.

## Bitácora

Cada conversión queda guardada en la carpeta `bitacora/`, junto al `.exe`, con la
entrada y la salida completas. Sirve para volver atrás y para adjuntar al reportar
una falla.

## Qué hay en este repositorio

Solo la distribución: este README, el manifiesto `version.json` que usa el actualizador,
y los ejecutables publicados en *Releases*. El código fuente no se publica acá.
