# TelecomX_LATAM-Parte-2

Proyecto Telecom X Descripción del Proyecto Este proyecto se enfoca en analizar y predecir la cancelación de clientes (Churn) en una empresa de telecomunicaciones ficticia, "Telecom X". El objetivo principal es identificar a los clientes con mayor probabilidad de abandonar el servicio para que la empresa pueda implementar estrategias de retención efectivas. Se sigue un flujo de trabajo típico de ciencia de datos, que incluye la extracción, transformación y carga (ETL) de datos, análisis exploratorio de datos (EDA) y la construcción y evaluación de modelos de Machine Learning.

Origen de los Datos Los datos utilizados en este proyecto provienen del archivo TelecomX_Data.json. Este archivo contiene información detallada sobre los clientes de Telecom X, incluyendo datos demográficos, servicios contratados, información de cuenta y estado de cancelación.

Proceso ETL (Extracción, Transformación y Carga) El notebook comienza con un proceso ETL para preparar los datos para el análisis y modelado:

Extracción: Se carga el archivo TelecomX_Data.json y se normaliza su estructura anidada en un DataFrame de pandas. Transformación: Se corrige la columna account.Charges.Total convirtiéndola a tipo numérico y manejando los valores nulos (rellenándolos con 0). Se renombran las columnas para simplificar su acceso y comprensión. Se eliminan columnas irrelevantes para el modelado (customerID). Se codifican las variables categóricas utilizando One-Hot Encoding. Se estandarizan las variables numéricas (tenure, MonthlyCharges, TotalCharges) utilizando StandardScaler. Carga: El DataFrame transformado y preprocesado se guarda en un archivo CSV llamado telecom_data_processed.csv para su uso posterior. Análisis Exploratorio de Datos (EDA) Se realizó un análisis exploratorio para comprender las características de los datos y su relación con la cancelación de clientes:

Proporción de Churn: Se calculó y visualizó la distribución de clientes que cancelan y los que no, mostrando un desbalance en las clases (aproximadamente 25.7% de Churn). Relación entre Tipo de Contrato y Churn: Se visualizó la tasa de cancelación por tipo de contrato, revelando que los clientes con contratos mes a mes tienen una tasa de cancelación significativamente mayor. Relación entre Tenure/Total Charges y Churn: Se utilizaron boxplots para mostrar la distribución del tiempo de contrato y los cargos totales para clientes que cancelaron y los que no, indicando que los clientes que cancelan tienden a tener un tiempo de contrato y cargos totales menores. Análisis de Correlación: Se generó una matriz de correlación para identificar las variables más relacionadas con la cancelación. Modelado de Machine Learning Se implementaron y evaluaron dos modelos de clasificación para predecir la cancelación:

Separación de Datos: El dataset preprocesado se dividió en conjuntos de entrenamiento (80%) y prueba (20%). Regresión Logística: Se entrenó un modelo de Regresión Logística. Random Forest: Se entrenó un modelo Random Forest Classifier. Evaluación y Comparación de Modelos Ambos modelos se evaluaron utilizando métricas comunes de clasificación (Accuracy, Precision, Recall, F1-Score) y matrices de confusión.

Resultados:

Modelo Accuracy Precision (Sí Cancela) Recall (Sí Cancela) F1-Score (Sí Cancela) Regresión Logística 0.8012 0.63 0.54 0.58 Random Forest 0.7813 0.59 0.47 0.53 Análisis:

La Regresión Logística mostró un desempeño ligeramente superior en general, y notablemente mejor en la precisión y el recall para la clase "Sí Cancela", que es crucial para identificar correctamente a los clientes en riesgo. El Random Forest pudo haber sufrido un ligero overfitting en los datos de entrenamiento.

Conclusión:

Para este problema, la Regresión Logística se seleccionó como el modelo ganador debido a su mejor rendimiento en las métricas clave para la predicción de churn y su simplicidad.

Conclusiones e Interpretación Los hallazgos clave del análisis y modelado incluyen:

Los clientes con contratos mes a mes tienen una alta propensión a cancelar. Los clientes que cancelan tienden a tener un tiempo de contrato más corto y cargos totales más bajos. La Regresión Logística es un modelo efectivo para predecir la cancelación en este dataset. Telecom X puede utilizar estos hallazgos para:

Ofrecer incentivos a los clientes con contratos mes a mes para cambiarse a contratos más largos. Identificar a los clientes con bajo tiempo de contrato y cargos totales como de alto riesgo y dirigirles ofertas de retención. Implementar el modelo de Regresión Logística para obtener una lista de clientes con alta probabilidad de cancelar y priorizar sus esfuerzos de retención. Configuración y Uso Para ejecutar este notebook:

Clona el repositorio de GitHub. Abre el notebook en Google Colab o en tu entorno local con Jupyter Notebook/Lab. Asegúrate de tener el archivo TelecomX_Data.json en el mismo directorio que el notebook o ajusta la ruta del archivo en el código. Ejecuta las celdas secuencialmente.
