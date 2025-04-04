# AWS Video Converter Pro

[![Python Version](https://img.shields.io/badge/python-3.x-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**AWS Video Converter Pro** es una aplicación de escritorio desarrollada en Python que permite convertir videos utilizando AWS MediaConvert. La aplicación facilita la configuración de credenciales de AWS, la selección de archivos de video y la generación de trabajos de conversión con múltiples perfiles de calidad.

> **Nota:**  
> Esta aplicación requiere una conexión a Internet para comunicarse con los servicios de AWS (S3 y MediaConvert).

---

## Características

- **Interfaz gráfica moderna:**  
  Utiliza `ttkbootstrap` para ofrecer una experiencia visual agradable y personalizable.

- **Integración con AWS:**  
  Gestiona credenciales de forma segura mediante cifrado, y se conecta tanto a AWS S3 como a AWS MediaConvert.

- **Conversión de Video Multiformato:**  
  Soporta múltiples formatos y perfiles de calidad (1080p, 720p, 480p, 360p) para adaptarse a tus necesidades.

- **Historial y Seguimiento de Trabajos:**  
  Permite rastrear el estado y progreso de cada conversión, con alertas y notificaciones cuando finaliza el trabajo.

- **Configuración Avanzada:**  
  Ofrece opciones personalizadas para bitrate, codec, y otros parámetros de conversión.

---

## Requisitos

- **Python 3.x**  
  [Descargar Python](https://www.python.org/downloads/)

- **AWS CLI** (opcional para algunas validaciones)  
  [Guía de instalación de AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

- **Dependencias Python**  
  Las dependencias del proyecto están listadas en el archivo `requirements.txt`:

  ```txt
  ttkbootstrap
  boto3
  cryptography
  keyring
  ```

---

## Instalación

1. **Clona el repositorio:**

   ```bash
   git clone https://github.com/tu_usuario/aws-video-converter-pro.git
   ```

2. **Ingresa al directorio del proyecto:**

   ```bash
   cd aws-video-converter-pro
   ```

3. **Instala las dependencias necesarias:**

   ```bash
   pip install -r requirements.txt
   ```

---

## Ejecución en Modo Desarrollo

Para iniciar la aplicación en modo desarrollo, ejecuta:

```bash
python main.py
```

Al ejecutar el comando, se abrirá la interfaz gráfica de la aplicación, donde podrás:

- Configurar y gestionar tus credenciales AWS.
- Seleccionar archivos de video para la conversión.
- Enviar trabajos a AWS MediaConvert y seguir su progreso.

---

## Empaquetado a Ejecutable (.exe)

Si deseas distribuir la aplicación sin depender de Python, puedes convertir el script a un ejecutable usando **PyInstaller**. Se incluye un script por lotes que realiza lo siguiente:

- Verifica que AWS CLI esté instalado.
- Comprueba e instala PyInstaller si es necesario.
- Empaqueta `main.py` en un único archivo ejecutable.

### Pasos:

1. **Ejecuta el archivo `build_exe.bat`:**

   ```bat
   build_exe.bat
   ```

   > **Alerta:**  
   > Asegúrate de tener el archivo `icon.ico` en el directorio raíz, ya que se utiliza para el ícono del ejecutable.

2. El ejecutable se generará en la carpeta `dist`.

---

## Desinstalación y Limpieza

Si deseas eliminar la aplicación y limpiar las configuraciones (incluyendo claves de encriptación en keyring y archivos de configuración), utiliza el siguiente script por lotes:

```bat
uninstall_app.bat
```

Este script realizará lo siguiente:

- Borrará la clave de encriptación almacenada en **keyring**.
- Eliminará la carpeta de configuración (`%USERPROFILE%\.aws_video_converter`).

---

## Licencia

Este proyecto está licenciado bajo la [Licencia MIT](LICENSE).
