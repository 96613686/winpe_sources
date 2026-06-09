# _memmove

- ea: `0x100366a8`
- end: `0x100366ae`
- name: `_memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1001e0f0`
- `0x10026233`
- `0x100264c2`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x100366a8`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  return _memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x100366a8  jmp     ds:__imp__memmove
```
