# memcpy_0

- ea: `0x18000edc6`
- end: `0x18000edcc`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800031c0`
- `0x1800036b8`
- `0x180003c08`
- `0x180004c24`
- `0x18000621c`
- `0x18000b564`
- `0x18000e330`

## import_xrefs

- `msvcrt!memcpy` at `0x18000edc6`

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
0x18000edc6  jmp     cs:__imp_memcpy
```
