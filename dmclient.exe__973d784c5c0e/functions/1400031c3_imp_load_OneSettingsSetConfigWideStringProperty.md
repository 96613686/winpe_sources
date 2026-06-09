# __imp_load_OneSettingsSetConfigWideStringProperty

- ea: `0x1400031c3`
- end: `0x1400031cf`
- name: `__imp_load_OneSettingsSetConfigWideStringProperty`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1400030a2`

## import_xrefs

- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x1400031c3`

## pseudocode

```c
__int64 load_OneSettingsSetConfigWideStringProperty()
{
  return _tailMerge_onesettingsclient_dll();
}

```

## disassembly

```asm
0x1400031c3  lea     rax, __imp_OneSettingsSetConfigWideStringProperty
0x1400031ca  jmp     __tailMerge_onesettingsclient_dll
```
