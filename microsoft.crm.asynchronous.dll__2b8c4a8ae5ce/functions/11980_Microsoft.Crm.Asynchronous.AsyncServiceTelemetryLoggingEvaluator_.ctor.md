# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::.ctor

- ea: `0x11980`
- end: `0x11b19`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::.ctor`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x11b20`

## pseudocode

```c

```

## disassembly

```asm
0x11980  ldarg.0
0x11981  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x11986  dup
0x11987  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticsConstants::StatsDBOperationId
0x1198c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x11991  dup
0x11992  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticsConstants::StatsOperationId
0x11997  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1199c  dup
0x1199d  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticsConstants::StatsSizeOperationId
0x119a2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x119a7  dup
0x119a8  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticsConstants::StorageLimitNotificationId
0x119ad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x119b2  dup
0x119b3  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticsConstants::UpdateStatIntervalsOperationId
0x119b8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x119bd  dup
0x119be  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::RecurringJob_DeleteCompletedSystemJobs_Id
0x119c3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x119c8  dup
0x119c9  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::RecurringJob_DeleteCompletedProcessSessionsForSyncWorkflows_Id
0x119ce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x119d3  dup
0x119d4  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::RecurringJob_RecurringSeriesExpansionJob_Id
0x119d9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x119de  dup
0x119df  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::RecurringJob_PostToYammerJob_Id
0x119e4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x119e9  dup
0x119ea  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::RecurringJob_GoalRollupJob_Id
0x119ef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x119f4  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::_fixedIds
0x119f9  ldarg.0
0x119fa  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x119ff  dup
0x11a00  ldc.i4.s 9
0x11a02  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a07  dup
0x11a08  ldc.i4.s 0x10
0x11a0a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a0f  dup
0x11a10  ldc.i4.s 0x12
0x11a12  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a17  dup
0x11a18  ldc.i4.s 0x13
0x11a1a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a1f  dup
0x11a20  ldc.i4.s 0x14
0x11a22  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a27  dup
0x11a28  ldc.i4.s 0x16
0x11a2a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a2f  dup
0x11a30  ldc.i4.s 0x18
0x11a32  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a37  dup
0x11a38  ldc.i4.s 0x19
0x11a3a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a3f  dup
0x11a40  ldc.i4.s 0x1F
0x11a42  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a47  stfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::_systemJobTypes
0x11a4c  ldarg.0
0x11a4d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x11a52  dup
0x11a53  ldc.i4.s 0xE
0x11a55  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a5a  dup
0x11a5b  ldc.i4.s 0xF
0x11a5d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a62  dup
0x11a63  ldc.i4.s 0x1E
0x11a65  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a6a  dup
0x11a6b  ldc.i4.s 0x3D
0x11a6d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a72  dup
0x11a73  ldc.i4.s 0x20
0x11a75  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a7a  dup
0x11a7b  ldc.i4.s 0x29
0x11a7d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a82  dup
0x11a83  ldc.i4.s 0x2A
0x11a85  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a8a  dup
0x11a8b  ldc.i4.s 0x2E
0x11a8d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a92  dup
0x11a93  ldc.i4.s 0x2F
0x11a95  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11a9a  dup
0x11a9b  ldc.i4.s 0x30
0x11a9d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11aa2  stfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::_scalegroupOrganizationMaintenanceJobs
0x11aa7  ldarg.0
0x11aa8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x11aad  dup
0x11aae  ldc.i4.s 0xC
0x11ab0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11ab5  dup
0x11ab6  ldc.i4.s 0x15
0x11ab8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11abd  dup
0x11abe  ldc.i4.s 0x1A
0x11ac0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11ac5  dup
0x11ac6  ldc.i4.s 0x1C
0x11ac8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11acd  dup
0x11ace  ldc.i4.s 0x1D
0x11ad0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11ad5  dup
0x11ad6  ldc.i4.s 0x23
0x11ad8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11add  dup
0x11ade  ldc.i4.s 0x26
0x11ae0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11ae5  dup
0x11ae6  ldc.i4.s 0x2B
0x11ae8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11aed  dup
0x11aee  ldc.i4.s 0x2C
0x11af0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11af5  dup
0x11af6  ldc.i4.s 0x35
0x11af8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11afd  dup
0x11afe  ldc.i4.s 0x37
0x11b00  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11b05  dup
0x11b06  ldc.i4.s 0x40
0x11b08  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x11b0d  stfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::_canBeIgnoredJobTypes
0x11b12  ldarg.0
0x11b13  call     instance void [mscorlib]System.Object::.ctor()
0x11b18  ret
```
