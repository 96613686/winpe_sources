# memset_0

- ea: `0x18000cbbe`
- end: `0x18000cbc4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d50`
- `0x180001fc0`
- `0x18000225c`
- `0x1800024d4`
- `0x180002dc4`
- `0x180003f00`
- `0x1800045b0`
- `0x1800050b0`
- `0x180005470`
- `0x18000642c`
- `0x180008ec0`
- `0x18000b328`
- `0x18000b7a0`
- `0x18000bda0`
- `0x18000c080`

## import_xrefs

- `msvcrt!memset` at `0x18000cbbe`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset_0(void *a1, int Val, size_t Size)
{
  return memset(a1, Val, Size);
}

```

## disassembly

```asm
0x18000cbbe  jmp     cs:__imp_memset
```
