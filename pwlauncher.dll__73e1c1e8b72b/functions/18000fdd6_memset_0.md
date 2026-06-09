# memset_0

- ea: `0x18000fdd6`
- end: `0x18000fddc`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180002b3c`
- `0x180005c98`
- `0x1800070ec`
- `0x1800077f8`
- `0x180007e74`
- `0x180008488`
- `0x180008900`
- `0x180009360`
- `0x18000946c`
- `0x18000aed8`
- `0x18000de18`

## import_xrefs

- `msvcrt!memset` at `0x18000fdd6`

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
0x18000fdd6  jmp     cs:__imp_memset
```
