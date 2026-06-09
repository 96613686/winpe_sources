# Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::UpdateReadyJobsToExecuting

- ea: `0x6930`
- end: `0x69e5`
- name: `Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::UpdateReadyJobsToExecuting`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6430`

## callees

- `0x6930`
- `0x6e60`
- `0x6ee0`

## string_xrefs

- `0x69c2`: `d:\dbs\sh\dccm2\1101_190851\cmd\34\src\Core\ObjectModel\Async\AsyncService\ScalegroupMaintenanceJobsMonitor.cs`
- `0x69bd`: `UpdateReadyJobsToExecuting`

## pseudocode

```c

```

## disassembly

```asm
0x6930  ldarg.1
0x6931  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData>::GetEnumerator()
0x6936  stloc.0
0x6937  br       loc_69CD
0x693c  ldloc.0
0x693d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData>::get_Current()
0x6942  stloc.1
0x6943  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x6948  stloc.2
0x6949  ldloc.2
0x694a  ldstr    aIsrunning// "IsRunning"
0x694f  ldc.i4.1
0x6950  box      [mscorlib]System.Boolean
0x6955  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x695a  ldloc.2
0x695b  ldstr    aModifiedon_0// "ModifiedOn"
0x6960  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6965  box      [mscorlib]System.DateTime
0x696a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x696f  ldloc.2
0x6970  ldstr    aHost// "Host"
0x6975  call     string [mscorlib]System.Environment::get_MachineName()
0x697a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x697f  ldloc.2
0x6980  ldstr    aHostlocked// "HostLocked"
0x6985  ldc.i4.1
0x6986  box      [mscorlib]System.Boolean
0x698b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6990  ldloc.2
0x6991  ldstr    aNextruntime_0// "NextRunTime"
0x6996  ldloc.1
0x6997  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::get_NextRuntime()
0x699c  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x69a1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x69a6  ldarg.2
0x69a7  ldstr    aScalegroupmain_0// "ScaleGroupMaintenanceJobs"
0x69ac  ldloc.1
0x69ad  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::get_Id()
0x69b2  box      [mscorlib]System.Guid
0x69b7  ldloc.2
0x69b8  ldc.i4   0x11B
0x69bd  ldstr    aUpdatereadyjob// "UpdateReadyJobsToExecuting"
0x69c2  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x69c7  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x69cc  pop
0x69cd  ldloc.0
0x69ce  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x69d3  brtrue   loc_693C
0x69d8  leave.s  loc_69E4
0x69da  ldloc.0
0x69db  brfalse.s loc_69E3
0x69dd  ldloc.0
0x69de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69e3  endfinally
0x69e4  ret
```
