# Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::get_StateStatusUpdateMaxRetryCount

- ea: `0xed50`
- end: `0xed61`
- name: `Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::get_StateStatusUpdateMaxRetryCount`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xe6f0`

## string_xrefs

- `0xed51`: `AsyncStateStatusUpdateMaxRetryCount`

## pseudocode

```c

```

## disassembly

```asm
0xed50  ldarg.0
0xed51  ldstr    aAsyncstatestat_0// "AsyncStateStatusUpdateMaxRetryCount"
0xed56  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xed5b  unbox.any [mscorlib]System.Int32
0xed60  ret
```
