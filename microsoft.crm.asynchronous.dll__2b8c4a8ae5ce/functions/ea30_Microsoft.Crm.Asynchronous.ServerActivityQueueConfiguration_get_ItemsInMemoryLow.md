# Microsoft.Crm.Asynchronous.ServerActivityQueueConfiguration::get_ItemsInMemoryLow

- ea: `0xea30`
- end: `0xea55`
- name: `Microsoft.Crm.Asynchronous.ServerActivityQueueConfiguration::get_ItemsInMemoryLow`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xe6e0`
- `0xe6f0`
- `0xea30`

## string_xrefs

- `0xea31`: `ActivityQueueItemsInMemoryLow`

## pseudocode

```c

```

## disassembly

```asm
0xea30  ldarg.0
0xea31  ldstr    aActivityqueuei_0// "ActivityQueueItemsInMemoryLow"
0xea36  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xea3b  stloc.0
0xea3c  ldloc.0
0xea3d  brtrue.s loc_EA4E
0xea3f  ldarg.0
0xea40  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::get_Sku()
0xea45  ldc.i4.2
0xea46  beq.s    loc_EA4B
0xea48  ldc.i4.s 0x64
0xea4a  ret
0xea4b  ldc.i4.s 0x64
0xea4d  ret
0xea4e  ldloc.0
0xea4f  unbox.any [mscorlib]System.Int32
0xea54  ret
```
