# Atividade Final - Solução de ambiente AWS com Kubernetes 

Este repositório contém a atividade final do Programa de Bolsas DevSecOps - JUN 2024. O projeto tem como objetivo desenvolver uma proposta de solução arquitetônica e financeira para uma empresa fictícia, fornecendo uma infraestrutura escalável e robusta para seu eCommerce. A proposta inclui valores, prazos de entrega e um cronograma macro de entregas.

## Seções com Ícones Representativos

1. **Modernização da Infraestrutura**
   - **Descrição:** Migração para a Nuvem AWS, aproveitando a alta disponibilidade, segurança e escalabilidade da plataforma.

2. **Arquitetura de Microsserviços com Docker e Kubernetes**
   - **Descrição:** Decomposição da aplicação em serviços independentes, permitindo escalonamento granular e maior resiliência. Containerização com Docker e orquestração com Kubernetes para otimizar recursos e simplificar o gerenciamento.

3. **Banco de Dados de Alta Performance**
   - **Descrição:** Migração para AWS RDS Aurora MySQL, um serviço de banco de dados relacional compatível com MySQL, oferecendo alta performance, escalabilidade e disponibilidade. Implementação de estratégias de replicação e clusterização para garantir a continuidade do negócio.

4. **CDN para Conteúdo Estático (AWS CloudFront)**
   - **Descrição:** Distribuição global de conteúdo estático (imagens, vídeos, links) utilizando S3, reduzindo a latência, melhorando a performance e otimizando custos.

5. **Balanceamento de Carga (AWS Application Load Balancing)**
   - **Descrição:** Distribuição inteligente do tráfego entre as instâncias da aplicação, garantindo alta disponibilidade e tolerância a falhas através de target groups com health check.

6. **Auto Scaling (AWS Auto Scaling)**
   - **Descrição:** Ajuste automático da capacidade de processamento com base sob demanda, garantindo performance consistente mesmo em picos de acesso e otimizando os custos.

7. **Monitoramento e Alertas (AWS CloudWatch)**
   - **Descrição:** Monitoramento 24/7 da infraestrutura e aplicações com alertas proativos para identificar e solucionar problemas rapidamente. Dashboards customizados para visualização da performance e saúde do sistema.

8. **Segurança Reforçada**
   - **Descrição:** Implementação de melhores práticas de segurança na nuvem, firewalls (AWS WAF), monitoramento de segurança e uso do Key Management Service (KMS) para proteger os dados.

---

## 2. Arquitetura da Nova Solução

A arquitetura proposta alinha-se com as melhores práticas DevOps e é composta pelos seguintes elementos:

- **Camada de Aplicação:**
  - **EKS Cluster:** Hospeda a aplicação React containerizada, permitindo escalabilidade horizontal automática.

- **Camada de Dados:**
  - **Amazon Aurora for MySQL Multi-AZ:** Banco de dados relacional gerenciado com alta disponibilidade e failover automático.

- **Camada de Armazenamento Estático:**
  - **Amazon S3:** Armazena conteúdos estáticos com integração ao CloudFront para distribuição.
  - **Amazon CloudFront:** Acelera a entrega de conteúdo aos usuários finais globalmente.

- **Camada de Rede e Segurança:**
  - **Application Load Balancer:** Distribui o tráfego entre os pods do EKS, com health checks configurados.
  - **VPC com Sub-redes Públicas e Privadas:** Isola recursos e controla o fluxo de tráfego.
  - **AWS WAF e Shield:** Protegem a aplicação contra ameaças comuns e ataques DDoS.
  - **IAM Policies e Security Groups:** Restrição de acesso baseada em funções e necessidades específicas.

- **Monitoramento e Backup:**
  - **AWS CloudWatch:** Monitora métricas e logs, permitindo ações proativas.
  - **AWS Backup:** Automatiza backups regulares do RDS e outros recursos críticos.

<div align="center">
  <img src="/src/AWS-diagram.jpg" width="720px">
   <p><em>Nova Arquitetura</em></p>
</div>

---

## 3. Valores (Estimativa de Custos)

**Custos Mensais Aproximados:**

- Pods EKS 4x: **US$ 292**
- **Amazon Aurora for MySQL Multi-AZ (db.r3.large):** **US$ 467**
- **Amazon S3 e CloudFront:** **US$ 210**
- **AWS Backup e Armazenamento de Backups:** **US$ 32**
- **Outros Serviços (VPC, CloudWatch, WAF, etc.):** **US$ 41**
<div align="center">
  <img src="/src/estimativa-projeto.png" width="720px">
   <p><em>Representação da estimativa de preço</em></p>
</div>

**Total Estimado Mensal:** **US$ 1042**

**Total Estimado Anual:** **US$ 12500**

---

## 4. Prazo de Entrega

**Tempo Total Estimado:** **21 dias úteis com uma equipe de 3 pessoas**

**Trabalhando 6 horas por dia**

**Total de horas trabalhadas até a entrega: 378 horas**
<div align="center">
  <img src="/src/crono.png" width="720px">
   <p><em>Cronograma Macro de Entregas</em></p>
</div>


---

## 5. Cronograma Macro de Entregas

### **Semana 1: Planejamento e Configuração Inicial da Infraestrutura**

- Revisão detalhada dos requisitos e definição do escopo final.
- Configuração da VPC, sub-redes, tabelas de rotas e gateways.
- Implementação de políticas IAM e criação de usuários e funções necessárias.
- Configuração do cluster Amazon EKS.
- Criação e configuração do Amazon Aurora for MySQL com Multi-AZ

### **Semana 2: Definição da Infraestrutura e Deploy da Aplicação**

- Configuração do Amazon S3 e CloudFront para armazenamento estático.
- Containerização da aplicação React e deploy nos pods do EKS.
- Integração com o Application Load Balancer e configuração de health checks.
- Configuração do AWS WAF e AWS Shield para proteção avançada.
- Definição e implementação de grupos de segurança.

### **Semana 3: Backup, testes e otimizações finais**

- Configuração do AWS Backup para políticas de backup automatizadas.
- Realização de testes de carga, desempenho e segurança.
- Otimizações baseadas nos resultados dos testes.
- Configuração do AWS CloudWatch para monitoramento e alertas.

### **Semana 4: Go-Live e Documentação**

- Migração final e cutover para o novo ambiente.
- Treinamento da equipe de TI da "Fast Engineering S/A".
- Entrega de documentação completa e suporte pós-implementação inicial.
