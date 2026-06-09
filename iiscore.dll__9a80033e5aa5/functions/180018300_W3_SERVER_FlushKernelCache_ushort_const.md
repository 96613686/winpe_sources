# W3_SERVER::FlushKernelCache(ushort const *)

- ea: `0x180018300`
- end: `0x18001830a`
- name: `?FlushKernelCache@W3_SERVER@@UEAAJPEBG@Z`
- size: `10`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `w3dt!UlAtqFlushUlCache` at `0x180018303`

## pseudocode

```c
int __fastcall W3_SERVER::FlushKernelCache(W3_SERVER *this, unsigned __int16 *a2)
{
  return UlAtqFlushUlCache(a2);
}

```

## disassembly

```asm
0x180018300  mov     rcx, rdx
0x180018303  jmp     cs:__imp_?UlAtqFlushUlCache@@YAJPEAG@Z; UlAtqFlushUlCache(ushort *)
```
