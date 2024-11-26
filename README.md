# lab01- sumador 
## Alejandro Zapata

## informe de laoratorio 

### sumador 
Entregable 1: Comentarios sobre sum1bcc_primitive.v
Descripción del archivo sum1bcc_primitive.v
El archivo implementa un sumador completo de un bit utilizando una descripción estructural, basada en compuertas lógicas.

Componentes principales
Entradas:

A: Primer bit de entrada.
B: Segundo bit de entrada.
Ci: Acarreo de entrada.
Salidas:

S: Resultado de la suma sin acarreo.
Cout: Acarreo generado por la suma.
Señales intermedias (wire):

a_ab: Representa A · B.
x_ab: Representa A ⊕ B.
cout_t: Representa (A ⊕ B) · Ci.
Ecuaciones lógicas implementadas
S = (A ⊕ B) ⊕ Ci.
Cout = (A · B) + ((A ⊕ B) · Ci).
Funcionamiento
Se utilizan compuertas lógicas básicas (AND, OR, XOR) para implementar la lógica de la tabla de verdad de un sumador completo. Cada operación lógica está conectada a través de señales (wire), simulando las conexiones físicas entre compuertas.

Entregable 2: Comentarios sobre sum1bcc.v
Descripción del archivo sum1bcc.v
El archivo implementa el mismo sumador completo, pero utiliza una descripción funcional, basada en operaciones aritméticas.

Componentes principales
Entradas:

A: Primer bit de entrada.
B: Segundo bit de entrada.
Ci: Acarreo de entrada.
Salidas:

S: Resultado de la suma sin acarreo.
Cout: Acarreo generado por la suma.
Registro (reg) de 2 bits:

st[0]: Almacena el resultado de la suma (S).
st[1]: Almacena el acarreo generado (Cout).
Funcionamiento
El bloque always @(*) realiza la suma de las tres entradas (A + B + Ci) cada vez que alguna cambia. El resultado se almacena en el registro st, que se divide en dos partes:

st[0]: Bit menos significativo (S).
st[1]: Bit más significativo (Cout).

## Diferencias entre `sum1bcc_primitive.v` y `sum1bcc.v`

**Diferencias clave:**

- `sum1bcc_primitive.v`: Implementación estructural basada en compuertas lógicas explícitas.  
- `sum1bcc.v`: Implementación funcional basada en operaciones aritméticas.

| Aspecto                 | `sum1bcc_primitive.v`                           | `sum1bcc.v`                                 |
|-------------------------|-------------------------------------------------|---------------------------------------------|
| **Tipo de descripción** | Estructural: Usa compuertas lógicas explícitas. | Funcional: Usa una operación aritmética.    |
| **Uso de señales**       | Define señales intermedias (`wire`).           | Usa un registro (`reg`) para almacenar resultados. |
| **Lógica**              | Basada en operaciones lógicas explícitas.       | Implementada de forma implícita al sumar.   |
| **Complejidad**         | Más detallado, adecuado para diseño a nivel de hardware. | Más compacto, adecuado para simulación.    |

