# Proyecto: Análisis y Predicción de Enfermedad Renal Crónica (ERC)

Este repositorio contiene el análisis de datos completo para un proyecto de predicción de ERC, enfocado en un riguroso preprocesamiento de datos y la interpretabilidad del modelo.

## El Notebook

El archivo principal es `ERC.ipynb`. Este notebook detalla el proceso completo:

1.  **Fase 0 (Estrategia):** Definición del objetivo (predecir ERC) y la métrica (Recall).
2.  **Fase 1 (Carga):** Carga robusta de los datos "sucios" (`kidney_disease.csv`).
3.  **Fase 2 (Limpieza Profunda):**
    * Limpieza semántica (traducción y estandarización).
    * Corrección de tipos de datos.
    * Análisis de outliers fisiopatológicos (corrección de `potasio=47` y `sodio=4.5`).
    * Imputación avanzada (MICE) para rescatar a los 400 pacientes.
4.  **Fase 3 (Ingeniería de Características):**
    * Manejo de multicolinealidad (eliminación de `vol_celular_paq`).
    * Transformación logarítmica para corregir sesgo (`creatinina_serica`).
    * Selección de características (eliminación de `potasio` por p-value > 0.05).
5.  **Fase 4 (Modelado y Análisis):**
    * Entrenamiento de un modelo `LogisticRegression` (99% accuracy).
    * Análisis de interpretabilidad (coeficientes).
    * Diagnóstico de fallos (análisis del único Falso Negativo, Paciente 224).

## Resultados Clave

El modelo final (Regresión Logística) alcanzó un **99% de accuracy** y un **AUC de 1.00**, demostrando un rigor bioestadístico. El modelo es 100% interpretable y sus decisiones (basadas en `albumina` y `creatinina`) son clínicamente coherentes.
