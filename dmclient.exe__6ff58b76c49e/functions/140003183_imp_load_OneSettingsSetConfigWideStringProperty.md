# __imp_load_OneSettingsSetConfigWideStringProperty

- ea: `0x140003183`
- end: `0x14000318f`
- name: `__imp_load_OneSettingsSetConfigWideStringProperty`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140003062`

## import_xrefs

- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x140003183`

## pseudocode

```c
__int64 load_OneSettingsSetConfigWideStringProperty()
{
  return _tailMerge_onesettingsclient_dll();
}

```

## disassembly

```asm
0x140003183  lea     rax, __imp_OneSettingsSetConfigWideStringProperty
0x14000318a  jmp     __tailMerge_onesettingsclient_dll
```
