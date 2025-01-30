# Взаимодействие микросервисов: Практические примеры

В данном репозитории собраны примеры различных способов взаимодействия микросервисов.

---

## 📌 Доступные реализации

### 1️⃣ Взаимодействие через Apache Kafka
[![Kafka Interaction](https://github-readme-stats.vercel.app/api/pin/?username=srBob01&repo=services-interaction-kafka&show_owner=true)](https://github.com/srBob01/services-interaction-kafka)

🔹 **Описание:**
- Взаимодействие микросервисов через **Kafka**.
- **Producer** публикует сообщения в Kafka, **Consumer** их обрабатывает и отправляет email-уведомления.
- PostgreSQL хранит товары и владельцев.
- Тестирование email-уведомлений через MailHog.

🛠 **Технологии:** Spring Boot, Kafka, PostgreSQL, MailHog, Docker Compose.

📌 **Где используется?**
- Когда требуется **асинхронная обработка событий**.
- Для **разделения нагрузки** между несколькими сервисами.
- В системах с **высокой доступностью и отказоустойчивостью**.

---

### 2️⃣ Взаимодействие через RabbitMQ
[![RabbitMQ Interaction](https://github-readme-stats.vercel.app/api/pin/?username=srBob01&repo=services-interaction-rabbit&show_owner=true)](https://github.com/srBob01/services-interaction-rabbit)

🔹 **Описание:**
- Аналогичный пример, но с использованием **RabbitMQ** вместо Kafka.
- Реализация **асинхронного взаимодействия** через очереди сообщений.
- **Producer** отправляет события, **Consumer** их обрабатывает и выполняет бизнес-логику.

🛠 **Технологии:** Spring Boot, RabbitMQ, PostgreSQL, Docker Compose.

📌 **Где используется?**
- Когда требуется **надежная доставка сообщений**.
- В **разграниченных доменах**, где разные сервисы работают независимо.
- В системах, где важен **гибкий механизм маршрутизации сообщений**.

---

### 3️⃣ Взаимодействие через WebClient (синхронный и асинхронный REST)
[![WebClient Interaction](https://github-readme-stats.vercel.app/api/pin/?username=srBob01&repo=services-interaction-web-client&show_owner=true)](https://github.com/srBob01/services-interaction-web-client)

🔹 **Описание:**
- Реализация **синхронного** и **асинхронного** взаимодействия микросервисов через **Spring WebClient**.
- **Синхронный клиент** блокирует поток до получения ответа.
- **Асинхронный клиент** продолжает выполнение и получает ответ через callback.

🛠 **Технологии:** Spring Boot, WebClient.

📌 **Где используется?**
- **Синхронный подход** подходит для **простых API-запросов**.
- **Асинхронный подход** полезен, когда важна **производительность и масштабируемость**.
- При работе с **внешними API**, где ожидание может быть долгим.

---

### 4️⃣ Взаимодействие через RestTemplate
[![RestTemplate Interaction](https://github-readme-stats.vercel.app/api/pin/?username=srBob01&repo=services-interaction-rest-template&show_owner=true)](https://github.com/srBob01/services-interaction-rest-template)

🔹 **Описание:**
- **Синхронное** взаимодействие через **Spring RestTemplate**.
- **RestClient** отправляет HTTP-запрос к **RestServer**.
- Сервер обрабатывает запрос и возвращает ответ.

🛠 **Технологии:** Spring Boot, RestTemplate.

📌 **Где используется?**
- Для **простых API-запросов**, где не нужна асинхронность.
- В системах с **предсказуемыми задержками**.
- В интеграции с **внешними REST API**.

---

### 5️⃣ Взаимодействие через WebSocket
[![WebSocket Interaction](https://github-readme-stats.vercel.app/api/pin/?username=srBob01&repo=services-interaction-websocket&show_owner=true)](https://github.com/srBob01/services-interaction-websocket)

🔹 **Описание:**
- Реализация **чата на WebSocket** с использованием протокола **STOMP**.
- Клиенты могут отправлять сообщения в реальном времени.
- Сервер ретранслирует их всем подписанным клиентам.

🛠 **Технологии:** Spring Boot, WebSocket, STOMP, SockJS.

📌 **Где используется?**
- Для **чата и push-уведомлений**.
- В **интерактивных веб-приложениях** (биржи, игровые серверы).
- В системах с **низкой задержкой**.

---

### 6️⃣ Взаимодействие через gRPC
[![gRPC Interaction](https://github-readme-stats.vercel.app/api/pin/?username=srBob01&repo=services-interaction-grpc&show_owner=true)](https://github.com/srBob01/services-interaction-grpc)

🔹 **Описание:**
- Взаимодействие через **gRPC**, использующее Protocol Buffers.
- Клиент отправляет запрос на сервер с именем и списком хобби.
- Сервер отвечает потоком сообщений (стриминг).

🛠 **Технологии:** gRPC, Protocol Buffers, Spring Boot.

📌 **Где используется?**
- Когда важна **высокая производительность**.
- В **распределённых системах**, работающих на разных языках программирования.
- Для **высоконагруженных сервисов**, где важна **низкая задержка**.

---

## 🚀 Итог

| Метод | Тип взаимодействия | Когда использовать? |
|--------|------------------|----------------------|
| **Kafka** | Асинхронный, события | Высокая нагрузка, отказоустойчивость |
| **RabbitMQ** | Асинхронный, очереди | Гибкая маршрутизация сообщений |
| **WebClient** | Синхронный/Асинхронный REST | API-запросы, интеграции |
| **RestTemplate** | Синхронный REST | Простые HTTP-запросы |
| **WebSocket** | Двусторонняя связь | Чат, уведомления, real-time данные |
| **gRPC** | Высокопроизводительное API | Распределённые системы |

