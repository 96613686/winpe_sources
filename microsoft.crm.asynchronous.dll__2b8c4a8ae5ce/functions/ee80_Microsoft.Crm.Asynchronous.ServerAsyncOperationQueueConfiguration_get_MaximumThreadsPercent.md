# Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::get_MaximumThreadsPercent

- ea: `0xee80`
- end: `0xee91`
- name: `Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::get_MaximumThreadsPercent`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe6f0`

## string_xrefs

- `0xee81`: `AsyncMaximumThreadsPercent`

## pseudocode

```c

```

## disassembly

```asm
0xee80  ldarg.0
0xee81  ldstr    aAsyncmaximumth// "AsyncMaximumThreadsPercent"
0xee86  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xee8b  unbox.any [mscorlib]System.Double
0xee90  ret
```
