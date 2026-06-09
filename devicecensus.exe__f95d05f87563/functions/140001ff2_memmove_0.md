# memmove_0

- ea: `0x140001ff2`
- end: `0x140001ff8`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1400033d0`
- `0x1400044b8`
- `0x1400086ac`
- `0x14000e380`
- `0x14000ee0c`

## import_xrefs

- `msvcrt!memmove` at `0x140001ff2`

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
0x140001ff2  jmp     cs:__imp_memmove
```
