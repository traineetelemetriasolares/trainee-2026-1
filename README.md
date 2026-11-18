# Desafio Trainee Telemetria 2026/1 – Mini-Barco

Repositório do desafio trainee de **Telemetria e Gerenciamento Energético** (edição 2026/1, abril). O objetivo do desafio é desenvolver um sistema de telemetria completo aplicado a um **mini-barco funcional**, simulando em escala reduzida parte das funcionalidades do barco de competição da equipe.

> ⚠️ **Status do projeto: incompleto.** Somente a **Etapa 1 (prototipagem/simulação)** foi concluída. A **Etapa 2 (montagem física e integração com o mini-barco)** não foi finalizada, e, por consequência, as etapas seguintes (servidor/web e integração final) não foram iniciadas.

---

## Sumário

- [Visão geral do desafio](#visão-geral-do-desafio)
- [Status das etapas](#status-das-etapas)
- [Etapa 1 – Protótipo no Tinkercad](#etapa-1--protótipo-no-tinkercad)
- [Etapa 2 – Montagem física (não concluída)](#etapa-2--montagem-física-não-concluída)
- [Estrutura do repositório](#estrutura-do-repositório)
- [Próximos passos](#próximos-passos)
- [Referências](#referências)

---

## Visão geral do desafio

O desafio é dividido em quatro etapas, cobrindo sistemas embarcados, eletrônica, telemetria, controle de motores, comunicação sem fio, backend, banco de dados, desenvolvimento web e integração de sistemas:

| Etapa | Descrição |
|-------|-----------|
| 1 | Desenvolvimento e simulação do sistema embarcado (leitura de sensores, interpretação de comandos e controle do mini-barco) |
| 2 | Montagem física do sistema eletrônico com ESP32 e integração com o mini-barco |
| 3 | Servidor web que se comunica com o ESP32 via HTTP e Socket.IO, armazena os dados e oferece monitoramento em tempo real |
| 4 | Integração completa no mini-barco, com testes práticos de funcionamento, comunicação e monitoramento |

O enunciado completo está em [`Desafio Trainee Telemetria 2026_1.pdf`](./Desafio%20Trainee%20Telemetria%202026_1.pdf).

## Status das etapas

| Etapa | Status |
|-------|--------|
| 1 – Simulação no Tinkercad | ✅ Concluída |
| 2 – Circuito físico e integração com o mini-barco | ❌ Não concluída |
| 3 – Backend e página web | ⬜ Não iniciada |
| 4 – Integração final | ⬜ Não iniciada |

## Etapa 1 – Protótipo no Tinkercad

O protótipo foi desenvolvido e simulado no [Tinkercad Circuits](https://www.tinkercad.com/circuits), com base em uma placa **Arduino UNO**. O esquemático exportado está em [`Esquemático circuito trainees 2026_1.pdf`](./Esquem%C3%A1tico%20circuito%20trainees%202026_1.pdf) (projeto "12 - DISPLAY LCD 16x2").

### Requisitos da etapa

Conforme o enunciado, o sistema embarcado deve interpretar, monitorar e transmitir:

- **Botão on/off**: indica se o sistema está ligado ou desligado.
- **Sensor de temperatura**: leitura em graus Celsius.
- **Potenciômetro (acelerador)**: 0 V corresponde à velocidade 0 e a tensão máxima, à velocidade máxima.
- **Controle de motor por PWM**: ajuste da velocidade do motor.
- **LCD**: exibe temperatura, intensidade do acelerador e status do sistema.

### Componentes presentes no esquemático

| Componente | Função |
|------------|--------|
| Arduino UNO (U1) | Microcontrolador do protótipo |
| Display LCD 16x2 (U2) | Exibição de temperatura, acelerador e status |
| Botão (S2) com resistor de 10 kΩ (R2) | Liga/desliga o sistema |
| Potenciômetro de 250 kΩ | Acelerador (entrada analógica) |
| Potenciômetros de 10 kΩ (2×) | Ajuste do display (contraste/brilho) |
| Sensor de temperatura (U3) | Medição da temperatura |
| Transistor NPN (T1) + motor DC (M1) | Acionamento do motor via PWM |
| LED vermelho (D1) com resistor de 330 Ω (R3) | Indicação de status |
| Resistores de 220 Ω (R1) e 1 kΩ (R4) | Limitação de corrente |
| Servo motor (SERVO1) | Atuador adicional |
| Bateria (P1) | Alimentação |

### Entregáveis da etapa

Segundo o enunciado, esta etapa pede a apresentação da simulação funcional (sensores, controle do motor, LCD e lógica de funcionamento) e um relatório com dificuldades encontradas, soluções adotadas, limitações do sistema e decisões de projeto.

## Etapa 2 – Montagem física (não concluída)

A montagem física **não foi finalizada**. O que o enunciado previa para esta etapa:

- Montar o circuito físico utilizando **ESP32**.
- Integrar o sistema ao mini-barco.
- Controlar o motor.
- Implementar o envio de dados via **Wi-Fi** (HTTP) para o servidor.
- Garantir alimentação estável do sistema.

Funcionalidades extras sugeridas: monitoramento de bateria, leitura de corrente, sensores adicionais, modos de operação, controle remoto e proteção contra subtensão.

## Estrutura do repositório

```
trainee-2026-1/
├── README.md
├── Desafio Trainee Telemetria 2026_1.pdf       # Enunciado do desafio
└── Esquemático circuito trainees 2026_1.pdf    # Esquemático do protótipo (Tinkercad)
```

## Próximos passos

Para dar continuidade ao projeto:

1. **Migrar o protótipo para ESP32**, adaptando pinagem, níveis de tensão (3,3 V) e uso de PWM.
2. **Montar o circuito físico** e integrá-lo ao mini-barco, garantindo alimentação estável e acionamento seguro do motor.
3. **Implementar o envio de dados via Wi-Fi** (HTTP) a partir do ESP32.
4. **Desenvolver o servidor** (HTTP + Socket.IO) com banco de dados para persistência.
5. **Criar a página web em TypeScript**, com temperatura, posição do acelerador, status do sistema e gráficos em tempo real.
6. **Realizar a integração final** e os testes práticos no mini-barco.

## Referências

- [HTTP – MDN Web Docs](https://developer.mozilla.org/pt-BR/docs/Web/HTTP)
- [Socket.IO](http://socket.io)
- [Capacitação em Desenvolvimento Web (YouTube)](https://youtube.com/watch?v=7ItQiJ0FrWo)
- [Tinkercad Circuits](https://www.tinkercad.com/circuits)
