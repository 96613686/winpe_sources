# memset_0

- ea: `0x18000b0ce`
- end: `0x18000b0d4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180004bd8`
- `0x180005244`
- `0x180005778`
- `0x180005d70`
- `0x18000688c`
- `0x180006c58`
- `0x180008ff4`
- `0x180009020`
- `0x18000929c`
- `0x180009918`
- `0x18000ab44`

## import_xrefs

- `msvcrt!memset` at `0x18000b0ce`

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
0x18000b0ce  jmp     cs:__imp_memset
```
