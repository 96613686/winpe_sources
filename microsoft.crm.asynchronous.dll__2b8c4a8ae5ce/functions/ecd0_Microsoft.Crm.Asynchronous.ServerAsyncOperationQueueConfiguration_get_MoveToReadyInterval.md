# Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::get_MoveToReadyInterval

- ea: `0xecd0`
- end: `0xece7`
- name: `Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::get_MoveToReadyInterval`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe6f0`

## string_xrefs

- `0xecd1`: `AsyncMoveToReadyInterval`

## pseudocode

```c

```

## disassembly

```asm
0xecd0  ldarg.0
0xecd1  ldstr    aAsyncmovetorea// "AsyncMoveToReadyInterval"
0xecd6  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xecdb  unbox.any [mscorlib]System.Int32
0xece0  conv.r8
0xece1  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0xece6  ret
```
