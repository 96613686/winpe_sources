# memset_0

- ea: `0x18000ded2`
- end: `0x18000ded8`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800030ec`
- `0x1800063dc`
- `0x180008194`
- `0x180009250`
- `0x180009924`
- `0x18000a918`
- `0x18000bd1c`
- `0x18000c310`
- `0x18000cf64`

## import_xrefs

- `msvcrt!memset` at `0x18000ded2`

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
0x18000ded2  jmp     cs:__imp_memset
```
