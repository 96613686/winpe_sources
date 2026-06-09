# memset_0

- ea: `0x18000edde`
- end: `0x18000ede4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b78`
- `0x1800022c8`
- `0x180005294`
- `0x180006d40`
- `0x1800075f0`
- `0x180007e1c`
- `0x180008850`
- `0x180009204`
- `0x180009980`
- `0x180009d74`
- `0x18000a028`
- `0x18000a8b8`
- `0x18000abfc`
- `0x18000b088`
- `0x18000bb5c`
- `0x18000c390`
- `0x18000d370`
- `0x18000e448`
- `0x18000e510`

## import_xrefs

- `msvcrt!memset` at `0x18000edde`

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
0x18000edde  jmp     cs:__imp_memset
```
