# __imp_load_DnsStringCopyAllocateEx

- ea: `0x180022e12`
- end: `0x180022e1e`
- name: `__imp_load_DnsStringCopyAllocateEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180022d39`

## import_xrefs

- `DNSAPI!DnsStringCopyAllocateEx` at `0x180022e12`

## pseudocode

```c
__int64 load_DnsStringCopyAllocateEx()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x180022e12  lea     rax, __imp_DnsStringCopyAllocateEx
0x180022e19  jmp     __tailMerge_dnsapi_dll
```
