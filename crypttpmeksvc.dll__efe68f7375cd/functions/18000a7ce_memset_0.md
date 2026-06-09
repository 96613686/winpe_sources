# memset_0

- ea: `0x18000a7ce`
- end: `0x18000a7d4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180001140`
- `0x180001480`
- `0x1800030f0`
- `0x180007d80`
- `0x180007e24`
- `0x180008174`
- `0x1800089e8`
- `0x180008b50`

## import_xrefs

- `msvcrt!memset` at `0x18000a7ce`

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
0x18000a7ce  jmp     cs:__imp_memset
```
