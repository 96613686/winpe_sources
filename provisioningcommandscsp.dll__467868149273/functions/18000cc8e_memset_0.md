# memset_0

- ea: `0x18000cc8e`
- end: `0x18000cc94`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1800025b0`
- `0x180002844`
- `0x180002b04`
- `0x180003814`
- `0x1800045a8`
- `0x180004f7c`
- `0x18000539c`
- `0x180005b0c`
- `0x18000660c`
- `0x1800067ac`
- `0x1800096c0`

## import_xrefs

- `msvcrt!memset` at `0x18000cc8e`

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
0x18000cc8e  jmp     cs:__imp_memset
```
