# memset_0

- ea: `0x180008bbe`
- end: `0x180008bc4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001dd0`
- `0x1800020d0`
- `0x180003d10`
- `0x180003fe0`
- `0x180004220`
- `0x180005840`

## import_xrefs

- `msvcrt!memset` at `0x180008bbe`

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
0x180008bbe  jmp     cs:__imp_memset
```
