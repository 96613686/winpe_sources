# TOKEN_KEY::GetUserNameW(void)

- ea: `0x1800034a0`
- end: `0x1800034ab`
- name: `?GetUserNameW@TOKEN_KEY@@UEBAPEBGXZ`
- size: `11`
- prototype: `const unsigned __int16 *__fastcall(TOKEN_KEY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800034a4`

## pseudocode

```c
const unsigned __int16 *__fastcall TOKEN_KEY::GetUserNameW(TOKEN_KEY *this)
{
  return STRU::QueryStr((TOKEN_KEY *)((char *)this + 8));
}

```

## disassembly

```asm
0x1800034a0  add     rcx, 8
0x1800034a4  jmp     cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
```
