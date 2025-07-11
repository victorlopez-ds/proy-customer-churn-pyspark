# Predicción de Churn de Clientes con MLlib de PySpark

Este proyecto implementa modelos de Machine Learning para predecir el churn (abandono) de clientes en una agencia de marketing digital que ofrece servicios de publicidad en páginas web.

## 📋 Descripción del Problema

Una agencia de marketing ha detectado que muchas de sus compañías cliente se dan de baja del servicio. Para mejorar su índice de retención, necesitan identificar qué clientes tienen mayor probabilidad de abandonar el servicio, permitiendo así asignar ejecutivos de cuentas (Account Managers) de forma estratégica.

## 🎯 Objetivo

Desarrollar un modelo predictivo que identifique los clientes con mayor riesgo de churn, utilizando PySpark MLlib para el procesamiento distribuido de datos.

## 📊 Dataset

El dataset `customer_churn.csv` contiene información de 900 clientes con las siguientes características:

### Variables de Entrada
- **Names**: Nombre del último contacto de la compañía
- **Age**: Edad del cliente
- **Total_Purchase**: Número total de anuncios comprados
- **Account_Manager**: Variable binaria (0: sin manager, 1: con manager asignado)
- **Years**: Número de años como cliente
- **Num_Sites**: Número de sitios web usando el servicio
- **Onboard_date**: Fecha de registro del contacto más reciente
- **Location**: Dirección de la sede central
- **Company**: Nombre de la compañía

### Variable Objetivo
- **Churn**: Variable binaria (0: cliente activo, 1: cliente que abandonó)

### Distribución de Clases
- Clientes activos: 750 (83.3%)
- Clientes que abandonaron: 150 (16.7%)

> ⚠️ **Nota**: El dataset está desbalanceado, por lo que se implementa división estratificada.

## 🛠️ Tecnologías Utilizadas

- **PySpark**: Framework de procesamiento distribuido
- **MLlib**: Librería de Machine Learning de Spark
- **Python**: Lenguaje de programación principal

### Librerías Principales
```python
from pyspark.sql import SparkSession
from pyspark.ml.feature import VectorAssembler, StandardScaler
from pyspark.ml.classification import NaiveBayes, LogisticRegression
from pyspark.ml.evaluation import MulticlassClassificationEvaluator
from pyspark.ml import Pipeline
```

