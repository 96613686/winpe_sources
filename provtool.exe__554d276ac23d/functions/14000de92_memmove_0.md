# memmove_0

- ea: `0x14000de92`
- end: `0x14000de98`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400033a8`
- `0x140008850`
- `0x1400088f0`
- `0x140008cd8`

## import_xrefs

- `msvcrt!memmove` at `0x14000de92`

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
0x14000de92  jmp     cs:__imp_memmove
```
