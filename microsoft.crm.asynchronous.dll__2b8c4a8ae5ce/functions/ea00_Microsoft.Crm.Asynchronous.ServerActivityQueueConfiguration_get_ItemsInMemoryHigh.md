# Microsoft.Crm.Asynchronous.ServerActivityQueueConfiguration::get_ItemsInMemoryHigh

- ea: `0xea00`
- end: `0xea2b`
- name: `Microsoft.Crm.Asynchronous.ServerActivityQueueConfiguration::get_ItemsInMemoryHigh`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xe6e0`
- `0xe6f0`
- `0xea00`

## string_xrefs

- `0xea01`: `ActivityQueueItemsInMemoryHigh`

## pseudocode

```c

```

## disassembly

```asm
0xea00  ldarg.0
0xea01  ldstr    aActivityqueuei// "ActivityQueueItemsInMemoryHigh"
0xea06  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xea0b  stloc.0
0xea0c  ldloc.0
0xea0d  brtrue.s loc_EA24
0xea0f  ldarg.0
0xea10  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::get_Sku()
0xea15  ldc.i4.2
0xea16  beq.s    loc_EA1E
0xea18  ldc.i4   0x15E
0xea1d  ret
0xea1e  ldc.i4   0x15E
0xea23  ret
0xea24  ldloc.0
0xea25  unbox.any [mscorlib]System.Int32
0xea2a  ret
```
