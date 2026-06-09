# memmove_0

- ea: `0x180034b5c`
- end: `0x180034b62`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180007300`
- `0x180014944`
- `0x180014ccc`
- `0x180015158`
- `0x18002cad8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180034b5c`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove_0(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x180034b5c  jmp     cs:__imp_memmove
```
