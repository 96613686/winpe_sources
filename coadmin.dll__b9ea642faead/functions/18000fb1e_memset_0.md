# memset_0

- ea: `0x18000fb1e`
- end: `0x18000fb24`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x18000238c`
- `0x180003590`
- `0x1800063c0`
- `0x1800068d4`
- `0x180008ae0`
- `0x180009f60`
- `0x18000a0b0`
- `0x18000b08c`
- `0x18000b2d4`
- `0x18000cfd4`
- `0x18000de90`
- `0x18000eeb8`
- `0x18000f468`
- `0x18000f730`

## import_xrefs

- `msvcrt!memset` at `0x18000fb1e`

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
0x18000fb1e  jmp     cs:__imp_memset
```
