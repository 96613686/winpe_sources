# memmove_0

- ea: `0x1400076dd`
- end: `0x1400076e3`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140007314`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1400076dd`

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
0x1400076dd  jmp     cs:__imp_memmove
```
