## Notas do livro Expressões Regulares - Marinho Jargas

#### Capítulo 2

### Representantes

| Metacaractere | Função| 
|:-----:|-----|
| .   | Um caractere qualquer| 
| []  | Lista de caracteres permitidos e são literais|  
|  [^]| Lista de caracteres proibidos(negação) |

### Quantificadores

| Metacaractere |	Função |
|:----:|----|	
|?    | Zero ou um caractere(Opcional)|
|*	|Zero ou mais(Curinga)|
|+|	Um ou mais (Não opcional, pelo menos um)|
|{n,m}	|De n até m(Controle)|

### Âncoras

|Metacaractere	| Função|
|:----:|-----|
|^|	Início da linha(fica fora da lista)|
|$|	Fim da linha |
|\b|	Borda, início ou fim da palavra|

* Início da linha

    ^[^0-9]		

* Linha vazia

    ^$ 		

* Linhas que tenham entre 20 e 60 caracteres

    ^.{20,60}	

* Casa com: dia, diagragma, bom-dia

    \bdia		

* Casa com: dia, melodia, bom-dia

    dia\b		

### Outros

|Metacaractere|	Função|
|:---:|---|
|\c|	Escape, torna o caractere c literal|
|	\| |Um ou outro(alternativa)|
|()|	Delimita um grupo|
|\1...\9|	Retrovisor, usado para casar grupos de 1-9 (casa trechos já casados, útil quando se sabe o que será casao máximo são 9)|

#### Exemplos
* Boa-tarde|boa-noite
* (ha!)+				
    - ha!, ha!ha! ....
* (\.[0-9]){3}			
    - .0.1.2, .2.3.6 ...
* Boa-(tarde|noite)		
    - Boa-tarde, Boa-noite
* (# | n\.|núm) 7			
    - \# 7, n. 7, núm 7
* (in|con)?certo			
    - incerto, concerto, certo
* ((su|hi)per)?mercado		
    - mercado, supermercado, hipermecardo
* [[:alpah:]_]+\(\)			
    - útil para achar funções em códigos
* (quero)-\1			
    - quero-quero
* ([A-Za-z]+)-\1			
    - quero-quero, bate-bate
* ([A-Za-z]+)-?\1			
    - quero-quero, bate-bate, bombom, lili, dudu, bibi 
* \b([A-Za-z]+)-?\1\b
* (lenta)(mente) é \2 \1		
    - lentamente é mente lenta
* ((band)eira)nte \1 \2		
    - bandeirante badeira banda
* ((((a)b)c)d)-1 \1,\2,\3,\4	
    - abcd-1 = abcd, abc, ab,a
* Contar os parênteses da esquerda para a direita, esse vai ser o número do retrovisor.
* O retrovisor referencia o texto casado, encontrado, e não a expressão regular do grupo.
* (\[0-9])\1	66 mas não casa com 69 porque o \1 é 6, dessa forma, só casa números iguais.

### Intervalos

* 0-9	a-z	A-Z	|Não casam com letras acentuadas
* \[ 	Pode ficar em qualquer posição dentro de uma lista
* \]	Deve ficar no início de uma lista para não confundir com o fechamento da lista

# Posix - Para resolver caracteres acentuados e outras coisas mais

|Classe POSIX|	Similar	|Significado|
|:---:|----|----|
|[:upper:]|	\[A-Z]	|Letras maiúsculas|
|[:lower:]|	\[a-z]	|Letras minúsculas|
|[:alpha:]|	\[A-Za-z]	|Maiúsculas e minúsculas|
|[:alphanum:]|	\[A-Za-z0-9]	|Letras e números|
|[:digit:]|	\[0-9]	|Números|
|[:xdigit:]|	\[0-9A-Fa-f]|	Números hexadecimais|
|[:punc:]|	\[.,!?;...]|	Sinais de pontuação|
|[:blank:]|	\[ \t]	|Espaço e tab|
|[:space:]|	\[ \t\n\r\f\v]	|Caracteres brancos|
|[:cntrl:]|		|Caractere de controle|
|[:graph:]|	\[^ \t\n\r\f\v]	|Caracteres imprimíveis|
|[:print:]|	\[^ \t\n\r\f\v]	|Imprimíveis e o espaço|

* Maiúscula dentro de uma lista [[:upper:]]. É necessário usar o colchete do posix e da lista.
* \[^[:alpha:]]	Não vai pegar letras maiúsculas ou minúsculas acentuadas ou não
* :-@		Do : até o @ na tabela 
* A-z		Do A até o z na tabela 

#### Capítulo 3

#### Capítulo x 

### RegEx no Python
