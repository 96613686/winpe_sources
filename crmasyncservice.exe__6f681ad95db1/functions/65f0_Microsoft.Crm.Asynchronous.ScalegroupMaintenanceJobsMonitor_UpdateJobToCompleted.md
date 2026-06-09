# Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::UpdateJobToCompleted

- ea: `0x65f0`
- end: `0x66d0`
- name: `Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::UpdateJobToCompleted`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x64c0`

## callees

- `0x65f0`
- `0x6e60`
- `0x6ee0`

## string_xrefs

- `0x66b3`: `UpdateJobToCompleted`
- `0x66b8`: `d:\dbs\sh\dccm2\1101_190851\cmd\34\src\Core\ObjectModel\Async\AsyncService\ScalegroupMaintenanceJobsMonitor.cs`

## pseudocode

```c

```

## disassembly

```asm
0x65f0  ldarg.1
0x65f1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::get_NextRuntime()
0x65f6  stloc.1
0x65f7  ldloca.s 1
0x65f9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x65fe  stloc.0
0x65ff  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x6604  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x6609  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService(valuetype [mscorlib]System.Guid)
0x660e  stloc.2
0x660f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x6614  stloc.3
0x6615  ldloc.3
0x6616  ldstr    aIsrunning// "IsRunning"
0x661b  ldc.i4.0
0x661c  box      [mscorlib]System.Boolean
0x6621  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6626  ldloc.3
0x6627  ldstr    aLastruntime// "LastRunTime"
0x662c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6631  box      [mscorlib]System.DateTime
0x6636  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x663b  ldloc.3
0x663c  ldstr    aNextruntime_0// "NextRunTime"
0x6641  ldloc.0
0x6642  box      [mscorlib]System.DateTime
0x6647  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x664c  ldloc.3
0x664d  ldstr    aModifiedon_0// "ModifiedOn"
0x6652  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6657  box      [mscorlib]System.DateTime
0x665c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6661  ldloc.3
0x6662  ldstr    aLastrunmessage// "LastRunMessage"
0x6667  ldarg.2
0x6668  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x666d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x6672  stloc.s  4
0x6674  ldloc.s  4
0x6676  ldstr    aId// "Id"
0x667b  ldarg.1
0x667c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::get_Id()
0x6681  box      [mscorlib]System.Guid
0x6686  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x668b  ldloc.s  4
0x668d  ldstr    aHost// "Host"
0x6692  call     string [mscorlib]System.Environment::get_MachineName()
0x6697  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x669c  ldloc.2
0x669d  ldstr    aScalegroupmain_0// "ScaleGroupMaintenanceJobs"
0x66a2  ldloc.3
0x66a3  ldc.i4.1
0x66a4  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x66a9  dup
0x66aa  ldc.i4.0
0x66ab  ldloc.s  4
0x66ad  stelem.ref
0x66ae  ldc.i4   0xCA
0x66b3  ldstr    aUpdatejobtocom// "UpdateJobToCompleted"
0x66b8  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x66bd  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x66c2  pop
0x66c3  leave.s  loc_66CF
0x66c5  ldloc.2
0x66c6  brfalse.s loc_66CE
0x66c8  ldloc.2
0x66c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66ce  endfinally
0x66cf  ret
```
