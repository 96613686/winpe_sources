# __imp_load_DnsNameCopy

- ea: `0x180022dee`
- end: `0x180022dfa`
- name: `__imp_load_DnsNameCopy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180022d39`

## import_xrefs

- `DNSAPI!DnsNameCopy` at `0x180022dee`

## pseudocode

```c
__int64 load_DnsNameCopy()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x180022dee  lea     rax, __imp_DnsNameCopy
0x180022df5  jmp     __tailMerge_dnsapi_dll
```
