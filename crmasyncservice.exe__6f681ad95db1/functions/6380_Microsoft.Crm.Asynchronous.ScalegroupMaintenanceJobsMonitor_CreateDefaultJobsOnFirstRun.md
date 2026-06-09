# Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::CreateDefaultJobsOnFirstRun

- ea: `0x6380`
- end: `0x63e2`
- name: `Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::CreateDefaultJobsOnFirstRun`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x6310`

## callees

- `0x6380`
- `0x69f0`

## string_xrefs

- `0x63cb`: `Exception while calling CreateDefaultJobsOnFirstRun : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6380  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x6385  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x638a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor(valuetype [mscorlib]System.Guid)
0x638f  stloc.0
0x6390  ldloc.0
0x6391  ldstr    aScalegroupmain_0// "ScaleGroupMaintenanceJobs"
0x6396  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::TableExistsInMetadata(string)
0x639b  brfalse.s loc_63B4
0x639d  ldarg.0
0x639e  ldstr    aScalegroupmain_1// "ScaleGroupMaintenanceJobs_lock"
0x63a3  ldnull
0x63a4  ldftn    void Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobCreator::CreateDefaultJobsOnFirstRun()
0x63aa  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x63af  call     instance void Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::ExecuteInConfigApplock(string appLockName, class [mscorlib]System.Action action)
0x63b4  leave.s  loc_63C0
0x63b6  ldloc.0
0x63b7  brfalse.s loc_63BF
0x63b9  ldloc.0
0x63ba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x63bf  endfinally
0x63c0  leave.s  loc_63E1
0x63c2  stloc.1
0x63c3  ldloc.1
0x63c4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x63c9  ldc.i4.s 0x15
0x63cb  ldstr    aExceptionWhile_6// "Exception while calling CreateDefaultJo"...
0x63d0  ldc.i4.1
0x63d1  newarr   [mscorlib]System.Object
0x63d6  dup
0x63d7  ldc.i4.0
0x63d8  ldloc.1
0x63d9  stelem.ref
0x63da  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x63df  leave.s  loc_63E1
0x63e1  ret
```
