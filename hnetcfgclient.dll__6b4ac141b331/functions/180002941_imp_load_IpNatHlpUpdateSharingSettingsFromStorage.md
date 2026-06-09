# __imp_load_IpNatHlpUpdateSharingSettingsFromStorage

- ea: `0x180002941`
- end: `0x18000294d`
- name: `__imp_load_IpNatHlpUpdateSharingSettingsFromStorage`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000289e`

## import_xrefs

- `IpNatHlpClient!IpNatHlpUpdateSharingSettingsFromStorage` at `0x180002941`

## pseudocode

```c
__int64 load_IpNatHlpUpdateSharingSettingsFromStorage()
{
  return _tailMerge_ipnathlpclient_dll();
}

```

## disassembly

```asm
0x180002941  lea     rax, __imp_IpNatHlpUpdateSharingSettingsFromStorage
0x180002948  jmp     __tailMerge_ipnathlpclient_dll
```
