
Попробуйте запустить код:

```js run
let str = "Привет";

str.test = 5; // (*)

alert(str.test);
```

В зависимости от того, используете ли вы cтрогий режим (`use strict`) или нет, результат может быть:
1. `undefined` (без strict)
2. Ошибка (strict mode)

Почему? Давайте посмотрим что происходит в строке кода, отмеченной `(*)`:

1. В момент обращения к свойству `str` создается "объект-обертка".
2. В cтрогом режиме, попытка изменения этого объекта выдает ошибку.
3. В стандартном режиме, операция продолжается, объект получает свойство `test`, но после этого "объект-обертка" удаляется.

Выходит, в стандартном режиме на последней линии `str` больше не имеет свойства `test`.

**Данный пример наглядно показывает, что примитивы не являются объектами.**

Они не могут хранить дополнительные данные.
