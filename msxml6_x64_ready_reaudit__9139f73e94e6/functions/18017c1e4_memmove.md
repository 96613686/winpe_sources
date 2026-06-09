# memmove

- ea: `0x18017c1e4`
- end: `0x18017c1ea`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `25`
- callee_count: `0`
- tags: ``

## callers

- `0x180013784`
- `0x18002b278`
- `0x1800374ac`
- `0x18003f7a0`
- `0x18003fa90`
- `0x18003fbc0`
- `0x180041cb0`
- `0x180041f80`
- `0x1800531b0`
- `0x18007acdc`
- `0x18007bd6c`
- `0x180080434`
- `0x1800a3c8c`
- `0x1800a531c`
- `0x1800bc2a4`
- `0x1800c55c8`
- `0x1800c850c`
- `0x1800d2e5c`
- `0x1800dbdc8`
- `0x18010d78c`
- `0x18011d050`
- `0x18015175c`
- `0x180152188`
- `0x180152b38`
- `0x180178ff0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18017c1e4`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  return __imp_memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x18017c1e4  jmp     cs:__imp_memmove
```
