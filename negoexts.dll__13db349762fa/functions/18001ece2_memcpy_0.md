# memcpy_0

- ea: `0x18001ece2`
- end: `0x18001ece8`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `33`
- callee_count: `0`
- tags: ``

## callers

- `0x1800011b4`
- `0x180001414`
- `0x180002470`
- `0x180002694`
- `0x180002970`
- `0x180002e00`
- `0x180003a10`
- `0x180004404`
- `0x180005bc0`
- `0x180006650`
- `0x18000676c`
- `0x180006a48`
- `0x1800070d0`
- `0x180008e60`
- `0x180009c98`
- `0x18000a29c`
- `0x18000b8d0`
- `0x18000bc0c`
- `0x18000d388`
- `0x18000ec9c`
- `0x180016824`
- `0x180016f70`
- `0x180017b60`
- `0x180018f28`
- `0x18001a020`
- `0x18001a3b4`
- `0x18001b9b0`
- `0x18001bba4`
- `0x18001d71c`
- `0x18001d92c`
- `0x18001db40`
- `0x18001e2b4`
- `0x18001e5f0`

## import_xrefs

- `msvcrt!memcpy` at `0x18001ece2`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy_0(void *a1, const void *Src, size_t Size)
{
  return memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x18001ece2  jmp     cs:__imp_memcpy
```
