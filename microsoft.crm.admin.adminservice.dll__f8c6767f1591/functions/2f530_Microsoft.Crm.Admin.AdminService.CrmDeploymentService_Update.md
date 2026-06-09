# Microsoft.Crm.Admin.AdminService.CrmDeploymentService::Update

- ea: `0x2f530`
- end: `0x2f5e9`
- name: `Microsoft.Crm.Admin.AdminService.CrmDeploymentService::Update`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2f610`
- `0x2f750`

## callees

- `0x2f530`

## string_xrefs

- `0x2f57e`: `Update`
- `0x2f583`: `D:\a\1\s\src\CrmLive\Admin\Deployment\CrmDeploymentService.cs`
- `0x2f5a1`: `Updated Deployment, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x2f530  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2f535  ldc.i4.s 0x14
0x2f537  ldstr    aUpdatingDeploy// "Updating Deployment, Id=({0})"
0x2f53c  ldc.i4.1
0x2f53d  newarr   [mscorlib]System.Object
0x2f542  dup
0x2f543  ldc.i4.0
0x2f544  ldarg.1
0x2f545  box      [mscorlib]System.Guid
0x2f54a  stelem.ref
0x2f54b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f550  ldarg.1
0x2f551  ldstr    aDeploymentIden// "Deployment identifier"
0x2f556  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2f55b  ldarg.2
0x2f55c  ldstr    aDeploymentProp// "Deployment property bag"
0x2f561  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2f566  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2f56b  stloc.0
0x2f56c  ldloc.0
0x2f56d  ldstr    aDeployment// "Deployment"
0x2f572  ldarg.1
0x2f573  box      [mscorlib]System.Guid
0x2f578  ldarg.2
0x2f579  ldc.i4   0x265
0x2f57e  ldstr    aUpdate// "Update"
0x2f583  ldstr    aDA1SSrcCrmlive_58// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Deplo"...
0x2f588  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x2f58d  pop
0x2f58e  leave.s  loc_2F59A
0x2f590  ldloc.0
0x2f591  brfalse.s loc_2F599
0x2f593  ldloc.0
0x2f594  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f599  endfinally
0x2f59a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2f59f  ldc.i4.s 0x14
0x2f5a1  ldstr    aUpdatedDeploym// "Updated Deployment, Id=({0})"
0x2f5a6  ldc.i4.1
0x2f5a7  newarr   [mscorlib]System.Object
0x2f5ac  dup
0x2f5ad  ldc.i4.0
0x2f5ae  ldarg.1
0x2f5af  box      [mscorlib]System.Guid
0x2f5b4  stelem.ref
0x2f5b5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f5ba  leave.s  loc_2F5E8
0x2f5bc  stloc.1
0x2f5bd  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2f5c2  ldc.i4.s 0x14
0x2f5c4  ldstr    aExceptionUpdat_2// "Exception Updating Deployment, Id=({0} "...
0x2f5c9  ldc.i4.2
0x2f5ca  newarr   [mscorlib]System.Object
0x2f5cf  dup
0x2f5d0  ldc.i4.0
0x2f5d1  ldarg.1
0x2f5d2  box      [mscorlib]System.Guid
0x2f5d7  stelem.ref
0x2f5d8  dup
0x2f5d9  ldc.i4.1
0x2f5da  ldloc.1
0x2f5db  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2f5e0  stelem.ref
0x2f5e1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f5e6  rethrow
0x2f5e8  ret
```
