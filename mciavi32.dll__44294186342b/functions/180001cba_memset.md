# memset

- ea: `0x180001cba`
- end: `0x180001cc0`
- name: `memset`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180006f50`
- `0x18000ae48`
- `0x18000b0d8`
- `0x18000b840`
- `0x18000d6bc`
- `0x18000db04`
- `0x18000fce0`
- `0x180010cd4`
- `0x1800112a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180001cba`

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
0x180001cba  jmp     cs:__imp_memset
```
