# memcmp_0

- ea: `0x18000cba6`
- end: `0x18000cbac`
- name: `memcmp_0`
- size: `6`
- prototype: `int __cdecl(const void *Buf1, const void *Buf2, size_t Size)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180005f5c`
- `0x180006900`
- `0x180008ec0`
- `0x180009370`
- `0x1800098ac`

## import_xrefs

- `msvcrt!memcmp` at `0x18000cba6`

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
0x18000cba6  jmp     cs:__imp_memcmp
```
