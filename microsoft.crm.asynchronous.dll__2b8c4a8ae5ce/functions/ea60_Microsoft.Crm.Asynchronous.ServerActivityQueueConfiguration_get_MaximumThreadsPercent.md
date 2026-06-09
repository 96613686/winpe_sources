# Microsoft.Crm.Asynchronous.ServerActivityQueueConfiguration::get_MaximumThreadsPercent

- ea: `0xea60`
- end: `0xea71`
- name: `Microsoft.Crm.Asynchronous.ServerActivityQueueConfiguration::get_MaximumThreadsPercent`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe6f0`

## string_xrefs

- `0xea61`: `ActivityQueueMaximumThreadsPercent`

## pseudocode

```c

```

## disassembly

```asm
0xea60  ldarg.0
0xea61  ldstr    aActivityqueuem// "ActivityQueueMaximumThreadsPercent"
0xea66  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xea6b  unbox.any [mscorlib]System.Double
0xea70  ret
```
