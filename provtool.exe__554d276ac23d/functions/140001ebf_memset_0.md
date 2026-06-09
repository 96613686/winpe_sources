# memset_0

- ea: `0x140001ebf`
- end: `0x140001ec5`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x1400017e0`
- `0x1400023bc`
- `0x1400027b4`
- `0x140002a34`
- `0x140002ce8`
- `0x140002f94`
- `0x140003de0`
- `0x140005204`
- `0x1400059ac`
- `0x1400079f4`
- `0x140007df8`
- `0x140008510`
- `0x140009590`
- `0x140009b10`
- `0x14000b454`
- `0x14000c7f0`
- `0x14000c920`

## import_xrefs

- `msvcrt!memset` at `0x140001ebf`

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
0x140001ebf  jmp     cs:__imp_memset
```
