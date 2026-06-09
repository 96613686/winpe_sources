# Microsoft.Crm.Asynchronous.Rollups.JobExecutor::DeleteInactiveRollupJob

- ea: `0xce30`
- end: `0xce48`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobExecutor::DeleteInactiveRollupJob`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x16e20`

## callees

- `0xce30`
- `0xdd20`
- `0xdf60`

## pseudocode

```c

```

## disassembly

```asm
0xce30  ldarg.1
0xce31  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_RollupProperties()
0xce36  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RollupStateCode [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData::get_StateCode()
0xce3b  brfalse.s loc_CE46
0xce3d  ldarg.1
0xce3e  callvirt instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.RollupJob::Delete()
0xce43  pop
0xce44  ldc.i4.1
0xce45  ret
0xce46  ldc.i4.0
0xce47  ret
```
