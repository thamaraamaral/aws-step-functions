# Fichamento sobre AWS Step Functions

Este fichamento tem como objetivo apresentar a AWS Step Functions. Para tanto, serão utilizadas como base as aulas do bootcamp da DIO sobre Engenharia de Prompts.

## Projeto: situação problema

<img src='images\fluxograma.png'>
(Imagem produzida utilizando Canva)

Imagine um sistema de pedidos por aplicativo. Nele, o usuário realiza um pedido. Esse pedido é salvo em seu histórico, *microsserviço 1*. Há um gerenciamento para notificações de usuários e de restaurantes, *microsserviço 2*. Há um gerenciamento do *status* do pedido, *microsserviço 3*.

## Serviços de mensagens assíncronas: o Publisher e o Subscriber
Tradicionalmente, a comunicação entre microsserviços em um sistema como esse é feita através de serviços de mensageria, como RabbitMQ e Apache Kafka. Esses serviços permitem que os microsserviços troquem mensagens de forma assíncrona, mas exigem uma configuração complexa e podem dificultar a visualização e o gerenciamento do fluxo de trabalho como um todo.

A **AWS Step Functions** oferece uma solução mais elegante e visual para orquestrar esses fluxos de trabalho. Em vez de lidar com a complexidade da configuração de serviços de mensageria, a Step Functions permite que você modele o fluxo do seu pedido de forma declarativa, utilizando um diagrama visual. Cada etapa do processo, como validar o pedido, processar o pagamento e enviar a notificação, é representada por um estado na *máquina de estado*. A Step Functions se encarrega de garantir que cada estado seja executado na ordem correta e de lidar com possíveis erros ou exceções.

<img src='images\states.png'>(Breve apresentação dos Step Functions States - Disponível em: https://catalog.workshops.aws/stepfunctions/en-US/introduction/states - Em 31/10/2024 às 09 h)

Além disso, a Step Functions se integra perfeitamente com outros serviços da AWS, como Lambda, SNS e SQS, permitindo que você invoque funções Lambda, publique mensagens em tópicos SNS ou envie mensagens para filas SQS diretamente a partir dos seus estados. Isso simplifica significativamente a construção de sistemas distribuídos e resilientes.

## AWS Step Functions
Pensando no contexto de escabilidade e de sistemas mais complexos, a **AWS Step Functions** foi idealizada. 

A **AWS Step Functions** não é um sistema de serviços de mensageria, é muito mais. *A AWS Step Functions é um serviço gerenciado que permite criar e visualizar workflows (fluxos de trabalho) de forma declarativa, ou seja, usando trabalhos visuais.* Com esse serviço da AWS, é possível utilizar serviços de mensageria para desencadear workflows. 

Assim, a **AWS Step Functions pode ser utilizada para modelar o fluxo de um pedido, desde a criação até a entrega**.

<img src='images\AWS_Step_Functions_HIW.bc3d2930f00dd0401269367b8e8617a7dba5915c.png'>(Disponível em: https://aws.amazon.com/pt/step-functions/ - Em 31/10/2024 às 08 h 30 min)

## Solução com AWS Step Functions 
A Step Functions permite criar máquinas de estado que definem os passos de um workflow. Cada passo pode ser uma tarefa simples (como enviar uma notificação) ou uma chamada para outro serviço (como um Lambda).

<img src='images\workflows.png'>(Breve explicação sobre Step Functions Workflows retirado do site https://catalog.workshops.aws/stepfunctions/en-US/introduction/workflows - Em 31/10/2024 às 08 h 40 min)


## Alguns benefícios da AWS Step Functions
- Fácil configuração e fluxo de trabalho visual;
- Etapas de tratamento de erros, tempo limite e fluxo de processamento prontas e disponíveis;
- Integração direta com serviços disponibilizados pela AWS e, também, com mais de 10 mil APIs.
- Integração de SaaS diretamente do fluxo de trabalho do usuário;
- Facilidade na coordenação de componentes distribuídos

Para saber mais, visite: https://aws.amazon.com/pt/step-functions/features/?pg=ln&sec=hs

## Dica de estudos
No site da AWS Step Functions é possível conferir um **workshop autoguiado do Step Functions**. Esse é um ótimo material para quem quer conhecer o básico sobre a AWS Step Functions.

Para saber mais, visite
https://catalog.workshops.aws/stepfunctions/en-US/
