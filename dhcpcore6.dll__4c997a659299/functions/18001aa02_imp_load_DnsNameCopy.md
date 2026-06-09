# __imp_load_DnsNameCopy

- ea: `0x18001aa02`
- end: `0x18001aa0e`
- name: `__imp_load_DnsNameCopy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001a44a`

## import_xrefs

- `DNSAPI!DnsNameCopy` at `0x18001aa02`

## pseudocode

```c
__int64 load_DnsNameCopy()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x18001aa02  lea     rax, __imp_DnsNameCopy
0x18001aa09  jmp     __tailMerge_dnsapi_dll
```
