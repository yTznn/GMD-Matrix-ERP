# 🐂 GMD Matrix - Sistema de Gestão Pecuária de Precisão (Módulo Cria)

![Status](https://img.shields.io/badge/Status-Em_Desenvolvimento%20(Fazenda_Piloto)-warning)
![Stack](https://img.shields.io/badge/Stack-C%23%20.NET%208%20(LTS)-blueviolet)
![Arquitetura](https://img.shields.io/badge/Arquitetura-Clean%20Architecture%20%7C%20SaaS%20Multi--tenant-orange)
![Database](https://img.shields.io/badge/ORM-EF%20Core%20%2B%20Dapper-informational)

> 🔒 **Aviso de Propriedade Intelectual:** Este é um repositório de demonstração (Showcase). O GMD Matrix é um produto comercial (Startup) com lançamento previsto para a **TecnoShow 2026**. Por conter algoritmos de inteligência zootécnica e arquitetura proprietária, o código-fonte principal é fechado.

## 💡 A Visão do Produto e o Desafio
[cite_start]Na pecuária de corte, a fase de "Cria" é onde o lucro nasce[cite: 255]. [cite_start]A eficiência é medida pela capacidade da matriz em produzir um bezerro pesado por ano[cite: 271]. [cite_start]O desafio do mercado atual é a dependência de controles manuais e planilhas descentralizadas, que geram perda de histórico genealógico e atraso na tomada de decisão[cite: 256].

[cite_start]O **GMD Matrix** nasceu para digitalizar o fluxo de informação no campo[cite: 273]. [cite_start]A plataforma unifica o controle de matrizes, reprodutores e suas proles, focando no diferencial competitivo do sistema: o **GMD Inteligente (Ganho Médio Diário)**, que avalia o desempenho individual e do lote desde o nascimento até a desmama[cite: 257, 258].

## ⚙️ Engenharia e Arquitetura de Software
[cite_start]O sistema foi projetado para operar na nuvem (Software as a Service)[cite: 255], utilizando metodologias modernas para garantir segurança e performance em larga escala.

### 1. Arquitetura Multi-Tenant
* [cite_start]Para democratizar o acesso, o sistema permite que múltiplas propriedades rurais (Tenants) utilizem a mesma infraestrutura[cite: 260, 274].
* [cite_start]A segurança é garantida no nível da modelagem de domínio: todas as entidades principais herdam de uma classe base abstrata `Entity` com um `TenantId`[cite: 286, 308], garantindo o isolamento absoluto dos dados de cada fazenda no banco de dados.

### 2. Abordagem Híbrida de Persistência (ORMs)
[cite_start]Para equilibrar integridade e velocidade, implementei uma estratégia de persistência dupla[cite: 280, 281]:
* [cite_start]**Entity Framework Core:** Utilizado para os comandos de escrita (CRUD) e modelagem complexa do domínio (Matrizes, Partos, Genealogia)[cite: 281].
* [cite_start]**Dapper (Micro-ORM):** Utilizado para as consultas de alta performance e geração de relatórios pesados (Dashboard de Natalidade, Ranking de GMD), acessando o banco quase no estado da arte do SQL para evitar gargalos[cite: 281, 268].

## 🚀 Principais Módulos Funcionais
* [cite_start]🧬 **Ciclo Reprodutivo Automatizado:** Lançamentos de coberturas e partos geram automaticamente a árvore genealógica (pai/mãe) no cadastro dos bezerros[cite: 264].
* [cite_start]🩺 **Manejo Sanitário:** Controle completo de vacinas, doenças e medicamentos[cite: 265].
* [cite_start]📊 **Monitoramento de Desmama (O Diferencial):** Cálculo automático de GMD, comparando o peso ao nascer com o peso à desmama, gerando um ranking dos melhores animais do lote[cite: 244, 267].

## 🎯 Status Atual: AgroStartUp & TecnoShow
O projeto está atualmente em validação em ambiente real (Fazenda Piloto), concorrendo no programa **AgroStartUp** das universidades públicas, com estruturação tecnológica focada em escala comercial para apresentação oficial na **TecnoShow 2026**.