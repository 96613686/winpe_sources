# memset_0

- ea: `0x18000ac8e`
- end: `0x18000ac94`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1800052c0`
- `0x180005370`
- `0x180005464`
- `0x180006684`
- `0x1800075a8`
- `0x1800076cc`
- `0x1800088a0`
- `0x180008ac8`
- `0x1800097a0`
- `0x180009c88`
- `0x18000a168`

## import_xrefs

- `msvcrt!memset` at `0x18000ac8e`

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
0x18000ac8e  jmp     cs:__imp_memset
```
