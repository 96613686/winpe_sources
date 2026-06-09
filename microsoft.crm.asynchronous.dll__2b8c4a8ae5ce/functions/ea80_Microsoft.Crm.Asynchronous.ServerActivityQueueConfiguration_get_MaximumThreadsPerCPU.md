# Microsoft.Crm.Asynchronous.ServerActivityQueueConfiguration::get_MaximumThreadsPerCPU

- ea: `0xea80`
- end: `0xea99`
- name: `Microsoft.Crm.Asynchronous.ServerActivityQueueConfiguration::get_MaximumThreadsPerCPU`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe6f0`
- `0xea80`

## string_xrefs

- `0xea81`: `ActivityQueueMaximumThreadsPerCPU`

## pseudocode

```c

```

## disassembly

```asm
0xea80  ldarg.0
0xea81  ldstr    aActivityqueuem_0// "ActivityQueueMaximumThreadsPerCPU"
0xea86  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xea8b  stloc.0
0xea8c  ldloc.0
0xea8d  brfalse.s loc_EA96
0xea8f  ldloc.0
0xea90  unbox.any [mscorlib]System.Int32
0xea95  ret
0xea96  ldc.i4.s 0x64
0xea98  ret
```
