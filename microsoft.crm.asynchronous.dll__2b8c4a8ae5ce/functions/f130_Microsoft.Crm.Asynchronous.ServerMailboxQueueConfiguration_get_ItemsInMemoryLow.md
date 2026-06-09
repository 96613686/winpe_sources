# Microsoft.Crm.Asynchronous.ServerMailboxQueueConfiguration::get_ItemsInMemoryLow

- ea: `0xf130`
- end: `0xf155`
- name: `Microsoft.Crm.Asynchronous.ServerMailboxQueueConfiguration::get_ItemsInMemoryLow`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xe6e0`
- `0xe6f0`
- `0xf130`

## string_xrefs

- `0xf131`: `MailboxQueueItemsInMemoryLow`

## pseudocode

```c

```

## disassembly

```asm
0xf130  ldarg.0
0xf131  ldstr    aMailboxqueueit_0// "MailboxQueueItemsInMemoryLow"
0xf136  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xf13b  stloc.0
0xf13c  ldloc.0
0xf13d  brtrue.s loc_F14E
0xf13f  ldarg.0
0xf140  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::get_Sku()
0xf145  ldc.i4.2
0xf146  beq.s    loc_F14B
0xf148  ldc.i4.s 0x64
0xf14a  ret
0xf14b  ldc.i4.s 0x64
0xf14d  ret
0xf14e  ldloc.0
0xf14f  unbox.any [mscorlib]System.Int32
0xf154  ret
```
