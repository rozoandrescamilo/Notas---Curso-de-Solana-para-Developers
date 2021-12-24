# Notas---Curso-de-Solana-para-Developers

Profesora Carolina Velásquez
@kornatis

![](https://static.platzi.com/media/avatars/Platzi-f730e65b-e92b-44d3-81c0-5c59c4dc4658.png) ![](https://static.platzi.com/media/learningpath/badges/29fa8885-7536-44ba-8aea-7b32c8e39cc8.jpg) ![](https://static.platzi.com/media/achievements/piezas-solana-developers_badge-a5af9261-31ab-4d9d-be89-1410fd05e91b.png)

## Tabla de Contenidos

- [¿Qué es Solana?](#qué-es-solana)
  - [Proof of History (POH)](#proof-of-history-poh) 
- [Funcionamiento de Solana](#introducción-a-la-programación-con-solidity)
  - [Tower BFT](#tower-bft)
  - [Turbine](#turbine) 
  - [Gulf Stream](#gulf-stream)
  - [Sealevel](#sealevel)
  - [Pipelining](#pipelining)
  - [Cloudbreak](#cloudbreak)
  - [Archivers](#archivers)
  - [Accounts](#accounts)
- [Interacción con la red](#interacción-con-la-red)
  - [Clusters](#clusters)
  - [Clientes](#clientes)
  - [Flujo de trabajo de desarrollo en Solana](#flujo-de-trabajo-de-desarrollo-en-solana)
  

[![1](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/1.jpg?raw=true "1")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/1.jpg?raw=true "1")

# ¿Qué es Solana?

Página oficial: https://solana.com/es

Whitepaper de Solana escrito por Anatoly Yakovenko: https://solana.com/solana-whitepaper.pdf

Repositorio oficial en GitHub: https://github.com/solana-labs/

Solana es la cadena de bloques más rápida del mundo y el ecosistema de más rápido crecimiento en criptografía, con más de 400 proyectos que abarcan DeFi, NFT, Web3 y más.

La escalabilidad de Solana garantiza que las transacciones permanezcan por debajo de $ 0.01 tanto para desarrolladores como para usuarios.

Una de las innovaciones esenciales que Solana aporta es el consenso de la prueba de historia (PoH) desarrollado por Anatoly Yakovenko. Este concepto permite una mayor escalabilidad del protocolo, lo que a su vez aumenta la facilidad de uso.

Solana es conocida en el espacio de las criptomonedas debido a los tiempos de procesamiento increíblemente cortos que ofrece la cadena de bloques. El protocolo híbrido de Solana permite tiempos de validación significativamente reducidos tanto para la transacción como para la ejecución de contratos inteligentes. Con tiempos de procesamiento increíblemente rápidos, Solana también ha atraído mucho interés institucional.

[![2](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/2.png?raw=true "2")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/2.png?raw=true "2")

Es la red blockchain más rápida del mercado con 50.000 transacciones por segundo e incluso más, más de 1.500 validadores y puede generar un bloque cada 400 milisegundos.

[![3](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/3.png?raw=true "3")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/3.png?raw=true "3")

Comparativa de uso de energía en una sola transacción en Solana medida en Julios:

[![4](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/4.png?raw=true "4")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/4.png?raw=true "4")

PoW es probabilístico, todos los validadores tienen la misma probabilidad de encontrar la solución al problema.

[![5](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/5.png?raw=true "5")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/5.png?raw=true "5")

PoS es determinístico, la red asigna cuales son los nodos que validarán la transacción.

[![6](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/6.png?raw=true "6")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/6.png?raw=true "6")

Solana utiliza PoS y PoH (Proof of History) para sincronizar la red y que sea más rápida.

## Proof of History (POH)

PoH es una función de retardo verificable implementada como una función hash secuencial.

¿Qué pasaría si en lugar de confiar en la marca de tiempo pudiera probar que el mensaje ocurrió en algún momento antes y después de un evento? Cuando te tomas una fotografía con la portada del New York Times, estás creando una prueba de que tu fotografía fue tomada después de que se publicó ese periódico, o tienes alguna forma de influir en lo que publica el New York Times. Con Proof of History, puede crear un registro histórico que demuestre que un evento ha ocurrido en un momento específico en el tiempo. 

La Proof of History es una función de retardo verificable de alta frecuencia. Una función de retardo verificable requiere un número específico de pasos secuenciales para evaluar, pero produce un resultado único que se puede verificar de manera eficiente y pública.

[![8](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/8.png?raw=true "8")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/8.png?raw=true "8")

A manera de ejemplo se menciona como funcionan las llamadas y las antenas se menciona el modelo TDMA - Acceso múltiple por división de tiempo, el ancho de banda se divide en diferentes espacios de tiempo donde cada usuario puede comunicar un mensaje.

[![7](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/7.png?raw=true "7")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/7.png?raw=true "7")

PoH explicado por Anatoly Yakovenko: https://medium.com/solana-labs/proof-of-history-a-clock-for-blockchain-cf47a61a9274 

# Funcionamiento de Solana

## Tower BFT

Byzantine Fault Tolerance garantiza una tolerancia a fallos del sistema, si una parte del sistema (procesador) falla las demás partes deben seguir funcionando.

[![9](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/9.png?raw=true "9")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/9.png?raw=true "9")

Tower BFT es un protocolo de tolerancia a fallas bizantinas que combinado con Proof of History ayuda a mantener el funcionamiento seguro de su protocolo de consenso y red descentralizada. Tower BFT, es una evolución de Practical Bizantine Fault Tolerance (PBFT) un protocolo de tolerancia a fallas bizantinas bien conocido en el mundo de la computación distribuida.

[![10](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/10.png?raw=true "10")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/10.png?raw=true "10")

Tower BFT por Anatoly Yakovenko: https://medium.com/solana-labs/tower-bft-solanas-high-performance-implementation-of-pbft-464725911e79

## Turbine

Es un método de propagación de transacciones en Solana.

Ejemplo de red tradicional :

[![11](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/11.png?raw=true "11")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/11.png?raw=true "11")

Enviar 128 MB a 20.000 validadores puede ser complicado en la red tradicional de Bitcoin, pero Solana basandose en el protocolo de **BitTorrent** logra solucionar este problema.

Hay dos conceptos clave en BitTorrent: el TCP donde la comunición esta orientada a conexión con una línea directa para enviar un mensaje, y el UDP que es una conexión orientada a enviar el mensaje por paquetes. Este último es donde Solana hace lo mismo con la información que pasa por su red.

[![12](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/12.png?raw=true "12")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/12.png?raw=true "12")

En la red de Solana el líder divide el bloque en paquetes de hasta 64 KB de tamaño.  Para un bloque de 128 MB, el líder produce 2000 paquetes de 64 KB y transmite cada paquete a un validador diferente.

[![13](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/13.png?raw=true "13")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/13.png?raw=true "13")

¿Que pasa si hackers quieren apoderarse de la red y hacer una ataque eclipse?

**Ataque eclipse: Busca desconectar a la víctima del flujo de datos válido de la red. Esto con el propósito de que la víctima reciba datos manipulados por la parte del atacante. 

Para prevenir esto en la red se envían datos cifrados sobre cual será el próximo nodo donde irá la información, se tendría que hackear o alterar todos los nodos a la vez para poder vulnerarla.

## Gulf Stream

Primero hay que entender el concepto de **mempool** que son la cantidad de transacciones sin confirmar dentro de la red, en Bitcoin se encuentra en 10.000 - 20.000. Para esto Solana creó el protocolo Gulf Stream que es un reenvío de transacciones sin mempool.

[![14](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/14.png?raw=true "14")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/14.png?raw=true "14")

Gulf Stream es un protocolo de almacenamiento en cache de las transacciones de la red. Es el encargado de recibir la transacción y mandarla a todos los nodos, priorizando a los nodos generadores. Permite a todos los nodos de la red acceder a la información necesaria para la recreación de los bloques, lo que ayuda a los validadores a confirmar las transacciones antes de que se finalice el siguiente bloque, reduciendo los tiempos de confirmación y permite un volumen de transacciones sustancial.

Suponiendo que un bloque se genera cada 800 ms, para que un bloque sea totalmente validado es necesario un TTL - Time to Live (# de bloques que tiene ~ 32 bloques) significa que en 24 s la transacción va estar totalmente validada.

[![15](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/15.png?raw=true "15")](https://github.com/hackmilo/Notas---Curso-de-Solana-para-Developers/blob/main/img/15.png?raw=true "15")

## Sealevel



## Pipelining
## Cloudbreak
## Archivers
## Accounts

# Interacción con la red

## Clusters
## Clientes
## Flujo de trabajo de desarrollo en Solana