# Домашнее задание к занятию "13.Системы мониторинга"
#

1. Вас пригласили настроить мониторинг на проект. На онбординге вам рассказали, что проект представляет из себя 
платформу для вычислений с выдачей текстовых отчетов, которые сохраняются на диск. Взаимодействие с платформой 
осуществляется по протоколу http. Также вам отметили, что вычисления загружают ЦПУ. Какой минимальный набор метрик вы
выведите в мониторинг и почему?

> > >__Ответ:__ _Думаю что нужно добавить метрику связаную с временем ответа http, ошибки http запросов и CPU usage. Также, можно добавить сбор утилизации оперативной памяти и свободного места на диске._
#
2. Менеджер продукта посмотрев на ваши метрики сказал, что ему непонятно что такое RAM/inodes/CPUla. Также он сказал, что хочет понимать, насколько мы выполняем свои обязанности перед клиентами и какое качество обслуживания. Что вы можете ему предложить?
> > >__Ответ:__ _Можно предложить обсудить с клиентом введение целевые показатели SLO, SLA, SLI_
#
3. Вашей DevOps команде в этом году не выделили финансирование на построение системы сбора логов. Разработчики в свою очередь хотят видеть все ошибки, которые выдают их приложения. Какое решение вы можете предпринять в этой ситуации, чтобы разработчики получали ошибки приложения?
> > >__Ответ:__ _Можно предложить использование перехватчика ошибок Sentry_
#
4. Вы, как опытный SRE, сделали мониторинг, куда вывели отображения выполнения SLA=99% по http кодам ответов. 
Вычисляете этот параметр по следующей формуле: summ_2xx_requests/summ_all_requests. Данный параметр не поднимается выше 
70%, но при этом в вашей системе нет кодов ответа 5xx и 4xx. Где у вас ошибка?
> > >__Ответ:__ _формула расчета должна быть (summ_2xx_requests + summ_3xx_requests)/summ_all_requests_
#
5. Опишите основные плюсы и минусы pull и push систем мониторинга.
> > >__Ответ:__ _pull плюсы: лекго контролировать подлинность данных, возможность единого прокси для агентос с TLS, упрощенная отладка получения данных с агентов ; push плюсы: упрощение репликации данных, гибкая настройка отправки пакетов, менее затратный способ передачи данных UDP; push минусы: страдает гарантия доставки пакетов_

#
6. Какие из ниже перечисленных систем относятся к push модели, а какие к pull? А может есть гибридные?

    - Prometheus 
    - TICK
    - Zabbix
    - VictoriaMetrics
    - Nagios
> > >__Ответ:__ 
>>>>_Prometheus_ - pull

>>>>_TICK_ - push

>>>>_Zabbix_ - push, pull

>>>>_VictoriaMetrics_ - push, pull

>>>>_Nagios_ - pull

#
7. Cкриншот с отображением метрик утилизации места на диске (disk->host->telegraf_container_id) из веб-интерфейса.
![07](/images/01.png)

#
8.  Cкриншот c метриками связаными с docker в веб-интерфейсе базы telegraf.autogen.
![08](/images/02.png)
