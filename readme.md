# Web Scraping de tablas de forma simple con Pandas

El web scraping es una técnica de extracción de datos que implica la recopilación de información de sitios web de manera automatizada. Utilizando programas o scripts, los denominados "bots" o "rastreadores" navegan por páginas web, acceden a su contenido y extraen datos específicos según las instrucciones previamente establecidas. Esta técnica es empleada para obtener información estructurada de la web, como precios de productos, reseñas, noticias, y cualquier otro tipo de datos públicos. 

Una de las maneras más simples de extraer tablas de una página web es con pandas. Lo podemos hacer con unas pocas líneas de código.
Por ejemplo, queremos obtener información sobre la cantidad de población de cada Estado de México. Para el año 2020 esa información está disponible en el artículo de Wikipedia ["Organización Territorial de México"](https://es.wikipedia.org/wiki/Organizaci%C3%B3n_territorial_de_M%C3%A9xico).

Con seis líneas de código podemos seleccionar la tabla que necesitamos, exportarla al formato que nos resulte conveniente o transformarla en un dataframe para realizar análisis en python.

    import pandas as pd

    # crear variable de la web
    url = "https://es.wikipedia.org/wiki/Organizaci%C3%B3n_territorial_de_M%C3%A9xico"
    # leer la web
    tables = pd.read_html(url)
    # seleccionar la tabla de la web, en este caso la tercera (comienza a contar desde 0)
    table = tables[2]
    # crear dataframe
    df = pd.DataFrame(table)
    # exportar a formato excel
    df.to_excel("pob_estados_mex.xlsx", index=False)

