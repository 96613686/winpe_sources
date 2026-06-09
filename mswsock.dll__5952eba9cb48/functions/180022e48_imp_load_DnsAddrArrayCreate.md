# __imp_load_DnsAddrArrayCreate

- ea: `0x180022e48`
- end: `0x180022e54`
- name: `__imp_load_DnsAddrArrayCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180022d39`

## import_xrefs

- `DNSAPI!DnsAddrArrayCreate` at `0x180022e48`

## pseudocode

```c
__int64 load_DnsAddrArrayCreate()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x180022e48  lea     rax, __imp_DnsAddrArrayCreate
0x180022e4f  jmp     __tailMerge_dnsapi_dll
```
