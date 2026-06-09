# __imp_load_OneSettingsCreateDownloadConfig

- ea: `0x14000319f`
- end: `0x1400031ab`
- name: `__imp_load_OneSettingsCreateDownloadConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1400030a2`

## import_xrefs

- `OneSettingsClient!OneSettingsCreateDownloadConfig` at `0x14000319f`

## pseudocode

```c
__int64 load_OneSettingsCreateDownloadConfig()
{
  return _tailMerge_onesettingsclient_dll();
}

```

## disassembly

```asm
0x14000319f  lea     rax, __imp_OneSettingsCreateDownloadConfig
0x1400031a6  jmp     __tailMerge_onesettingsclient_dll
```
