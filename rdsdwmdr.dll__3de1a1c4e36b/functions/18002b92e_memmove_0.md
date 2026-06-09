# memmove_0

- ea: `0x18002b92e`
- end: `0x18002b934`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180008058`

## import_xrefs

- `msvcrt!memmove` at `0x18002b92e`

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
0x18002b92e  jmp     cs:__imp_memmove
```
