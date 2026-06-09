# __imp_load_DnsQueryConfigAllocEx

- ea: `0x180022db8`
- end: `0x180022dc4`
- name: `__imp_load_DnsQueryConfigAllocEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180022d39`

## import_xrefs

- `DNSAPI!DnsQueryConfigAllocEx` at `0x180022db8`

## pseudocode

```c
__int64 load_DnsQueryConfigAllocEx()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x180022db8  lea     rax, __imp_DnsQueryConfigAllocEx
0x180022dbf  jmp     __tailMerge_dnsapi_dll
```
