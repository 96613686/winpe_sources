# memcpy_0

- ea: `0x18000bde9`
- end: `0x18000bdef`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180001970`
- `0x180002e50`
- `0x180003250`
- `0x180003e20`
- `0x180004200`
- `0x180006c14`
- `0x1800086d0`
- `0x180009370`
- `0x180009ff0`
- `0x18000a2cc`
- `0x18000a5f8`
- `0x18000aa78`
- `0x18000ad20`
- `0x18000b1f8`
- `0x18000b78c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x18000bde9`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy_0(void *a1, const void *Src, size_t Size)
{
  return memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x18000bde9  jmp     cs:__imp_memcpy
```
