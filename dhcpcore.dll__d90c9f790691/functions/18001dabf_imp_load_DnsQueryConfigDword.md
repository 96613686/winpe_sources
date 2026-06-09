# __imp_load_DnsQueryConfigDword

- ea: `0x18001dabf`
- end: `0x18001dacb`
- name: `__imp_load_DnsQueryConfigDword`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18001da0a`

## import_xrefs

- `DNSAPI!DnsQueryConfigDword` at `0x18001dabf`

## pseudocode

```c
__int64 load_DnsQueryConfigDword()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x18001dabf  lea     rax, __imp_DnsQueryConfigDword
0x18001dac6  jmp     __tailMerge_dnsapi_dll
```
