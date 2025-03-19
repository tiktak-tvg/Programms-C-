# ROBOCOPY
Robocopy (от англ. Robust File Copy) — утилита командной строки для репликации (не просто копирования) каталогов (папок).

Программа RobocopyFile.exe на C#  

C:\Users\sol>robocopy /?

-------------------------------------------------------------------------------
   ROBOCOPY     ::     Robust File Copy for Windows
-------------------------------------------------------------------------------

              Применение :: ROBOCOPY источник назначение [файл [файл]...]
                            [Параметры]

                 Источник:: Исходная папка (диск:\путь или
                            \\сервер\общий ресурс\путь).
              Назначение :: Конечная папка (диск:\путь или
                            \\сервер\общий ресурс\путь).
                    Файл :: Копировать файлы   (имена и подстановочные знаки:
                            по умолчанию "*.*").


Параметры копирования:

                      /S :: Копировать вложенные папки, кроме пустых.
                      /E :: Копировать вложенные папки, включая пустые.
                  /LEV:n :: Копировать только верхние n уровней исходного
                            дерева папок.

                      /Z :: Копирование файлов с возобновлением.
                      /B :: Копирование файлов в режиме архивирования.
                     /ZB :: Используется режим с возобновлением; если доступ
                            запрещен, используется режим архивации.
                      /J :: Копирование с использованием небуферизованного
                            ввода-вывода (рекомендуется для больших файлов).
                 /EFSRAW :: Копирование всех зашифрованных файлов в режиме
                            EFS RAW.
                   /COPY :: флаги копирования
                      
 Что копируется для файлов (по умолчанию /COPY:DAT).<br>
                       (флаги копирования: D=данные, A=атрибуты, T=метки времени, X=пропускать альтернативные потоки данных).<br>
                            (S=Безопасность=NTFS ACLs, O=Сведения о владельце, U=Сведения аудита).


                    /SEC :: Копировать файлы с параметрами безопасности
                            (эквивалентно /COPY:DATS).
                /COPYALL :: Копировать все сведения о файле (эквивалентно
                            /COPY:DATSOU).
                 /NOCOPY :: Не копировать никаких сведений о файле
                            (полезно с параметром /PURGE).
                 /SECFIX :: Исправлять параметры безопасности для всех файлов,
                            даже пропущенных.
                 /TIMFIX :: Исправлять атрибуты времени для всех файлов,
                            даже пропущенных.

                  /PURGE :: Удалять файлы и папки назначения, которых больше
                            не существует в источнике.
                    /MIR :: Создать зеркало дерева папок
                            (эквивалентно /E  с /PURGE).

                    /MOV :: Перемещать файлы (удаление из источника после
                            копирования).
                   /MOVE :: Перемещать файлы и папки (удаление из источника
                            после копирования).

          /A+:[RASHCNET] :: Добавлять заданные атрибуты скопированным файлам.
          /A+:[RASHCNET] :: Удалять заданные атрибуты из скопированных файлов.

                 /CREATE :: Создать только дерево папок и файлы нулевой длины.
                    /FAT :: Создать файлы назначения только в формате 8.3 FAT.
                    /256 :: Отключить поддержку длинных путей ( > 256 знаков).

                  /MON:n :: Наблюдать за источником; перезапустить после
                            n изменений.
                  /MOT:m :: Наблюдать за источником; перезапустить через m
                            минут, если произошли изменения.

           /RH:hhmm-hhmm :: Часы запуска — время, когда можно запускать новое
                            копирование.
                     /PF :: Проверять часы запуска по файлам (не по проходам).

                  /IPG:n :: Интервал между пакетами (мс) для снижения нагрузки
                            на сеть при низкоскоростных подключениях.

                /SJ :: копировать соединения как соединения, а не как целевые объекты соединений.
                /SL :: копировать символические ссылки как ссылки, а не как целевые объекты ссылок.

                 /MT[:n] :: Выполнить многопотоковое копирование с помощью n потоков (по умолчанию 8).
                            n должно быть не меньше 1 и не больше 128.
                            Этот параметр несовместим с параметрами /IPG и /EFSRAW.
                       Перенаправляйте выходные данные с помощью параметра /LOG, чтобы повысить производительность.

                  /DCOPY :: флаги копирования  
                  
Что копировать для каталогов (по умолчанию /DCOPY:DA).<br>
                       (флаги копирования: D=данные, A=атрибуты, T=метки времени, E=расширенные атрибуты, X=пропускать альтернативные потоки данных).

                /NODCOPY :: Не копировать никаких сведений о каталоге
                            (по умолчанию выполняется /DCOPY:DA).

              /NOOFFLOAD :: Копирование файлов без использования механизма
                            разгрузки копий Windows.

          /COMPRESS:: запрашивать сетевое сжатие во время передачи файла, если применимо.
 
Параметры выбора файлов:

                      /A :: Копировать только файлы с установленным атрибутом
                            "Архивный".
                      /M :: Копировать только файлы с атрибутом "Архивный" и
                            сбросить его.
         /IA:[RASHCNETO] :: Включить файлы, у которых установлен какой-либо из
                            заданных атрибутов.
         /XA:[RASHCNETO] :: Исключить файлы, у которых установлен какой-либо из
                            заданных атрибутов.

      /XF file [файл]... :: Исключить файлы, соответствующие заданным именам,
                            путям и подстановочным знакам.
     /XD dirs [папки]... :: Исключить папки, соответствующие заданным именам
                            и путям.

                     /XC :: Исключить измененные файлы.
                     /XN :: Исключить более поздние файлы.
                     /XO :: Исключить более ранние файлы.
                     /XX :: Исключить дополнительные файлы и папки.
                     /XL :: Исключить отдельно расположенные файлы и папки.
                     /IS :: Включить те же файлы.
                     /IT :: Включить оптимизированные файлы.

                  /MAX:n :: Максимальный размер файла — исключить файлы,
                            размер которых более n байт.
                  /MIN:n :: Минимальный размер файла — исключить файлы,
                            размер которых менее n байт.

               /MAXAGE:n :: Максимальный возраст файла — исключить файлы,
                            возраст которых превышает n дней.
               /MINAGE:n :: Минимальный возраст файла — исключить файлы,
                            возраст которых менее n дней.
               /MAXLAD:n :: Наиболее поздняя дата последнего обращения —
                            исключить файлы, которые не использовались
                            с даты n.
               /MINLAD:n :: Наиболее ранняя дата последнего обращения —
                            исключить файлы, которые использовались после
                            даты n.
                            (Если n < 1900, то n = n дней, в противном случае
                            n — дата в формате ДДММГГГГ).

               /FFT :: использовать время файлов FAT (двухсекундная точность).
               /DST :: учитывать одночасовую разницу при переходе на летнее время.

                /XJ :: исключить символьные ссылки (для файлов и каталогов) и точки соединения.
               /XJD :: исключить символические ссылки для каталогов и точки соединения.
               /XJF :: исключить символические ссылки для файлов.

                /IM :: Включение измененных файлов (отличающееся время изменения).

Параметры повторных попыток:

                    /R:n :: Число повторных попыток для неудавшихся копий:
                            по умолчанию — 1 миллион.
                    /W:n :: Время ожидания между повторными попытками:
                            по умолчанию — 30 секунд.

                    /REG :: Сохранить /R:n и /W:n в реестре как параметры
                            по умолчанию.

                    /TBD :: Ждать, пока будут определены имена общих ресурсов (ошибка повторной попытки 67).


               /LFSM :: работать в режиме нехватки свободного места, включая паузу и возобновление копирования (см. примечания).

               /LFSM:n[KMG] :: /LFSM, задающий размер основания в n [К: кило, М: мега, Г: гига] байт.


Параметры ведения журнала:

                      /L :: Только список — файлы не копируются, не удаляются,
                            не помечаются метками времени.
                      /X :: Сообщать обо всех дополнительных файлах, а не
                            только о выбранных.
                      /V :: Подробный вывод с указанием пропущенных файлов.
                     /TS :: Включать в вывод метки времени исходных файлов.
                     /FP :: Включать в вывод полные пути файлов.
                  /BYTES :: Печатать размеры в байтах.

                     /NS :: Без размера - не заносить в журнал размер файлов.
                     /NC :: Без класса - не заносить в журнал классы файлов.
                    /NFL :: Без списка файлов - не заносить в журнал
                            имена файлов.
                    /NDL :: Без списка папок - не заносить в журнал
                            имена папок.

                     /NP :: Без хода процесса — не отображать число
                            скопированных процентов.
                    /ETA :: Показывать оценку времени окончания
                            копирования файлов.

               /LOG:файл :: Записывать состояние в файл журнала (перезаписывать
                            существующий журнал).
              /LOG+:файл :: Записывать состояние в файл журнала (добавлять к
                            существующему журналу).

            /UNILOG:файл :: Записывать состояние в файл журнала в формате
                            Юникод (перезаписывать существующий журнал).
           /UNILOG+:файл :: Записывать состояние в файл журнала в формате
                            Юникод (добавлять к существующему журналу).

                    /TEE :: Направлять выходные данные в окно консоли и в файл
                            журнала.

                    /NJH :: Без заголовка задания.
                    /NJS :: Без сведений о задании.

                /UNICODE :: Cостояние вывода в формате Юникод.


Параметры задания:

        /JOB:имя_задания :: Взять параметры из указанного файла задания.
       /SAVE:имя_задания :: Сохранить параметры в указанный файл задания
                   /QUIT :: Выйти после обработки командной строки
                            (для просмотра параметров).
                   /NOSD :: Не указывается исходная папка.
                   /NODD :: Не указывается папка назначения.
                     /IF :: Включить следующие файлы.


Комментарии:

       Использование /PURGE или /MIR в корневом каталоге тома ранее приводило к тому, что
       команда robocopy применяла запрошенную операцию к файлам внутри каталога
       Volume Information также. Сейчас это не так; если
       задан какой-либо из этих параметров, команда robocopy будет пропускать все файлы или каталоги с этим
       именем в исходных и целевых каталогах верхнего уровня данного сеанса копирования.

       Классификация измененных файлов применяется, только если исходная
       и конечная файловые системы поддерживают метки времени изменения (например, NTFS)
       и у исходных и конечных файлов различно только время
       изменения. Эти файлы не копируются по умолчанию. Укажите параметр /IM,
       для их включения.

       Флаг /DCOPY:E требует копирования расширенных атрибутов
       для каталогов. Обратите внимание: команда robocopy продолжит выполняться,
       если не удастся скопировать расширенные атрибуты каталога. Этот флаг не включен
       в /COPYALL.

       Использование /LFSM требует, чтобы команда robocopy работала в "режиме нехватки свободного места".
       В этом режиме команда robocopy будет приостановлена, когда копирование файла вызовет
       свободное место на конечном томе опустится ниже значения "floor", которое
       может быть явно задано формой флага LFSM:n[KMG].
       Если значение /LFSM указано без явного значения floor, то для параметра floor задается значение
       десять процентов от размера конечного тома.
       Режим нехватки свободного места несовместим с /MT, /EFSRAW, /B и /ZB.
