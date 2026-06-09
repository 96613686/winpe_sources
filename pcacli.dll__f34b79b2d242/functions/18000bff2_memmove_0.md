# memmove_0

- ea: `0x18000bff2`
- end: `0x18000bff8`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002210`
- `0x1800046c0`
- `0x180007200`
- `0x18000aa1c`

## import_xrefs

- `msvcrt!memmove` at `0x18000bff2`

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
0x18000bff2  jmp     cs:__imp_memmove
```
