# memmove_0

- ea: `0x14002c40c`
- end: `0x14002c412`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x140004750`
- `0x1400061dc`
- `0x1400062d0`
- `0x140008308`
- `0x140009398`
- `0x14000be5c`
- `0x1400111f4`
- `0x140011338`
- `0x140013a44`
- `0x14001c3b0`
- `0x1400246a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x14002c40c`

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
0x14002c40c  jmp     cs:__imp_memmove
```
