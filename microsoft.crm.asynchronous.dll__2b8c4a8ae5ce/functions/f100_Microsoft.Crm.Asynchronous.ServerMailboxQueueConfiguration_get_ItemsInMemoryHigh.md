# Microsoft.Crm.Asynchronous.ServerMailboxQueueConfiguration::get_ItemsInMemoryHigh

- ea: `0xf100`
- end: `0xf12b`
- name: `Microsoft.Crm.Asynchronous.ServerMailboxQueueConfiguration::get_ItemsInMemoryHigh`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xe6e0`
- `0xe6f0`
- `0xf100`

## string_xrefs

- `0xf101`: `MailboxQueueItemsInMemoryHigh`

## pseudocode

```c

```

## disassembly

```asm
0xf100  ldarg.0
0xf101  ldstr    aMailboxqueueit// "MailboxQueueItemsInMemoryHigh"
0xf106  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xf10b  stloc.0
0xf10c  ldloc.0
0xf10d  brtrue.s loc_F124
0xf10f  ldarg.0
0xf110  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::get_Sku()
0xf115  ldc.i4.2
0xf116  beq.s    loc_F11E
0xf118  ldc.i4   0x15E
0xf11d  ret
0xf11e  ldc.i4   0x15E
0xf123  ret
0xf124  ldloc.0
0xf125  unbox.any [mscorlib]System.Int32
0xf12a  ret
```
