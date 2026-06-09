# __imp_load_OneSettingsFreeDownloadConfig

- ea: `0x140003157`
- end: `0x140003163`
- name: `__imp_load_OneSettingsFreeDownloadConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1400030a2`

## import_xrefs

- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x140003157`

## pseudocode

```c
__int64 load_OneSettingsFreeDownloadConfig()
{
  return _tailMerge_onesettingsclient_dll();
}

```

## disassembly

```asm
0x140003157  lea     rax, __imp_OneSettingsFreeDownloadConfig
0x14000315e  jmp     __tailMerge_onesettingsclient_dll
```
