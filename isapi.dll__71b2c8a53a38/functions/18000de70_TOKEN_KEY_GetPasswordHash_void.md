# TOKEN_KEY::GetPasswordHash(void)

- ea: `0x18000de70`
- end: `0x18000de7b`
- name: `?GetPasswordHash@TOKEN_KEY@@UEBAPEBGXZ`
- size: `11`
- prototype: `const unsigned __int16 *__fastcall(TOKEN_KEY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000de74`

## pseudocode

```c
const unsigned __int16 *__fastcall TOKEN_KEY::GetPasswordHash(TOKEN_KEY *this)
{
  return STRU::QueryStr((TOKEN_KEY *)((char *)this + 64));
}

```

## disassembly

```asm
0x18000de70  add     rcx, 40h ; '@'
0x18000de74  jmp     cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
```
