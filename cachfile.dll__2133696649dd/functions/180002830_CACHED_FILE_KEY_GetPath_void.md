# CACHED_FILE_KEY::GetPath(void)

- ea: `0x180002830`
- end: `0x18000283b`
- name: `?GetPath@CACHED_FILE_KEY@@UEBAPEBGXZ`
- size: `11`
- prototype: `const unsigned __int16 *__fastcall(CACHED_FILE_KEY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180002834`

## pseudocode

```c
const unsigned __int16 *__fastcall CACHED_FILE_KEY::GetPath(CACHED_FILE_KEY *this)
{
  return STRU::QueryStr((CACHED_FILE_KEY *)((char *)this + 8));
}

```

## disassembly

```asm
0x180002830  add     rcx, 8
0x180002834  jmp     cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
```
