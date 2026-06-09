# Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::get_ItemsInMemoryHigh

- ea: `0xee40`
- end: `0xee51`
- name: `Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::get_ItemsInMemoryHigh`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xef30`

## callees

- `0xe6f0`

## string_xrefs

- `0xee41`: `AsyncItemsInMemoryHigh`

## pseudocode

```c

```

## disassembly

```asm
0xee40  ldarg.0
0xee41  ldstr    aAsyncitemsinme// "AsyncItemsInMemoryHigh"
0xee46  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xee4b  unbox.any [mscorlib]System.Int32
0xee50  ret
```
