# __imp_load_DnsDhcpRemoveRegistrations

- ea: `0x18001daad`
- end: `0x18001dab9`
- name: `__imp_load_DnsDhcpRemoveRegistrations`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001da0a`

## import_xrefs

- `DNSAPI!DnsDhcpRemoveRegistrations` at `0x18001daad`

## pseudocode

```c
__int64 load_DnsDhcpRemoveRegistrations()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x18001daad  lea     rax, __imp_DnsDhcpRemoveRegistrations
0x18001dab4  jmp     __tailMerge_dnsapi_dll
```
