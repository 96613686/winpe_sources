# memcpy_0

- ea: `0x18003cff6`
- end: `0x18003cffc`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180008480`
- `0x1800178f8`
- `0x18001e1ec`

## import_xrefs

- `msvcrt!memcpy` at `0x18003cff6`

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
0x18003cff6  jmp     cs:__imp_memcpy
```
