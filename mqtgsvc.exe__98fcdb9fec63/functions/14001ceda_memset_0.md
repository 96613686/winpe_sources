# memset_0

- ea: `0x14001ceda`
- end: `0x14001cee0`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x1400031c4`
- `0x140003720`
- `0x14000f6e0`
- `0x140012540`
- `0x140016730`
- `0x1400167e0`
- `0x1400168d4`
- `0x140018204`
- `0x1400190b0`
- `0x1400191dc`
- `0x14001a0e4`
- `0x14001a460`
- `0x14001a680`
- `0x14001b2c0`
- `0x14001c0b0`

## import_xrefs

- `msvcrt!memset` at `0x14001ceda`

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
0x14001ceda  jmp     cs:__imp_memset
```
