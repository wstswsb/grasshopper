# Кузнечик (Криптографический Алгоритм)

## Описание проекта

Этот проект представляет собой реализацию криптографического алгоритма "Кузнечик" (GOST
R 34.12-2018),
который является национальным стандартом симметричного шифрования Российской Федерации.
Алгоритм используется для обеспечения конфиденциальности данных и обладает высокой
степенью стойкости к криптоанализу.

## Структура проекта

- `grassnechik/` - Исходный код реализации алгоритма Кузнечик.
- `tests/` - Набор тестов для проверки корректности реализации.
- `README.md` - Текущий файл README.

## Требования

- Python 3.12+

## Использование

### Пример шифрования и дешифрования

```python
import binascii

from grassnechik import Key, Grassnechik

message: list[int] = list(binascii.unhexlify("1122334455667700ffeeddccbbaa9988"))
key = Key.from_iterable(
    binascii.unhexlify(
        "8899aabbccddeeff0011223344556677"
        "fedcba98765432100123456789abcdef"
    )
)

encrypted: tuple[int, ...] = Grassnechik(key).encrypt(tuple(message))
decrypted: tuple[int, ...] = Grassnechik(key).decrypt(encrypted)
```

## Тестирование

Для запуска тестов выполните следующую команду:

```sh
pytest tests/
```

## Лицензия

Этот проект лицензирован под MIT License. Подробности можно найти в файле LICENSE.

---

Спасибо за использование проекта!