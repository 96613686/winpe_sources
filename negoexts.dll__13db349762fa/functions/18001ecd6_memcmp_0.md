# memcmp_0

- ea: `0x18001ecd6`
- end: `0x18001ecdc`
- name: `memcmp_0`
- size: `6`
- prototype: `int __cdecl(const void *Buf1, const void *Buf2, size_t Size)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180004404`
- `0x1800070d0`
- `0x180008e60`
- `0x18000bf1c`
- `0x180010e68`

## import_xrefs

- `msvcrt!memcmp` at `0x18001ecd6`

## pseudocode

```c
// attributes: thunk
int __cdecl memcmp_0(const void *Buf1, const void *Buf2, size_t Size)
{
  return memcmp(Buf1, Buf2, Size);
}

```

## disassembly

```asm
0x18001ecd6  jmp     cs:__imp_memcmp
```
