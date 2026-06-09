# memset_0

- ea: `0x18001abfa`
- end: `0x18001ac00`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180003138`
- `0x1800031ec`
- `0x180003488`
- `0x1800036f0`
- `0x180003f30`
- `0x180004284`
- `0x18000509c`
- `0x180005afc`
- `0x180005c38`
- `0x1800060a8`
- `0x180006e78`
- `0x18000c1d0`
- `0x18001077c`
- `0x180011538`
- `0x180013b7c`
- `0x1800143f0`
- `0x180016dd8`

## import_xrefs

- `msvcrt!memset` at `0x18001abfa`

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
0x18001abfa  jmp     cs:__imp_memset
```
