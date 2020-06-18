# Функциональные спецификации проекта "Кекеке"

## Общие требования

Проект должен быть написан на языке Typescript версии не ниже 3.9.2 с использованием строго режима.

## Модуль лексического анализатора

```typescript
export type Keyword = "break" |"char" |"else" | "if" | "for" | "int" | "return" | "void" | "while" | "sizeof";

export type Token = {
    type: "keyword",
    keyword: Keyword
} | {
    type: "operator",
    operator: "+" | "-" | "*" | "/" | "%" | "==" | "!="|">"|"<"|"<="|">=" | "&&" | "||" | "!" | "=" |"&" | "|"|"^"|"<<"|">>"|
} | {
    type: "string",
    string: string
} | {
    type: "identifier",
identifier: string,
} | {
    type: "special",
    char: "," | "." | ";" | "{" | "}" | "[" | "]" | "(" | ")"
} | {
    type: "const",
    value: number
}

/** 
 * Returns Token or null if no tokens left
*/
export type ScanFunction = () => Token | null;

export function TokenFactory(file: string): ScanFunction;
```

## Модуль синтаксического анализатора

```typescript
// @TODO
```

## Исполняемый файл

Исполняемый файл импортирует соответствующие функции из модулей и реализовывает программу согласно спецификации
