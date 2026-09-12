# 🛒 proyecto-tienda

Proyecto grupal de la **Universidad Nacional del Oeste (UNO)**. Realizaremos un sitio web sobre una tienda de ropa deportiva.

---

# 🚀 Tienda Deportiva (Guía de Setup Local)

Guía paso a paso para clonar, configurar la base de datos local y ejecutar la aplicación.

---

## 📋 Requisitos Previos

Asegúrate de tener instalado en tu equipo:
- [Node.js](https://nodejs.org/) (versión 16 o superior)
- [MySQL Server 8.0](https://dev.mysql.com/downloads/mysql/)

---

## 🛠️ Instalación y Configuración

### 1. Clonar el repositorio e instalar dependencias

Abre la terminal en la carpeta del proyecto y ejecuta:

`git pull origin main`
`npm install`

### 2. Configurar las Variables de Entorno (.env)

Crea un archivo llamado `.env` en la raíz del proyecto (al mismo nivel que `index.js`) con la siguiente configuración:

DB_HOST=localhost
DB_USER=root
DB_PASSWORD=TU_CONTRASEÑA_DE_MYSQL
DB_NAME=fast_tienda
DB_PORT=3306
PORT=3000

> ⚠️ **Importante:** Reemplaza `TU_CONTRASEÑA_DE_MYSQL` por la clave que definiste al instalar MySQL en tu equipo.

### 3. Crear y Poblar la Base de Datos Local

Abre la terminal de PowerShell en VS Code y ejecuta el siguiente comando para crear la base de datos `fast_tienda`, la tabla `ropas` e insertar los productos iniciales (reemplaza `TU_CONTRASEÑA_DE_MYSQL` por la tuya):

& "C:\Program Files\MySQL\MySQL Server 8.0\bin\mysql.exe" -u root -pTU_CONTRASEÑA_DE_MYSQL -e "CREATE DATABASE IF NOT EXISTS fast_tienda; USE fast_tienda; CREATE TABLE IF NOT EXISTS ropas (id INT AUTO_INCREMENT PRIMARY KEY, nombre VARCHAR(150) NOT NULL, precio DECIMAL(10, 2) NOT NULL, imgUrl VARCHAR(255) NOT NULL, sexo VARCHAR(50) NOT NULL); INSERT INTO ropas (nombre, precio, imgUrl, sexo) VALUES ('Musculosa Under Armour Gris', 18500.00, 'musculosa-under-armour-training-sportstyle-logo-gris-700021359315035-1.jpg', 'masculino'), ('Pantalón Deportivo Hombre', 24999.99, 'pantalon.webp', 'masculino'), ('Short Entrenamiento Hombre', 15500.00, 'short.jpg', 'masculino'), ('Remera Under Armour UA1376921', 19800.00, 'UA1376921-001-1.jpeg', 'masculino'), ('Top Deportivo Mujer Fitness', 16200.00, 'woman-workout-in-gym-with-dumbbells-royalty-free-image-1661857202.jpg', 'femenina'), ('Conjunto Deportivo Mujer', 28900.00, 'mujer-con-abdominales-visibles-haciendo-fitness.jpg', 'femenina');"

---

## 💻 Ejecución del Proyecto

1. Para iniciar el servidor Node.js/Express:

`node index.js`

2. Abre tu navegador e ingresa a cualquiera de las siguientes direcciones:
   - 👉 `http://localhost:3000/hombres.html`
   - 👉 `http://localhost:3000/mujeres.html`