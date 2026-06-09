# __imp_load_RasSrvAllowConnectionsConfig

- ea: `0x180002c2e`
- end: `0x180002c3a`
- name: `__imp_load_RasSrvAllowConnectionsConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180002baf`

## import_xrefs

- `RASDLG!RasSrvAllowConnectionsConfig` at `0x180002c2e`

## pseudocode

```c
__int64 load_RasSrvAllowConnectionsConfig()
{
  return _tailMerge_rasdlg_dll();
}

```

## disassembly

```asm
0x180002c2e  lea     rax, __imp_RasSrvAllowConnectionsConfig
0x180002c35  jmp     __tailMerge_rasdlg_dll
```
