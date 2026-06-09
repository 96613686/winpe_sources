# Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::ReleaseStuckJobs

- ea: `0x66d0`
- end: `0x6763`
- name: `Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::ReleaseStuckJobs`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6430`

## callees

- `0x6f50`

## string_xrefs

- `0x6757`: `d:\dbs\sh\dccm2\1101_190851\cmd\34\src\Core\ObjectModel\Async\AsyncService\ScalegroupMaintenanceJobsMonitor.cs`

## pseudocode

```c

```

## disassembly

```asm
0x66d0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x66d5  stloc.0
0x66d6  ldloc.0
0x66d7  ldstr    aIsrunning// "IsRunning"
0x66dc  ldc.i4.0
0x66dd  box      [mscorlib]System.Boolean
0x66e2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x66e7  ldloc.0
0x66e8  ldstr    aHostlocked// "HostLocked"
0x66ed  ldc.i4.0
0x66ee  box      [mscorlib]System.Boolean
0x66f3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x66f8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x66fd  stloc.1
0x66fe  ldc.i4.3
0x66ff  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6704  call     int32 Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsConfiguration::get_JobExpiredThresholdInSeconds()
0x6709  conv.r8
0x670a  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x670f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x6714  box      [mscorlib]System.DateTime
0x6719  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x671e  stloc.2
0x671f  ldloc.1
0x6720  ldstr    aNextruntime_0// "NextRunTime"
0x6725  ldloc.2
0x6726  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x672b  ldloc.1
0x672c  ldstr    aIsrunning// "IsRunning"
0x6731  ldc.i4.1
0x6732  box      [mscorlib]System.Boolean
0x6737  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x673c  ldarg.1
0x673d  ldstr    aScalegroupmain_0// "ScaleGroupMaintenanceJobs"
0x6742  ldloc.0
0x6743  ldc.i4.1
0x6744  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x6749  dup
0x674a  ldc.i4.0
0x674b  ldloc.1
0x674c  stelem.ref
0x674d  ldc.i4   0xD9
0x6752  ldstr    aReleasestuckjo// "ReleaseStuckJobs"
0x6757  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x675c  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x6761  pop
0x6762  ret
```
