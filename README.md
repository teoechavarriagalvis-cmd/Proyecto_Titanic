# Guía rápida de Markdown

## Títulos
```
# Título principal
## Subtítulo
### Sub-subtítulo
```

## Texto
```
**negrita**
*cursiva*
```

## Listas
```
- Elemento 1
- Elemento 2
```

## Listas numeradas
```
1. Primer paso
2. Segundo paso
```

## Bloques de código
Para comandos o código, usa 3 comillas invertidas:
\`\`\`
pip install pandas
\`\`\`

## Tabla simple
```
| Columna 1 | Columna 2 |
|-----------|-----------|
| Dato 1    | Dato 2    |
```

Ejemplo aplicado — tabla de resultados:
```
| Categoría   | Total ventas |
|-------------|--------------|
| Electrónica | $3,361,610   |
| Ropa        | $2,687,020   |
```

## Enlaces
```
[Texto del enlace](https://ejemplo.com)
```

# Análisis del Dataset Titanic

## Descripción del proyecto

Este proyecto consiste en realizar una exploración y limpieza básica del dataset del Titanic utilizando Python y la biblioteca Pandas.

El objetivo inicial es conocer la estructura de los datos, identificar valores vacíos y realizar un primer análisis sobre la cantidad de pasajeros que sobrevivieron y no sobrevivieron.

Durante el proyecto se utilizan diferentes funciones de Pandas para explorar, limpiar y analizar la información.

## Funciones investigadas

### `info()`

La función `info()` permite obtener información general sobre un DataFrame. Muestra la cantidad de filas, las columnas disponibles, los valores no nulos y el tipo de dato de cada columna.

Es útil para conocer rápidamente la estructura del dataset y detectar posibles problemas con los datos.

### `isnull().sum()`

`isnull()` permite identificar cuáles valores se encuentran vacíos o son nulos.

Al combinarlo con `sum()`, podemos obtener la cantidad total de valores vacíos que existen en cada columna.

En este dataset encontramos:

* `Age`: 177 valores vacíos.
* `Cabin`: 687 valores vacíos.
* `Embarked`: 2 valores vacíos.

Las demás columnas no presentan valores vacíos.

### `shape`

La propiedad `shape` permite conocer las dimensiones de un DataFrame.

Devuelve dos valores:

* Número de filas.
* Número de columnas.

En este dataset, `shape` devuelve:

```text
(891, 12)
```

Esto significa que el dataset contiene **891 filas y 12 columnas**.

### `head()`

La función `head()` permite visualizar las primeras filas de un DataFrame.

Por defecto muestra las primeras cinco filas, aunque también se puede indicar una cantidad diferente, por ejemplo `head(10)` para mostrar las primeras diez.

Esta función es útil para observar cómo están organizados los datos antes de comenzar el análisis.

### `fillna()`

La función `fillna()` permite reemplazar valores vacíos o nulos por otro valor.

En este proyecto se puede utilizar para completar los valores faltantes de la columna `Age`, por ejemplo, utilizando el promedio de edad.

### `drop()`

La función `drop()` permite eliminar filas o columnas de un DataFrame.

En el caso de `Cabin`, existen 687 valores vacíos de un total de 891 registros. Debido a que representa una gran cantidad de datos faltantes, se puede considerar eliminar esta columna en lugar de intentar completar todos sus valores.

### `value_counts()`

La función `value_counts()` cuenta cuántas veces aparece cada valor diferente dentro de una columna.

En este proyecto se utiliza sobre la columna `Survived` para conocer cuántos pasajeros sobrevivieron y cuántos no.

## Hallazgos de la exploración

Después de realizar la exploración inicial del dataset se encontraron los siguientes resultados:

* El dataset contiene **891 pasajeros**.
* El dataset contiene **12 columnas**.
* La columna `Age` tiene **177 valores vacíos**.
* La columna `Cabin` tiene **687 valores vacíos**, siendo la columna con mayor cantidad de información faltante.
* La columna `Embarked` tiene **2 valores vacíos**.
* **549 pasajeros no sobrevivieron**.
* **342 pasajeros sobrevivieron**.

Al comparar los valores de la columna `Survived`, se observa que hubo más pasajeros que no sobrevivieron que pasajeros que sobrevivieron.

## Limpieza de datos

Como siguiente etapa del proyecto se realizará una limpieza básica del dataset.

La columna `Age` contiene valores vacíos, por lo que se puede utilizar `fillna()` para reemplazarlos utilizando una estrategia como el promedio de edad.

La columna `Cabin` contiene una cantidad considerable de valores vacíos, por lo que se puede utilizar `drop()` para eliminarla si se considera que no es conveniente conservar una columna con tantos datos faltantes.

Finalmente, se guardará una nueva versión del dataset después de realizar la limpieza.

## Tecnologías utilizadas

* Python
* Pandas
* Git
* GitHub