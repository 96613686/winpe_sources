# memmove_0

- ea: `0x140013f0a`
- end: `0x140013f10`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14000b578`
- `0x1400102cc`
- `0x140010354`

## import_xrefs

- `VCRUNTIME140_CLR0400!memmove` at `0x140013f0a`

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
0x140013f0a  jmp     cs:__imp_memmove
```
