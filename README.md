# 📊 WAP Invest - Simulador de FIIs Inteligente

![Status](https://img.shields.io/badge/Status-Concluído-green) ![Event](https://img.shields.io/badge/Bootcamp-DIO-blue)

## 📝 Sobre o Projeto
Este projeto foi desenvolvido como parte do desafio técnico do **Bootcamp Santander (Excel + AI)** da [DIO](https://www.dio.me/).

O objetivo foi criar uma ferramenta de simulação para **Fundos Imobiliários (FIIs)** que ajuda o investidor a balancear a carteira automaticamente baseado no seu perfil de risco, sem a complexidade de macros ou scripts pesados.

## 🧠 A Lógica: Simplicidade e Performance
O diferencial técnico deste projeto é a estruturação dos dados. Em vez de utilizar fórmulas matriciais complexas ou inúmeros `SE` (nested IFs), optei por criar um relacionamento via **Chave Primária Artificial**.

### O Método da Chave Concatenada
Para cruzar o **Perfil do Investidor** com o **Tipo de Ativo**, criei uma chave única em ambas as tabelas (Dados e Simulador) utilizando uma fórmula simples de concatenação:

```excel
=C7 & "-" & D7
// Resultado Exemplo: "CONSERVADOR-PAPEL"
```

Isso permitiu transformar uma busca de dois critérios em uma busca simples e rápida com ```PROCV``` (VLOOKUP):
```
=PROCV(ChaveGerada; TabelaDados; 4; 0)
```

Essa abordagem torna a planilha muito mais leve e fácil de auditar do que soluções que usam ```SOMASES``` ou ```DESLOC```.

## 🎯 Funcionalidades
Perfil de Investidor Dinâmico: Ao mudar o perfil para Conservador, Moderado ou Agressivo, a planilha reconstrói a chave de busca e atualiza toda a alocação de ativos instantaneamente.

Simulação de Longo Prazo: Projeção de patrimônio e dividendos acumulados para até 30 anos baseada em juros compostos.

Cálculo Reverso: A ferramenta sugere o aporte ideal baseado na meta de investimento do usuário.

## 🛠️ Stack Utilizada
Microsoft Excel: Modelagem de dados, Fórmulas lógicas e Financeiras.

Git/GitHub: Documentação e versionamento de projeto.

## 🚀 Como testar
Baixe o arquivo ```.xlsx``` deste repositório.

Na aba Simulador, vá na célula de "Perfil" (amarela).

Troque as opções e veja as porcentagens da tabela inferior mudarem automaticamente através da busca por chaves.
#
_Desenvolvido por [William Pires](https://www.linkedin.com/in/williamapires) | Focando em soluções de dados eficientes._
