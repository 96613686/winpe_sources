# memmove_0

- ea: `0x18001aa8e`
- end: `0x18001aa94`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x180009018`
- `0x18000cd0c`
- `0x18000d9a0`

## import_xrefs

- `msvcrt!memmove` at `0x18001aa8e`

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
0x18001aa8e  jmp     cs:__imp_memmove
```
