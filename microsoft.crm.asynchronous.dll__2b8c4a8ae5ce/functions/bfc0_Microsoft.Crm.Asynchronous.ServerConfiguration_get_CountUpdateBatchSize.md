# Microsoft.Crm.Asynchronous.ServerConfiguration::get_CountUpdateBatchSize

- ea: `0xbfc0`
- end: `0xbfd5`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::get_CountUpdateBatchSize`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xc960`

## string_xrefs

- `0xbfc5`: `ImportCountUpdateBatchSize`

## pseudocode

```c

```

## disassembly

```asm
0xbfc0  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xbfc5  ldstr    aImportcountupd// "ImportCountUpdateBatchSize"
0xbfca  call     object Microsoft.Crm.Asynchronous.ServerConfiguration::ReadServerSetting(class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService, string settingName)
0xbfcf  unbox.any [mscorlib]System.Int32
0xbfd4  ret
```
