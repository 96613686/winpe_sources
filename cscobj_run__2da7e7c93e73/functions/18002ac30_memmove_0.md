# memmove_0

- ea: `0x18002ac30`
- end: `0x18002ac36`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x1800020a0`
- `0x180002df0`
- `0x180003710`
- `0x180003ca0`
- `0x180004028`
- `0x180004270`
- `0x180004a20`
- `0x180004cf0`
- `0x1800052c0`
- `0x180005e90`
- `0x1800061a0`
- `0x180006e70`
- `0x1800076e0`
- `0x1800083f0`
- `0x180022644`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18002ac30`

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
0x18002ac30  jmp     cs:__imp_memmove
```
