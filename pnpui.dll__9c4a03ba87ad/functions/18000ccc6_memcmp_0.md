# memcmp_0

- ea: `0x18000ccc6`
- end: `0x18000cccc`
- name: `memcmp_0`
- size: `6`
- prototype: `int __cdecl(const void *Buf1, const void *Buf2, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005c58`
- `0x180008b24`
- `0x18000b868`

## import_xrefs

- `msvcrt!memcmp` at `0x18000ccc6`

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
0x18000ccc6  jmp     cs:__imp_memcmp
```
