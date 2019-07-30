Notes
=====

1. Что вызвало сомнения в постановке задачи:
  - направление связи между таблицами trip_service и flight_segment. Предположил обратное.
  - передача названия аэропорта в GET. В реальности ожидал бы airport_id (758) или code (DME). Вынес это в отдельный запрос.
  
2. По оптимизации индексов таблиц под эту конкретную задачу: удалил бы неиспользуемые. 
3. По оптимизации под нагрузку: начал бы с
   - правильной настройки mysql
   - кеширования memcached результатов выборки из БД на фиксированое время (5с).
   Но это в зависимости от объемов, параметров, требований.