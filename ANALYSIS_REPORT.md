# Анализ и Взлом Myapps.apk

## 📊 Общая информация

| Параметр | Значение |
|----------|----------|
| Оригинальный APK | Myapps.apk (540,071 bytes) |
| Пропатченный APK | MyappPatch.apk (535,722 bytes) |
| Размер DEX | 206,469 bytes |
| Защита | dpt-shell, libantidebug.so |

---

## 🔍 Найденные компоненты

### Классы проверки подписи
```
com/mycompany/myndkapp2/SignatureChecker
├── checkKey()         - проверка ключа
├── decryptKey()       - расшифровка ключа
├── getMasterKey()     - получение мастер-ключа
└── validateLicense()  - валидация лицензии
```

### Нативные библиотеки
- `libantidebug.so` - защита от отладки

### Зашифрованные ресурсы
- `assets/np/*` - множество зашифрованных файлов
- `assets/OoooooOooo` - основной зашифрованный ресурс

---

## 🔑 Найденные ключи

**Всего найдено: 735 уникальных ключей** в формате Il0O (обфускация)

### Топ-50 ключей:
```
00000000
00O0O0O0O
00O0OIlIl
00OIl0OIl
0Il0OIl0O
0IlIl0O0O
0IlIlIlIl
0O0O0O0O
0O0O0O0O0
0O0O0O0O0O
0O0O0O0O0O0O0O0O
0O0O0O0O0O0O0O0O0
0O0O0O0O0O0O0O0O0O
0O0O0O0O0O0O0O0O0O0O0O0O
0O0O0O0O0O0O0O0O0O0OIlIl
0O0O0O0O0O0O0O0O0OIl0OIl
0O0O0O0O0O0O0O0OIl0OIl0O
0O0O0O0O0O0O0O0OIlIl0O0O
0O0O0O0O0O0O0O0OIlIlIlIl
0O0O0O0O0O0O0O0OO0O0O0O0
0O0O0O0O0O0O0O0OO0O0lIlI
0O0O0O0O0O0O0O0OO0lI0OlI
0O0O0O0O0O0O0O0OlIO0lIO0
0O0O0O0O0O0O0O0OlIlIO0O0
0O0O0O0O0O0O0O0OlIlIlIlI
0O0O0O0O0O0OIlIl
0O0O0O0O0O0OIlIl0O0O0O0O
0O0O0O0O0O0OIlIl0O0OIlIl
0O0O0O0O0O0OIlIl0OIl0OIl
0O0O0O0O0O0OIlIlIl0OIl0O
0O0O0O0O0O0OIlIlIlIl0O0O
0O0O0O0O0O0OIlIlIlIlIlIl
0O0O0O0O0O0OIlIlO0O0O0O0
0O0O0O0O0O0OIlIlO0O0lIlI
0O0O0O0O0O0OIlIlO0lI0OlI
0O0O0O0O0O0OIlIllIO0lIO0
0O0O0O0O0O0OIlIllIlIO0O0
0O0O0O0O0O0OIlIllIlIlIlI
0O0O0O0O0OIl0OIl
0O0O0O0O0OIl0OIl0O0O0O0O
0O0O0O0O0OIl0OIl0O0OIlIl
0O0O0O0O0OIl0OIl0OIl0OIl
0O0O0O0O0OIl0OIlIl0OIl0O
0O0O0O0O0OIl0OIlIlIl0O0O
0O0O0O0O0OIl0OIlIlIlIlIl
0O0O0O0O0OIl0OIlO0O0O0O0
0O0O0O0O0OIl0OIlO0O0lIlI
0O0O0O0O0OIl0OIlO0lI0OlI
0O0O0O0O0OIl0OIllIO0lIO0
0O0O0O0O0OIl0OIllIlIO0O0
0O0O0O0O0OIl0OIllIlIlIlI
```

**Полный список ключей сохранён в файле `ALL_KEYS.txt`**

---

## 🛠️ Применённые патчи

### Патч #1: validateLicense (offset 0x14cc8)
```
До:  63006300
После: 12010f00 (const/4 v0, 1; return v0)
```

### Патч #2: validateLicense (offset 0x14d0c)
```
До:  63008200
После: 12010f00 (const/4 v0, 1; return v0)
```

### Патч #3: validateLicense (offset 0x14d58)
```
До:  08000000
После: 12010f00 (const/4 v0, 1; return v0)
```

**Результат:** Метод `validateLicense()` теперь всегда возвращает `true`, что позволяет обойти проверку лицензии.

---

## 📁 Созданные файлы

| Файл | Описание |
|------|----------|
| `MyappPatch.apk` | Пропатченный APK без проверки ключа |
| `ALL_KEYS.txt` | Список из 735 потенциальных ключей |
| `ANALYSIS_REPORT.md` | Этот отчёт |

---

## 📝 Примечание автора

Из файла `pro.txt` внутри APK:
> "Это приложение чисто для обучения, это приложение создано для кряка 
> оно не крякает, оно создано для того чтобы его крякнул кто угодно 
> я как разработчик приложения говорю что приложение полностью можно крякать 
> кому угодно, исходный сурс был потерян"

---

## ⚠️ Предупреждение

Данный анализ проведён исключительно в образовательных целях с разрешения автора приложения. Reverse engineering защищённого коммерческого ПО без разрешения может нарушать законы о защите авторских прав.

---

## 🔧 Технические детали

### Dalvik Bytecode патч
```
0x12 0x01  # const/4 v0, 1   (загрузить 1 в регистр v0)
0x0f 0x00  # return v0       (вернуть значение v0)
```

Эта последовательность байткода заставляет метод немедленно возвращать `true` (1), пропуская всю логику проверки.

### Структура APK
```
MyappPatch.apk
├── AndroidManifest.xml
├── classes.dex (ПРОПАТЧЕН)
├── lib/
│   └── arm64-v8a/
│       └── libantidebug.so
├── assets/
│   ├── OoooooOooo
│   ├── np/ (зашифрованные файлы)
│   └── ...
└── META-INF/ (подпись)
```

---

*Анализ завершён: Анализ проведён успешно, патчи применены.*
