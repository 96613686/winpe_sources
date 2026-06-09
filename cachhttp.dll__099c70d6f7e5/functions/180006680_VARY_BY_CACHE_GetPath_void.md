# VARY_BY_CACHE::GetPath(void *)

- ea: `0x180006680`
- end: `0x18000668b`
- name: `?GetPath@VARY_BY_CACHE@@UEAAPEBGPEAX@Z`
- size: `11`
- prototype: `const unsigned __int16 *__fastcall(VARY_BY_CACHE *__hidden this, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180006684`

## pseudocode

```c
const unsigned __int16 *__fastcall VARY_BY_CACHE::GetPath(VARY_BY_CACHE *this, char *a2)
{
  return STRU::QueryStr((STRU *)(a2 + 24));
}

```

## disassembly

```asm
0x180006680  lea     rcx, [rdx+18h]
0x180006684  jmp     cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
```
