# memset

- ea: `0x1800023aa`
- end: `0x1800023b0`
- name: `memset`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180002f78`
- `0x180004bac`
- `0x180005c28`
- `0x18001b1e8`
- `0x180023820`
- `0x180023fb0`
- `0x180027b60`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x1800023aa`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  return __imp_memset(a1, Val, Size);
}

```

## disassembly

```asm
0x1800023aa  jmp     cs:__imp_memset
```
