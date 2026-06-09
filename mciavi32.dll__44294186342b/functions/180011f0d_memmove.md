# memmove

- ea: `0x180011f0d`
- end: `0x180011f13`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002b0c`
- `0x1800051e8`
- `0x180006b44`
- `0x180006f50`
- `0x18000a424`
- `0x18000bd6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180011f0d`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  return __imp_memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x180011f0d  jmp     cs:__imp_memmove
```
