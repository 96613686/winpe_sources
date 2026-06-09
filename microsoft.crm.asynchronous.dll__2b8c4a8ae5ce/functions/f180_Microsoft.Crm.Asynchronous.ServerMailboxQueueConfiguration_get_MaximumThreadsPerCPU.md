# Microsoft.Crm.Asynchronous.ServerMailboxQueueConfiguration::get_MaximumThreadsPerCPU

- ea: `0xf180`
- end: `0xf199`
- name: `Microsoft.Crm.Asynchronous.ServerMailboxQueueConfiguration::get_MaximumThreadsPerCPU`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe6f0`
- `0xf180`

## string_xrefs

- `0xf181`: `MailboxQueueMaximumThreadsPerCPU`

## pseudocode

```c

```

## disassembly

```asm
0xf180  ldarg.0
0xf181  ldstr    aMailboxqueuema_0// "MailboxQueueMaximumThreadsPerCPU"
0xf186  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xf18b  stloc.0
0xf18c  ldloc.0
0xf18d  brfalse.s loc_F196
0xf18f  ldloc.0
0xf190  unbox.any [mscorlib]System.Int32
0xf195  ret
0xf196  ldc.i4.s 0x64
0xf198  ret
```
