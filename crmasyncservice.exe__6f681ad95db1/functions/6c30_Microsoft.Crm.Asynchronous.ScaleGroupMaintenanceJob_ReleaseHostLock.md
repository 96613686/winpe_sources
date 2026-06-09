# Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJob::ReleaseHostLock

- ea: `0x6c30`
- end: `0x6cb3`
- name: `Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJob::ReleaseHostLock`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x6c30`
- `0x6cc0`

## string_xrefs

- `0x6c9b`: `d:\dbs\sh\dccm2\1101_190851\cmd\34\src\Core\ObjectModel\Async\AsyncService\ScalegroupMaintenanceJobs\ScalegroupMaintenanceJob.cs`

## pseudocode

```c

```

## disassembly

```asm
0x6c30  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x6c35  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x6c3a  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService(valuetype [mscorlib]System.Guid)
0x6c3f  stloc.0
0x6c40  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x6c45  stloc.1
0x6c46  ldloc.1
0x6c47  ldstr    aHostlocked// "HostLocked"
0x6c4c  ldc.i4.0
0x6c4d  box      [mscorlib]System.Boolean
0x6c52  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6c57  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x6c5c  stloc.2
0x6c5d  ldloc.2
0x6c5e  ldstr    aId// "Id"
0x6c63  ldarg.0
0x6c64  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJob::get_JobId()
0x6c69  box      [mscorlib]System.Guid
0x6c6e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6c73  ldloc.2
0x6c74  ldstr    aHost// "Host"
0x6c79  call     string [mscorlib]System.Environment::get_MachineName()
0x6c7e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6c83  ldloc.0
0x6c84  ldstr    aScalegroupmain_0// "ScaleGroupMaintenanceJobs"
0x6c89  ldloc.1
0x6c8a  ldc.i4.1
0x6c8b  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x6c90  dup
0x6c91  ldc.i4.0
0x6c92  ldloc.2
0x6c93  stelem.ref
0x6c94  ldc.i4.s 0x75
0x6c96  ldstr    aReleasehostloc// "ReleaseHostLock"
0x6c9b  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x6ca0  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x6ca5  pop
0x6ca6  leave.s  loc_6CB2
0x6ca8  ldloc.0
0x6ca9  brfalse.s loc_6CB1
0x6cab  ldloc.0
0x6cac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6cb1  endfinally
0x6cb2  ret
```
