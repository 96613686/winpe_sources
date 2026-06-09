# Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::get_StateStatusUpdateInterval

- ea: `0xed30`
- end: `0xed47`
- name: `Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::get_StateStatusUpdateInterval`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xe6f0`

## string_xrefs

- `0xed31`: `AsyncStateStatusUpdateInterval`

## pseudocode

```c

```

## disassembly

```asm
0xed30  ldarg.0
0xed31  ldstr    aAsyncstatestat// "AsyncStateStatusUpdateInterval"
0xed36  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xed3b  unbox.any [mscorlib]System.Int32
0xed40  conv.r8
0xed41  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0xed46  ret
```
