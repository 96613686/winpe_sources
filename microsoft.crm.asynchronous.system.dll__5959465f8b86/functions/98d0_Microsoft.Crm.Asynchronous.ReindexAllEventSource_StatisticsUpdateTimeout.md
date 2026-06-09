# Microsoft.Crm.Asynchronous.ReindexAllEventSource::StatisticsUpdateTimeout

- ea: `0x98d0`
- end: `0x993e`
- name: `Microsoft.Crm.Asynchronous.ReindexAllEventSource::StatisticsUpdateTimeout`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xe310`

## callees

- `0x9940`

## pseudocode

```c

```

## disassembly

```asm
0x98d0  ldarg.0
0x98d1  ldarg.1
0x98d2  ldarg.2
0x98d3  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_MaxRuntime()
0x98d8  ldarg.2
0x98d9  callvirt instance int64 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ActualTimeTakenInMilliseconds()
0x98de  ldarg.2
0x98df  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_StatisticsToUpdate()
0x98e4  ldarg.2
0x98e5  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_StatisticsUpdated()
0x98ea  ldarg.2
0x98eb  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_FragmentationScanDurationInSeconds()
0x98f0  ldarg.2
0x98f1  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_MiscStatsUpdateBeforeRebuildInSeconds()
0x98f6  ldarg.2
0x98f7  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ReindexComments()
0x98fc  ldarg.2
0x98fd  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ExceptionCode()
0x9902  ldarg.2
0x9903  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ExceptionMessage()
0x9908  ldarg.2
0x9909  callvirt instance bool [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_IsVerboseEnabled()
0x990e  ldarg.2
0x990f  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_AllIndexTypes()
0x9914  ldarg.2
0x9915  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_FragRebuildPctHigh()
0x991a  ldarg.2
0x991b  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_FragRebuildPctLow()
0x9920  ldarg.2
0x9921  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_MaxFragPctToRebuild()
0x9926  ldarg.2
0x9927  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_DefragType()
0x992c  ldarg.2
0x992d  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_RebuildDaysOfWeek()
0x9932  ldarg.2
0x9933  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_Maxdop()
0x9938  call     instance void Microsoft.Crm.Asynchronous.ReindexAllEventSource::StatisticsUpdateTimeout(valuetype [mscorlib]System.Guid organizationId, int32 maxRunTime, int64 actualTimeTakenInMs, int32 statisticsToUpdate, int32 statisticsUpdated, int32 fragmentationScanDurationInSeconds, int32 miscStatsUpdateBeforeRebuildInSeconds, string reindexComments, int32 exceptionCode, string exceptionMessage, bool verboseEnabled, int32 AllIndexTypes, int32 FragRebuildPctHigh, int32 FragRebuildPctLow, int32 MaxFragPctToRebuild, int32 DefragType, string RebuildDaysOfWeek, int32 Maxdop)
0x993d  ret
```
