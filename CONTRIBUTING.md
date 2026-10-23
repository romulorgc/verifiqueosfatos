# Como contribuir

Dá para ajudar de três jeitos: sugerindo uma fala para checar, apontando um erro numa checagem ou mandando um PR (com checagem ou com código).

- Sugerir uma fala: [abra uma issue "Sugerir uma fala para checar"](https://github.com/felippe-regazio/verifiqueosfatos/issues/new?template=sugerir-checagem.yml)
- Apontar um erro: [abra uma issue "Pedir correção"](https://github.com/felippe-regazio/verifiqueosfatos/issues/new?template=correcao.yml)

## Escrevendo uma checagem

### O que dá para checar

Só falas que podem ser conferidas com dados públicos: números, datas, leis, votações, o que alguém disse ou fez. Opinião, promessa e previsão ficam de fora, porque não há dado que diga se são verdadeiras.

### Passo a passo

1. **Transcreva a fala** o mais literal possível no campo `t`. Coloque na descrição do PR onde e quando ela foi dita (ex.: debate da Globo, 2º bloco, 21h40).
2. **Ache a fonte primária**: o dado no órgão que o produz (IBGE, Banco Central, TSE, Tesouro Nacional, Diário Oficial, Portal da Transparência, Câmara, Senado). Reportagem ajuda a achar o dado, mas não deve ser a única fonte.
3. **Classifique com a régua do rodapé** do site:
   - **Verdadeiro**: a fala confere com os dados
   - **Falso**: a fala contradiz os dados
   - **Parcial**: parte confere, mas há exagero, imprecisão ou falta de contexto
4. **Escreva a verificação** no campo `v`: o que foi conferido, qual é o dado certo e de onde ele vem. Sem adjetivo e sem comentário sobre o candidato.
5. **Coloque os links das fontes** no campo `s`.
6. **Abra o PR** e peça para outra pessoa conferir antes do merge. O checklist do PR ajuda a não esquecer nada.

### A mesma régua para todos

Uma fala é classificada pelo que os dados mostram, nunca por quem disse. Se você não aplicaria a mesma classificação a uma fala parecida do outro candidato, revise.

### Correções

Errar acontece, ainda mais ao vivo. Quando uma checagem publicada estiver errada:

- corrija o mesmo item no `posts.json`, sem apagar e criar outro, para os links já compartilhados continuarem levando à checagem certa
- explique no PR o que mudou e por quê, com a fonte

## Mexendo no código

Leia as premissas no [README](README.md): mínimo de bytes, nenhuma dependência e nada além do necessário.

- Se mudar um arquivo que o `sw.js` guarda no cache, suba o `CACHE_NAME` (a CI confere)
- Antes de mandar, valide o `posts.json` com `python scripts/validate_posts.py posts.json`
