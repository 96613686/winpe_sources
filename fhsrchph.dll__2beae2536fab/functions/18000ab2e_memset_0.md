# memset_0

- ea: `0x18000ab2e`
- end: `0x18000ab34`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800037ac`
- `0x180007dac`
- `0x18000a824`

## import_xrefs

- `msvcrt!memset` at `0x18000ab2e`

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
0x18000ab2e  jmp     cs:__imp_memset
```
