# memcmp_0

- ea: `0x18000aad1`
- end: `0x18000aad7`
- name: `memcmp_0`
- size: `6`
- prototype: `int __cdecl(const void *Buf1, const void *Buf2, size_t Size)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800089b0`
- `0x18000a4f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcmp` at `0x18000aad1`

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
0x18000aad1  jmp     cs:__imp_memcmp
```
