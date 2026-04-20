# Dataset: Interacciones de Estudiantes con Bot Tutor de Matemática

Este dataset contiene información anonimizada de interacciones entre estudiantes y un bot tutor de matemáticas (basado en modelos de lenguaje). Los datos han sido procesados para permitir estudios estadísticos y de aprendizaje automático preservando la privacidad de los usuarios.

## Resumen del Dataset

- **Número de interacciones:** 6,591
- **Periodo de tiempo:** 31 días (normalizados)
- **Tipo de tutor:** Tutor de álgebra y aritmética para estudiantes de diplomatura.
- **Formato:** CSV

## Estructura de Datos

El archivo `interacciones_estudiantes.csv` contiene las siguientes columnas:

1.  **User ID:** Identificador único del estudiante, anonimizado mediante una función hash (SHA-256). Permite rastrear la actividad de un mismo usuario a lo largo de múltiples sesiones sin revelar su identidad real.
2.  **Session-ID:** Identificador de la sesión de chat, anonimizado mediante hash (SHA-256). Útil para el análisis del flujo de la conversación y la duración de las interacciones.
3.  **Fecha y Hora:** Timestamp de la interacción, anonimizado mediante un desplazamiento temporal (*time shift*). La primera interacción del dataset ha sido fijada al **01/01/2026** y el resto de las fechas ajustadas proporcionalmente para mantener la estacionalidad y el ritmo de estudio real.
4.  **Cantidad de caracteres:** Volumen de texto total de la interacción (suma de la pregunta del estudiante y la respuesta del tutor). Esta métrica sirve como proxy de la complejidad de la consulta y la extensión de la explicación pedagógica.

## Procesamiento de Privacidad

Para garantizar el cumplimiento de los estándares de protección de datos:
- **Hashing:** Todos los identificadores personales persistentes han sido reemplazados por hashes irreversibles.
- **Time Shifting:** Las fechas reales han sido eliminadas y reemplazadas por una escala temporal sintética que preserva los intervalos exactos entre mensajes (segundos, minutos, días), permitiendo análisis de retención y hábitos de estudio sin exponer las fechas reales de cursado.
- **Filtrado:** El dataset cubre un periodo continuo de 31 días de actividad.

## Posibles Usos
- Análisis de patrones de estudio de los estudiantes.
- Modelado de la carga de trabajo y volumen de consultas.
- Estudio de la relación entre la longitud de las respuestas y la resolución de dudas.
- Análisis de la frecuencia de uso del tutor por sesión y por usuario.
