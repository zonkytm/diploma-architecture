# Информоционно-аналитическая система технического обслуживания ткацких станков с разработкой подсистемы анализа т состояния тканеобразующих механизмов


## Введение

Система предназначена для автоматизации процессов мониторинга, диагностики и планирования технического обслуживания (ТО) ткацких станков. Она позволяет в режиме реального времени собирать данные с датчиков, анализировать их, прогнозировать неисправности и оптимизировать график ТО. Это повышает надежность оборудования, снижает время простоя и минимизирует эксплуатационные затраты.

---

## Архитектура системы

Система разработана на основе микросервисной архитектуры, что обеспечивает гибкость, масштабируемость и удобство интеграции с существующими информационными системами предприятия. Основные модули системы:

1. **Модуль авторизации**  
   - Управляет состоянием пользователя в системе.
   - Модуль обеспечивает безопасность данных через многоуровневую систему аутентификации и авторизации, а также шифрование передаваемых данных.

2. **Модуль сбора данных**  
   - Взаимодействует с датчиками, установленными на оборудовании.
   - Собирает данные о ключевых параметрах станков (вибрация, температура, скорость и т.д.).
   - Передает данные в модуль обработки для дальнейшего анализа.

3. **Модуль обработки данных**  
   - Выполняет первичную обработку данных (фильтрацию шумов, проверку на ошибки).
   - Выявляет аномалии в параметрах оборудования.
   - Передает обработанные данные в модуль анализа и прогнозирования.

4. **Модуль анализа и прогнозирования**  
   - Анализирует данные с использованием методов машинного обучения, статистического анализа и нечеткой логики.
   - Прогнозирует сроки до следующего ТО.
   - Планирует график ТО с учетом приоритетов.

5. **Модуль управления датчиками и оборудованием**  
   - Регистрирует новые станки и датчики.
   - Настраивает параметры мониторинга для каждого станка.
   - Взаимодействует с базой данных для хранения конфигураций.

6. **Модуль уведомлений**  
   - Информирует сотрудников о необходимости ТО.
   - Уведомляет о завершении ТО.
   - Поддерживает различные каналы связи (email, SMS, push-уведомления).

7. **Модуль управления задачами ТО**  
   - Создает, редактирует и удаляет задачи на техническое обслуживание.
   - Назначает задачи сотрудникам или бригадам.
   - Отслеживает статус выполнения задач.
   - Хранит историю выполненных задач для анализа и отчетности.

8. **Модуль визуализации**  
   - Отображает данные в виде интерактивных графиков и таблиц.
   - Предоставляет доступ к календарю плановых ТО.
---

## Как работает система

### 1. Авторизация пользователя.

Пользователь начинает взаимодействие с системой в состоянии "Неавторизован". После успешной авторизации пользователь переходит в состояние "Авторизован" и начинает работу. Если пользователь делает три неудачные попытки входа, его аккаунт блокируется. По завершении работы сессия закрывается.

### 1. Мониторинг состояния оборудования
Датчики, установленные на ткацких станках, собирают данные о ключевых параметрах:
- Вибрация (ускорение и скорость).
- Температура подшипников.
- Скорость вращения главного вала.
- Энергопотребление.
- Уровень шума.
- Амплитуда качания батана.

Данные передаются в модуль сбора данных, который отправляет их в модуль обработки. После фильтрации и анализа аномалий данные передаются в модуль анализа и прогнозирования.

### 2. Анализ данных
Модуль анализа использует следующие методы:
- **Статистический анализ**: вычисление средних значений, стандартных отклонений и других показателей.
- **Спектральный анализ**: преобразование Фурье для выявления частотных характеристик.
- **Вейвлет-анализ**: детальное исследование временных рядов для выявления локальных изменений.
- **Нечеткая логика**: оценка состояния оборудования на основе экспертных знаний.
- **Машинное обучение**: прогнозирование отказов на основе исторических данных.

На основе анализа система определяет текущее состояние оборудования и прогнозирует возможные неисправности.

### 3. Прогнозирование ТО
Модуль анализа и прогнозирования рассчитывает:
- Время до следующего ТО.
- Приоритетность ТО.

### 4. Управление задачами ТО
Модуль управления задачами позволяет:
- Создавать задачи на основе данных из модуля анализа.
- Назначать задачи ответственным лицам.
- Отслеживать статус выполнения задач в реальном времени.
- Хранить историю выполненных задач для анализа.

### 5. Уведомления
Модуль уведомлений информирует сотрудников о предстоящих ТО через выбранные каналы связи.

---

## Преимущества системы

1. **Прогнозирование поломок**  
   Система позволяет заранее выявлять потенциальные неисправности и планировать ТО, минимизируя простои.

2. **Оптимизация затрат**  
   Благодаря точному прогнозированию ТО снижаются ненужные расходы на преждевременное обслуживание.

3. **Повышение надежности оборудования**  
   Регулярный мониторинг и своевременное устранение дефектов увеличивают срок службы станков.
---

## Требования к системе

### Общие требования
- Интуитивно понятный интерфейс.
- Поддержка русского и английского языков.
- Возможность масштабирования.

### Функциональные требования
- Сбор данных с датчиков в реальном времени.
- Анализ данных и прогнозирование ТО.
- Визуализация данных в виде графиков и таблиц.
- Управление задачами ТО.

### Нефункциональные требования
- Высокая производительность и минимальное время отклика.
- Надежность и доступность 
- Совместимость с современным оборудованием.

---

## Заключение

Разработанная система представляет собой комплексное решение для автоматизации процессов технического обслуживания ткацких станков. Она позволяет повысить эффективность производства, снизить эксплуатационные затраты и минимизировать простои оборудования.

---

## Используемые технологии

- **Языки программирования**: C#, JavaScript.
- **Базы данных**: PostgreSQL, MongoDB.
- **Аналитические инструменты**: MATLAB, TensorFlow, Fuzzy Logic Toolbox.
- **Интерфейс**: React.js.
- **Бэкенд**: ASP.NET