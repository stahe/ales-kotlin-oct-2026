# Aprender el lenguaje [Kotlin 2.4] mediante ejemplos

📖 **Lea el tutorial: [https://stahe.github.io/ales-kotlin-oct-2026/](https://stahe.github.io/ales-kotlin-oct-2026/)**

Este curso enseña el lenguaje [Kotlin](https://kotlinlang.org/) 2.4 **mediante ejemplos**: más de doscientos programas (337 archivos Kotlin), comentados línea por línea, con sus resultados de ejecución incluidos. Parte de los fundamentos del lenguaje y abarca las corrutinas, el acceso a bases de datos con JDBC y Hibernate, la programación de redes y los servicios web con Spring Boot.

Es la adaptación a Kotlin del curso [Aprender el lenguaje [Java 25]](https://stahe.github.io/ales-java-oct-2026/) (octubre de 2026), que a su vez es una adaptación del curso de [C# 14](https://stahe.github.io/ales-csharp-oct-2026/), una reescritura de un curso de C# de 2008: el mismo esquema, los mismos ejemplos, el mismo hilo conductor, pero escrito en el Kotlin actual. Todos los programas compilan **sin errores ni advertencias** con Kotlin 2.4.20 (con las advertencias tratadas como errores) y se ejecutaron en JDK 25; los resultados reproducidos en el curso son los de estas ejecuciones.

| Curso de Java 25 (2026) | Curso de Kotlin 2.4 (2026) |
|---|---|
| Java 25 (LTS), JDK 25 | Kotlin 2.4.20, JDK 25 |
| archivos fuente compactos (`java Prog.java`) | funciones `main` de alto nivel, `kotlinc`, triángulo verde de IntelliJ IDEA |
| proyectos Maven (`pom.xml`) | proyectos Gradle con Kotlin DSL (`build.gradle.kts`), wrapper de Gradle 9.8 |
| `null`, clases envoltorio y `Optional` | seguridad frente a `null` en el sistema de tipos (`?.`, `?:`, `!!`) |
| métodos de acceso, records, sin sobrecarga de operadores | propiedades, data classes, sobrecarga de operadores, funciones de extensión |
| excepciones verificadas, `try` con recursos | todas las excepciones no verificadas, `use` |
| Stream API | operaciones sobre colecciones, secuencias |
| interfaces funcionales, lambdas | tipos funcionales, lambdas, funciones `inline`, propiedades delegadas |
| `CompletableFuture`, hilos virtuales | **corrutinas**: `suspend`, `launch` / `async`, concurrencia estructurada, `Flow`, `Channel` |
| JUnit 6, Spring Framework 7 | JUnit 6 y `kotlin.test`, Spring Framework 7 (plugin `kotlin-spring`) |
| Jackson 3 | Jackson 3 con data classes |
| JDBC, MySQL Connector/J, HikariCP | lo mismo, con modismos de Kotlin |
| Hibernate 7 | Hibernate 7 con los plugins `kotlin-jpa` (no-arg) y all-open |
| `HttpClient`, `Socket` / `ServerSocket` | las mismas clases, en Kotlin |
| Spring Boot 4 | Spring Boot 4 en Kotlin |

## Esquema del curso

| Capítulo | Contenido |
|---|---|
| Instalación | JDK 25, IntelliJ IDEA / VS Code, el compilador `kotlinc`, Gradle (wrapper, Kotlin DSL), proyectos multimódulo |
| Fundamentos del lenguaje | tipos, `val` / `var`, inferencia de tipos, plantillas de cadenas, cadenas sin procesar, seguridad frente a `null`, conversiones, arreglos, operadores, `when`, rangos y bucles, excepciones, `use`, enumeraciones, parámetros predeterminados y con nombre, funciones locales, `Pair` y desestructuración |
| Clases, interfaces, data classes | constructores primarios, propiedades, `object` y `companion object`, herencia, clases selladas, sobrecarga de operadores, indexadores, value classes, funciones de extensión, interfaces, clases abstractas, genéricos y varianza, paquetes, data classes, conversión inteligente de tipos |
| Clases de Kotlin de uso frecuente | cadenas, arreglos, colecciones de solo lectura y mutables, operaciones funcionales, **secuencias**, archivos de texto y binarios, JSON con Jackson 3, expresiones regulares (`Regex`) |
| Arquitecturas en capas | [DAO] / [lógica de negocio] / [UI], compilaciones Gradle multiproyecto, pruebas unitarias con **JUnit 6** y `kotlin.test`, **inyección de dependencias** con Spring |
| Tipos funcionales, lambdas y eventos | tipos funcionales, lambdas, referencias a funciones, `fun interface`, clausuras, composición, funciones `inline`, listeners, propiedades delegadas observables |
| Hilos de ejecución | `thread { }`, **hilos virtuales**, `synchronized`, `@Volatile`, `ReentrantLock`, `Condition`, operaciones atómicas, semáforos, colecciones concurrentes, `ExecutorService`, fork/join, `ThreadLocal`, `ScopedValue` |
| Programación asíncrona | **corrutinas**: funciones `suspend`, `runBlocking`, `launch`, `async` / `await`, dispatchers, concurrencia estructurada, excepciones, cancelación y tiempos de espera, `Flow`, `Channel`, `CompletableDeferred`, paralelismo limitado, corrutinas e hilos virtuales |
| Acceso a bases de datos con JDBC | MySQL, MySQL Connector/J, `DataSource` y HikariCP, consultas parametrizadas e inyección SQL, transacciones, lotes, JDBC con hilos virtuales y corrutinas |
| **Hibernate** | entidades en Kotlin, `SessionFactory` / `Session`, CRUD, HQL y Criteria API, relaciones, migraciones, concurrencia optimista, SQL nativo, Spring ORM y `@Transactional` |
| Programación web | TCP/IP, IPv6, clientes y servidores TCP (un hilo virtual por cliente), HTTP, `HttpClient`, SMTP con Jakarta Mail |
| Servicios web | REST / JSON con **Spring Boot 4** en Kotlin, clientes de consola en Kotlin, cliente web en JavaScript, cliente Node.js |

## El hilo conductor: una calculadora de impuestos en 9 versiones

A lo largo del curso, versión a versión, se construye una aplicación de **cálculo del impuesto sobre la renta**:

- **Versión 1**: un único programa; **Versión 2**: clases e interfaces; **Versión 3**: datos leídos desde un archivo de texto o JSON;
- **versiones 4 y 5**: una arquitectura en capas, organizada en subproyectos de Gradle, probada con JUnit e integrada mediante inyección de dependencias con Spring;
- **versiones 6 y 7**: datos almacenados en una base de datos MySQL, recuperados mediante JDBC y luego Hibernate;
- **versión 8**: un servidor TCP para el cálculo del impuesto y su cliente;
- **versión 9**: un servicio web REST con Spring Boot, su cliente de consola y su cliente web.

## Tecnologías

Kotlin 2.4.20 · JDK 25 · Gradle 9.8 (Kotlin DSL) · IntelliJ IDEA · kotlinx.coroutines 1.11 · JUnit 6 · Spring Framework 7 · Jackson 3 · MySQL 8 · MySQL Connector/J 9 · HikariCP · Hibernate ORM 7.4 · Jakarta Persistence 3.2 · Spring Boot 4.1 · Laragon

## Requisitos previos

- Experiencia previa en programación en cualquier lenguaje.
- Un [JDK 25](https://adoptium.net) (Eclipse Temurin u otra distribución) e [IntelliJ IDEA](https://www.jetbrains.com/idea/) (Kotlin viene integrado). No es necesario instalar Gradle: cada carpeta de capítulo contiene su propio wrapper (`gradlew`). Si JDK 25 no está instalado, Gradle lo descargará automáticamente (mediante el plugin `foojay-resolver-convention`). [Laragon](https://laragon.org) para MySQL (capítulos sobre bases de datos). Las instrucciones de instalación se proporcionan en el curso.

## Autor

Este curso y su código fueron escritos por **Claude**, la IA de [Anthropic](https://www.anthropic.com) (octubre de 2026), a petición de Serge Tahé, a partir de su curso de Java 25.

Revisor: [Serge Tahé](https://stahe.github.io)
