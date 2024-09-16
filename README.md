# Flutter Medical App

Esta es una aplicación médica desarrollada en Flutter. La aplicación proporciona información sobre doctores, categorías médicas y más. 

## Estructura del Proyecto

El proyecto sigue la siguiente estructura de carpetas:

### `lib/models/`
- `category.dart`: Modela las categorías médicas.

Este archivo contiene la definición del modelo `CategoryModel`, que representa una categoría médica en la aplicación. El modelo tiene los siguientes campos:

- `vector`: Una cadena de texto que representa la ruta del archivo SVG asociado con la categoría.
- `isSelected`: Un valor booleano que indica si la categoría está seleccionada.

El modelo incluye un método estático `getCategories()` que devuelve una lista de instancias de `CategoryModel` con algunas categorías predefinidas.


### `lib/models/doctor.dart`

Este archivo define el modelo `DoctorModel`, que representa a un doctor en la aplicación. El modelo incluye varios atributos que describen al doctor, su disponibilidad y otros detalles relevantes. 

#### `DoctorModel`

- `name`: El nombre del doctor.
- `image`: La ruta de la imagen del doctor.
- `imageBox`: Un color de fondo para el cuadro de la imagen del doctor.
- `specialties`: Una lista de especialidades del doctor.
- `score`: La calificación del doctor.
- `bio`: Una breve biografía del doctor.
- `calendar`: Una lista de instancias de `CalendarModel` que indica los días disponibles del doctor.
- `time`: Una lista de instancias de `TimeModel` que muestra los horarios disponibles del doctor.

El modelo también incluye un método estático `getDoctors()` que proporciona una lista de doctores predefinidos.


### `lib/pages/detail.dart`

Este archivo define la página de detalles del doctor (`DetailPage`), donde se muestra información detallada sobre un doctor específico. La página permite a los usuarios ver detalles como la biografía del doctor, sus especialidades, disponibilidad en el calendario y horarios disponibles.

#### `DetailPage`

- **Constructor**: 
  - `doctorModel`: Un objeto `DoctorModel` que contiene la información del doctor que se mostrará en la página.

#### Estado de la Página

- `calendarData`: Lista de instancias de `CalendarModel` que representa la disponibilidad de los días del doctor.
- `timeData`: Lista de instancias de `TimeModel` que representa los horarios disponibles del doctor.

#### Métodos

- **`initState()`**: Inicializa `calendarData` y `timeData` con la información del doctor.
  
- **`build(BuildContext context)`**: Construye la interfaz de usuario de la página, que incluye:
  - **AppBar**: Barra de aplicación con un botón de retroceso y un título.
  - **`info()`**: Muestra información general sobre el doctor, incluyendo su nombre, especialidades, puntuación y biografía.
  - **`calendar()`**: Muestra una lista horizontal de días en el calendario del doctor. Los días pueden ser seleccionados.
  - **`time()`**: Muestra una lista horizontal de horarios disponibles para el doctor. Los horarios pueden ser seleccionados.
  - **`bookButton()`**: Un botón para reservar una cita con el doctor.

El código incluye varios widgets y gestos interactivos para permitir a los usuarios seleccionar fechas y horarios.

### `lib/pages/home.dart`

Este archivo define la página principal (`HomePage`), donde se presenta una lista de categorías y doctores disponibles. La página está diseñada para ofrecer una vista general y permitir la navegación a la página de detalles de un doctor.

#### `HomePage`

- **Constructor**: No tiene parámetros de entrada.

#### Estado de la Página

- `categoriesData`: Lista de instancias de `CategoryModel` que representa las categorías disponibles.
- `doctorsData`: Lista de instancias de `DoctorModel` que representa los doctores disponibles.

#### Métodos

- **`build(BuildContext context)`**: Construye la interfaz de usuario de la página principal, que incluye:
  - **`header()`**: Muestra un encabezado con un saludo, una notificación y un campo de búsqueda.
  - **`categories()`**: Muestra una lista horizontal de categorías. Los elementos pueden ser seleccionados, cambiando su apariencia.
  - **`doctors()`**: Muestra una lista de doctores. Al hacer clic en un doctor, se navega a la página de detalles (`DetailPage`) correspondiente.

El código utiliza `SingleChildScrollView` para permitir el desplazamiento en la página, y cada sección está organizada en columnas y filas para una disposición clara.

### `lib/main.dart`
- Archivo principal que arranca la aplicación.

### `assets/`
- `fonts/`: Fuentes utilizadas en la aplicación.
- `images/`: Imágenes utilizadas en la aplicación.
- `vectors/`: Gráficos vectoriales utilizados en la aplicación.
