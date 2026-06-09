# __imp_load_DnsWriteReverseNameStringForIpAddressW

- ea: `0x180022efc`
- end: `0x180022f08`
- name: `__imp_load_DnsWriteReverseNameStringForIpAddressW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180022d39`

## import_xrefs

- `DNSAPI!DnsWriteReverseNameStringForIpAddressW` at `0x180022efc`

## pseudocode

```c
__int64 load_DnsWriteReverseNameStringForIpAddressW()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x180022efc  lea     rax, __imp_DnsWriteReverseNameStringForIpAddressW
0x180022f03  jmp     __tailMerge_dnsapi_dll
```
