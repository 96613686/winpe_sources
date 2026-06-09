# __imp_load_OneSettingsCreateDownloadConfig

- ea: `0x14000315f`
- end: `0x14000316b`
- name: `__imp_load_OneSettingsCreateDownloadConfig`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140003062`

## import_xrefs

- `OneSettingsClient!OneSettingsCreateDownloadConfig` at `0x14000315f`

## pseudocode

```c
__int64 load_OneSettingsCreateDownloadConfig()
{
  return _tailMerge_onesettingsclient_dll();
}

```

## disassembly

```asm
0x14000315f  lea     rax, __imp_OneSettingsCreateDownloadConfig
0x140003166  jmp     __tailMerge_onesettingsclient_dll
```
