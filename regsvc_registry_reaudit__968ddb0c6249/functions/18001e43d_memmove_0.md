# memmove_0

- ea: `0x18001e43d`
- end: `0x18001e443`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800059a0`
- `0x180005f20`
- `0x18000b7c8`
- `0x18000f640`
- `0x180011d10`
- `0x18001b9c0`
- `0x18001bedc`
- `0x18001c734`
- `0x18001d32c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18001e43d`

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
0x18001e43d  jmp     cs:__imp_memmove
```
