# memmove_0

- ea: `0x180012a8c`
- end: `0x180012a92`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005050`
- `0x18000990c`
- `0x18000a3a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180012a8c`

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
0x180012a8c  jmp     cs:__imp_memmove
```
