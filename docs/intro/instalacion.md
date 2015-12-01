# Requsitos

* Servidor web
* PHP 5.4.0 o superior
* Base de datos SQL (MySQL, PostgreSQL, SQLite, SQL Server)
* Módulos PHP: mcrypt, gd, driver de base de datos deseado

# Instalar con Composer (recomendado)

Descargar la última versión de Virtuágora desde su 
[repositorio oficial](https://github.com/virtuagora/virtuagora/archive/master.zip) y descomprimir en la carpeta 
deseada. Una vez instalado [Composer](https://getcomposer.org/), Ingresar al directorio donde se descomprimió el 
archivo anterior y ejecutar en línea de comandos:
```
composer install
```
O en caso de utilizar el archivo de Composer autocontenido, ejecutar:
```
php composer.phar install
```
Una vez finalizado, la plataforma ya estará instalada.

# Cómo instalar Composer

En GNU/Linux, dirigirse con línea de comandos al directorio `/usr/local/bin` y ejecutar:
```
curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
```
En caso de querer utilizar solamente el archivo autocontenido (sin instalarlo), descargar su 
[última versión](https://getcomposer.org/composer.phar) y ubicarla en la raíz de la carpeta del proyecto.

# Instalar manualmente

Actualmente no se ofrece una descarga de Virtuágora que incluya todas sus dependencias, por lo que se deberá 
utilizar el método anterior por el momento.

# Configurar base de datos

Con un editor de texto, abrir el archivo `app/database.php` y modificar las siguientes líneas:
```
    'driver' => 'mysql',        // Opciones: pmysql, pgsql, sqlite o sqlsrv
    'host' => 'localhost',      // Si la BD no está en el mismo servidor, ingresar su IP
    'database' => 'virtuagora', // El nombre de la base de datos, debe estar creada de antemano y estar vacía
    'username' => 'root',       // Usuario con permisos para utilizar la base de datos anterior
    'password' => '',           // Contraseña del usuario
    'charset' => 'utf8',        // Dejar en utf8
    'collation' => 'utf8_general_ci',
    'prefix' => ''              // Prefijo para las tablas (no es necesario agregar uno)
```
Además, controlar que la última línea indique el huso horario correspondiente.
```
date_default_timezone_set('America/Argentina/Buenos_Aires');
```

# Asistente de instalación

Una vez instalados los archivos y configurada la base de datos, ingresar por el navegador a 
`virtuagora/public/install.php` y seguir el asistente para crear un usuario administrador. Luego de finalizar 
exitosamente este paso, **eliminar este archivo**.
