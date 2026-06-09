# memset_0

- ea: `0x18000c5ce`
- end: `0x18000c5d4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180002598`
- `0x180002818`
- `0x180002ac4`
- `0x180003140`
- `0x180003a74`
- `0x180004e30`
- `0x180005234`
- `0x180005930`
- `0x18000630c`
- `0x1800064ac`
- `0x180009290`

## import_xrefs

- `msvcrt!memset` at `0x18000c5ce`

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
0x18000c5ce  jmp     cs:__imp_memset
```
