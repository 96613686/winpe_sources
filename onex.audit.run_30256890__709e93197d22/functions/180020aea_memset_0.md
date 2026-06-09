# memset_0

- ea: `0x180020aea`
- end: `0x180020af0`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180006160`
- `0x180006bd0`
- `0x180010710`
- `0x180010f20`
- `0x180015f90`
- `0x18001ac0c`
- `0x18001ad40`
- `0x18001dd84`
- `0x18001ede0`
- `0x18001f690`
- `0x180022c30`
- `0x180028e18`
- `0x18002a22c`
- `0x18002ec50`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180020aea`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset_0(void *a1, int Val, size_t Size)
{
  return memset(a1, Val, Size);
}

```

## disassembly

```asm
0x180020aea  jmp     cs:__imp_memset
```
