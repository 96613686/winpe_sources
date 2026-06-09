# memmove_0

- ea: `0x14002e8d8`
- end: `0x14002e8de`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x14000cbb8`
- `0x14000cd84`
- `0x14000de24`
- `0x1400129e8`
- `0x1400145d0`
- `0x140016398`
- `0x1400168a0`
- `0x14001af8c`
- `0x14001b384`
- `0x14001cb74`
- `0x14002baf0`
- `0x14002da48`
- `0x140031990`
- `0x140031dfc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x14002e8d8`

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
0x14002e8d8  jmp     cs:__imp_memmove
```
