# memmove_0

- ea: `0x18003b95e`
- end: `0x18003b964`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d790`
- `0x18000e604`
- `0x18000f7c4`
- `0x18000fd24`
- `0x180012e30`
- `0x1800248c4`
- `0x180024948`
- `0x180032f9c`

## import_xrefs

- `msvcrt!memmove` at `0x18003b95e`

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
0x18003b95e  jmp     cs:__imp_memmove
```
