## wc (word count)

Ferramentas de linha de comando Unix, como o utilitário `wc`, são exemplos de engenharia de software de qualidade, refletindo os princípios fundamentais da Filosofia Unix. Um desses princípios é **escrever partes simples conectadas por interfaces limpas**. Utilitários como o `wc` são projetados para realizar uma única tarefa de forma eficiente, neste caso, contar palavras, linhas e caracteres, oferecendo uma interface de linha de comando (CLI) clara e direta, que lida com entradas de texto vindas de arquivos ou fluxos. Tal simplicidade torna essas ferramentas confiáveis e fáceis de entender.

Outro princípio é o de **desenhar programas para se conectarem a outros programas**. O `wc`, assim como outras ferramentas Unix, pode ser combinado com outros utilitários, permitindo a criação de pipelines para processamento de dados complexos. Tal modularidade é o que torna os utilitários de linha de comando Unix atemporais e eficazes.

O utilitário `wc` é um comando no Unix e sistemas baseados em Unix que é usado para contar o número de linhas, palavras e bytes (ou caracteres) em arquivos de texto ou na entrada padrão (stdin). Ao ser executado, ele exibe, por padrão, três contagens: o número de linhas, o número de palavras e o número de bytes, separados por espaços, para cada arquivo fornecido.

Implementar uma ferramenta como o `wc`, me proporcionou vários aprendizados, como:

- Manipulação de Arquivos e Fluxos de Dados
- Processamento de Strings
- Pipelines e Conexão entre Programas
- Contagem de caracteres em uft-8

A ideia de construção do utilitário `wc` veio do desafio #01 do [Coding Challenges](https://codingchallenges.fyi/challenges/challenge-wc).

### Todo

- [ ] Fazer o `wc` funcionar pelo redirecionamento ou por pipeline sem o uso de das opções (-l,-w,-m). Ou seja:

    ./wc < data/mem.dump
    
    cat data/mem.dum | ./wc

## wc em ação!

[emacao.webm](https://github.com/user-attachments/assets/67967934-1e43-4128-ba92-25681f1a0995)


## Experimente em Sua Máquina

#### Clone o repositório e entre no diretório do repo

    git clone https://github.com/yurincmt/wc.git ; cd wc

#### Instale as Dependências

    # Debian
    sudo apt install build-essential

> Os comando make devem ser executado no diretório raiz do projeto (onde o arquivo Makefile se encontra).

#### Compilar binário

    make build

#### Execute alguns testes

No diretório data/ podem ser encontrados alguns arquivos para testes. Execute das seguintes formas:

    ./wc data/mem.dump
    ./wc -l|-w|-m < data/mem.dump       # redirecionamento para entrada padrão (stdin)
    cat data/mem.dum | ./wc -l|-w|-m    # lê o arquivo por pipeline

## Estrutura do Projeto

    .
    ├── Makefile
    ├── README.md
    ├── data
    │   ├── mem.dump
    │   └── test.txt
    └── src
        ├── main.c
        ├── wc.c
        └── wc.h
