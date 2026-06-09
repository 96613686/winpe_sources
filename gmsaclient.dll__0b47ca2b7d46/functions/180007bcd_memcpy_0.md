# memcpy_0

- ea: `0x180007bcd`
- end: `0x180007bd3`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003514`
- `0x180004bbc`
- `0x180005018`
- `0x180006a38`
- `0x180007064`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x180007bcd`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy_0(void *a1, const void *Src, size_t Size)
{
  return memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x180007bcd  jmp     cs:__imp_memcpy
```
