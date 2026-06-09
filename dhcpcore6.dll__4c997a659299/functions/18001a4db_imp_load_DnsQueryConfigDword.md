# __imp_load_DnsQueryConfigDword

- ea: `0x18001a4db`
- end: `0x18001a4e7`
- name: `__imp_load_DnsQueryConfigDword`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18001a44a`

## import_xrefs

- `DNSAPI!DnsQueryConfigDword` at `0x18001a4db`

## pseudocode

```c
__int64 load_DnsQueryConfigDword()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x18001a4db  lea     rax, __imp_DnsQueryConfigDword
0x18001a4e2  jmp     __tailMerge_dnsapi_dll
```
