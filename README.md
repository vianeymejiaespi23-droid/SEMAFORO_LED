# SEAMP2 - Semáforo con Raspberry Pi 3 B+

## Descripción

Programa en Python que simula un semáforo con tres LEDs (rojo, amarillo y verde) conectados a los GPIO 18, 23 y 24, usando la librería RPi.GPIO en modo BCM. El ciclo se repite de forma continua: rojo durante 3 segundos, verde durante 3 segundos y amarillo durante 1 segundo. La consola muestra el estado actual. El programa se detiene con Ctrl+C y libera los pines al salir.

## Materiales

- Raspberry Pi 3 B+ con Raspberry Pi OS Lite 64-bit
- 1 LED rojo, 1 LED amarillo y 1 LED verde
- 3 resistencias (por ejemplo 220 Ω)
- Cables de conexión (jumpers) y protoboard

## Conexión

| LED | Pin GPIO | Pin físico | Conexión |
|---|---|---|---|
| Rojo | GPIO 18 | 12 | Resistencia, luego ánodo (pata larga) |
| Amarillo | GPIO 23 | 16 | Resistencia, luego ánodo (pata larga) |
| Verde | GPIO 24 | 18 | Resistencia, luego ánodo (pata larga) |

El cátodo (pata corta) de cada LED va a GND (por ejemplo, pin físico 14).

## Cómo ejecutarlo

1. Conectarse a la Pi por SSH.
2. Activar el entorno virtual:

```
source 8s11/bin/activate
```

3. Ejecutar el programa:

```
python SEAMP2.py
```

## Secuencia

| Orden | LED | Duración | Mensaje en consola |
|---|---|---|---|
| 1 | Rojo | 3 s | ROJO - ALTO |
| 2 | Verde | 3 s | VERDE - SIGUE |
| 3 | Amarillo | 1 s | AMARILLO - PRECAUCION |

Después del amarillo, el ciclo vuelve a empezar en rojo.

## Salida esperada

```
Semáforo iniciado (Modo BCM)
Rojo: GPIO 18 | Amarillo: GPIO 23 | Verde: GPIO 24
Presiona Ctrl+C para salir
ROJO - ALTO
VERDE - SIGUE
AMARILLO - PRECAUCION
```

## Detener el programa

Presionar **Ctrl+C**.

## Archivos

- `SEAMP2.py`: código del programa
