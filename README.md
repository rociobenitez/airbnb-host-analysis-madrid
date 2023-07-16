### 📝 DEFINICIÓN DE OBJETIVOS
---------------------------

**Objetivo:** ***¿Cuál es el objetivo o pregunta(s) central(es) de la visualización? ¿Qué pregunta quieres responder?*** 

Localizar los hosts más rentables para Airbnb, según su facturación promedio.

**Definición de KPI:**
- **Nombre:** Facturación promedio de cada host y clasificación de hosts en rangos de facturación.
- **Objetivo:** Identificar los 10 hosts más rentables en la plataforma.
- **Definición:** El KPI se calcula multiplicando el promedio de precio de los alojamientos de cada host por el promedio del número de veces que se alquilan.
- **Visualización:** Utilizar un gráfico de barras para representar la facturación promedio de cada host.
- **Gráfico secundario de apoyo:** Incluir un mapa para mostrar la ubicación geográfica de los alojamientos de los hosts destacados.
- **Fuente de datos:** Los datos provienen de Airbnb y también se utiliza el campo "n_veces_alquilado".

**Usuarios:** ***¿Quién es el público objetivo?*** El equipo directivo de Airbnb.

**Comportamiento:** ***¿Qué datos se utilizarán y qué conocimientos se pueden extraer de ellos?***

El objetivo principal es calcular el promedio de facturación de los 10 mejores hosts de Airbnb y determinar cuántos alojamientos tienen dentro de la plataforma. Además, como objetivo secundario, se busca conocer el número total de reseñas y la valoración promedio de cada uno de esos hosts. Estos datos son relevantes para evaluar la viabilidad de implementar un sistema de recompensa en la plataforma dirigido a estos hosts destacados, con el propósito de fomentar su continuo uso y participación en Airbnb.

**Frecuencia de uso:** Mensualmente

**Conclusión**
---------------

Pensando en la implementación de una metodología ágil, se establecen los siguientes objetivos:

1. Como analista del mercado de inmuebles turísticos,
2. Quiero generar un informe y gráficos que muestren los 10 mejores hosts de Airbnb, clasificados según su promedio de facturación,
3. Con el fin de establecer sistemas de recompensa para estos usuarios,
4. Con el objetivo de fomentar su continua participación y utilización de la plataforma.


Enfoque Ágil:

Valorar la colaboración activa entre el equipo de análisis y los stakeholders involucrados en el mercado de inmuebles turísticos.
Priorizar la generación de informes y gráficos que destaquen los 10 mejores hosts de Airbnb según su promedio de facturación.
Adaptarse a los cambios y requisitos en tiempo real para garantizar la precisión y relevancia del análisis.
Medir el éxito del proyecto a través de la efectividad de los sistemas de recompensa implementados y el aumento en la utilización de la plataforma por parte de los hosts destacados.
Buscar la mejora continua en la generación de informes y gráficos, incorporando retroalimentación y ajustes según sea necesario.

Con esta metodología ágil, se espera lograr una mayor comprensión del rendimiento de los hosts en Airbnb, identificando a los más destacados en términos de facturación y brindando incentivos adecuados para su retención y compromiso continuo con la plataforma.




### 📊 FACTURACIÓN PROMEDIO
---------------------------

Se crea un **campo calculado** llamado **“facturación promedio"** utilizando la fórmula `AVG([Price]) * AVG([Nº veces alquilado].`

Esta fórmula combina el precio promedio y el número de veces alquilado promedio para calcular un valor estimado de la facturación promedio por alojamiento. Sin embargo, se tienen en cuenta algunas consideraciones:

**1. Interpretación:** La facturación calculada de esta manera es un valor estimado promedio y ***puede no reflejar la realidad exacta para cada alojamiento individual.*** Es importante tener en cuenta que el cálculo asume que el precio promedio y el número de veces alquilado promedio son representativos de todos los alojamientos.

**2. Agregación:** Se tiene en cuenta que se está calculando el promedio del precio y el promedio del número de veces alquilado para todos los alojamientos de la tabla. Esto puede ser útil para obtener una idea general de la facturación promedio, pero al agregar los datos de todos los alojamientos, puede haber ***pérdida de información*** sobre las variaciones individuales.

**3. Contexto y análisis adicional:** La facturación promedio por alojamiento puede ser un dato útil para analizar y comparar diferentes hosts o realizar análisis generales. Sin embargo, también puede ser beneficioso realizar análisis más detallados y segmentados según el tipo de alojamiento, la ubicación geográfica u otros factores relevantes para obtener una visión más completa.




### 📊 GRÁFICO DE BARRAS
---------------------------

Se utiliza el **gráfico de barras** para comparar la facturación promedio entre diferentes hosts.

Al organizar los datos de esta manera, se puede identificar fácilmente qué hosts tienen una facturación más alta en promedio y cuáles tienen una facturación más baja. También se puede explorar cualquier patrón o tendencia en la facturación de los distintos hosts.


Algunas mejoras en la visualización:

**1. Ordenar los hosts por facturación:** Se ordena la columna de facturación en orden descendente para resaltar los hosts con la facturación más alta.

**2. Agregar colores o barras de referencia:** Se utilizan colores para resaltar visualmente los valores más altos y más bajos de facturación, lo que facilitará la identificación de los hosts más destacados.

**3. Incluir otras dimensiones:** Al tener información adicional sobre los hosts, como su review score rating (promedio), el número total de valoraciones o los alojamientos que ofrecen, se incluyen estas dimensiones adicionales en la descripción emergente para obtener una comprensión más completa de los factores que podrían influir en la facturación.

**4. Agregar títulos y etiquetas claras:** Se escogen títulos claros en la visualización y etiquetas para las columnas y filas, de manera que sea fácil de entender y comunicar la información.




### 📊 RANGOS DE FACTURACIÓN
---------------------------

Se crea un **campo calculado** llamado **“Rango facturación”** que utiliza la ***estructura condicional "IF-ELSEIF-ELSE"*** para categorizar los valores de facturación en diferentes rangos.

La condición establece que si la facturación es menor a 5000, se asignará la etiqueta 'Facturan < 5.000'. Luego, se establecen rangos de facturación utilizando las condiciones `">= 5000 AND < 10000"`, `">= 10000 AND < 15000"` y `">= 15000 AND <= 20000"`, asignando las etiquetas correspondientes a cada rango.

Finalmente, si la facturación es mayor a 20000, se asignará la etiqueta 'Facturan > 20.000'. Esto asegura que todos los valores de facturación se clasifiquen en una de las categorías establecidas.

Esta fórmula es útil para analizar la distribución de los alojamientos en función de sus niveles de facturación. Se utiliza esta nueva dimensión calculada en las visualizaciones para agrupar y comparar fácilmente los alojamientos según su rango de facturación.
