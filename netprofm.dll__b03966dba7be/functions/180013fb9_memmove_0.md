# memmove_0

- ea: `0x180013fb9`
- end: `0x180013fbf`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180006e90`
- `0x18000c154`
- `0x18001b240`
- `0x18002b50c`
- `0x180034504`
- `0x1800346d4`
- `0x1800349b4`
- `0x180038548`
- `0x180038800`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180013fb9`

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
0x180013fb9  jmp     cs:__imp_memmove
```
