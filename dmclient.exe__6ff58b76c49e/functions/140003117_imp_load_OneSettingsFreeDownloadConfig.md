# __imp_load_OneSettingsFreeDownloadConfig

- ea: `0x140003117`
- end: `0x140003123`
- name: `__imp_load_OneSettingsFreeDownloadConfig`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140003062`

## import_xrefs

- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x140003117`

## pseudocode

```c
__int64 load_OneSettingsFreeDownloadConfig()
{
  return _tailMerge_onesettingsclient_dll();
}

```

## disassembly

```asm
0x140003117  lea     rax, __imp_OneSettingsFreeDownloadConfig
0x14000311e  jmp     __tailMerge_onesettingsclient_dll
```
