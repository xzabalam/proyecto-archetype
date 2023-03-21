Crear un arquetipo de Maven a partir de un proyecto Spring existente es una excelente manera de reutilizar una estructura y configuración base para futuros proyectos. Aquí tienes los pasos para crear un arquetipo a partir de tu proyecto actual:

1. Asegúrate de tener instalado Maven en tu sistema y de que esté disponible en la línea de comandos. Para verificar si Maven está instalado, ejecuta:

```baash
mvn -version 
```

2. Navega hasta la raíz de tu proyecto Spring existente en la línea de comandos.
3. Ejecuta el siguiente comando para crear un arquetipo de tu proyecto actual:

```bash
mvn archetype:create-from-project
```

Esto generará una estructura de directorios llamada target/generated-sources/archetype.

4. Accede al directorio target/generated-sources/archetype:
```bash
cd target/generated-sources/archetype
```

5. Antes de instalar el arquetipo, en el directorio target/generated-sources/archetype/src/main/resources/archetype-resources. Aquí encontrarás los archivos y directorios de tu proyecto que formarán parte del arquetipo.

   * Personaliza la estructura de archivos: 
     * Elimina los archivos y directorios específicos de tu proyecto que no deseas incluir en el arquetipo. Por ejemplo, podrías querer eliminar archivos específicos de configuración o de datos.
     * Añade archivos y directorios adicionales que deseas incluir en el arquetipo. Por ejemplo, podrías agregar archivos de configuración genéricos o plantillas de código.
     * Personaliza el archivo pom.xml del arquetipo:

6. Ve al directorio target/generated-sources/archetype y abre el archivo pom.xml.
   * Revisa las dependencias y plugins en este archivo, y ajusta según sea necesario. Por ejemplo, puedes agregar o eliminar dependencias y plugins, o cambiar sus versiones.
   * Asegúrate de que el groupId, artifactId y la version sean únicos y descriptivos para tu arquetipo.
   * Ahora, tendrás que instalar el arquetipo en tu repositorio local de Maven. Esto instalará el arquetipo en tu repositorio local de Maven, haciéndolo disponible para su uso en futuros proyectos. Ejecuta el siguiente comando:
```bash
mvn install
```

7. Para utilizar el arquetipo recién creado, primero toma nota del groupId, artifactId y la version que se encuentran en el archivo pom.xml dentro del directorio target/generated-sources/archetype.
8Navega hasta el directorio donde deseas crear un nuevo proyecto a partir del arquetipo, y ejecuta el siguiente comando:

```bash
mvn archetype:generate -DarchetypeGroupId=<groupId> -DarchetypeArtifactId=<artifactId> -DarchetypeVersion=<version> -DgroupId=<new_project_groupId> -DartifactId=<new_project_artifactId>

mvn archetype:generate -DarchetypeGroupId=ec.gob.funcionjudicial.expel -DarchetypeArtifactId=expel-proyecto-archetype -DarchetypeVersion=1.0-SNAPSHOT -DgroupId=ec.gob.funcionjudicial.expel -DartifactId=expel-consultacausas
mvn archetype:generate -DarchetypeGroupId=ec.gob.funcionjudicial.expel -DarchetypeArtifactId=expel-proyecto-archetype -DarchetypeVersion=1.0-SNAPSHOT -DgroupId=ec.gob.funcionjudicial.expel -DartifactId=expel-ubicacion
mvn archetype:generate -DarchetypeGroupId=ec.gob.funcionjudicial.expel -DarchetypeArtifactId=expel-proyecto-archetype -DarchetypeVersion=1.0-SNAPSHOT -DgroupId=ec.gob.funcionjudicial.expel -DartifactId=expel-catalogo-juridico
mvn archetype:generate -DarchetypeGroupId=ec.gob.funcionjudicial.expel -DarchetypeArtifactId=expel-proyecto-archetype -DarchetypeVersion=1.0-SNAPSHOT -DgroupId=ec.gob.funcionjudicial.expel -DartifactId=expel-documentos
```

Una vez que hayas ejecutado este comando, Maven creará un nuevo proyecto basado en la estructura y configuración del arquetipo. Ahora puedes comenzar a trabajar en tu nuevo proyecto Spring utilizando la plantilla del arquetipo creado.

Recuerda que puedes personalizar aún más el arquetipo antes de instalarlo, ajustando la estructura de archivos, eliminando archivos innecesarios y realizando cambios en el pom.xml si es necesario.