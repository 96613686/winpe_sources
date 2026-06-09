# memmove_0

- ea: `0x18002e0be`
- end: `0x18002e0c4`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e9d0`
- `0x180010040`
- `0x1800101f8`
- `0x1800109fc`

## import_xrefs

- `msvcrt!memmove` at `0x18002e0be`

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
0x18002e0be  jmp     cs:__imp_memmove
```
