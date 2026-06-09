# Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::get_ItemsInMemoryLow

- ea: `0xee60`
- end: `0xee71`
- name: `Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::get_ItemsInMemoryLow`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xe6f0`

## string_xrefs

- `0xee61`: `AsyncItemsInMemoryLow`

## pseudocode

```c

```

## disassembly

```asm
0xee60  ldarg.0
0xee61  ldstr    aAsyncitemsinme_0// "AsyncItemsInMemoryLow"
0xee66  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xee6b  unbox.any [mscorlib]System.Int32
0xee70  ret
```
