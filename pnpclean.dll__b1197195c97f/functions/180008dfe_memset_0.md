# memset_0

- ea: `0x180008dfe`
- end: `0x180008e04`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180003d70`
- `0x180004c14`
- `0x180004e74`
- `0x1800058a0`
- `0x180005bd0`
- `0x180006644`
- `0x180006dc4`
- `0x180007498`
- `0x180007560`
- `0x180007680`
- `0x180007c00`
- `0x180007dec`
- `0x180008438`
- `0x180008b98`

## import_xrefs

- `msvcrt!memset` at `0x180008dfe`

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
0x180008dfe  jmp     cs:__imp_memset
```
