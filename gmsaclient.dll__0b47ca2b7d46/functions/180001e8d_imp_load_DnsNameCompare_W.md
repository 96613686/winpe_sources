# __imp_load_DnsNameCompare_W

- ea: `0x180001e8d`
- end: `0x180001e99`
- name: `__imp_load_DnsNameCompare_W`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001e0e`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x180001e8d`

## pseudocode

```c
__int64 load_DnsNameCompare_W()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x180001e8d  lea     rax, __imp_DnsNameCompare_W
0x180001e94  jmp     __tailMerge_dnsapi_dll
```
