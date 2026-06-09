# memmove_0

- ea: `0x180011ad2`
- end: `0x180011ad8`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001be50`
- `0x180021eec`

## import_xrefs

- `msvcrt!memmove` at `0x180011ad2`

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
0x180011ad2  jmp     cs:__imp_memmove
```
