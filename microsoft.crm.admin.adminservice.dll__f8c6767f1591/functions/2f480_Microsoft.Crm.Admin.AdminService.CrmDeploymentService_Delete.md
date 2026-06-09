# Microsoft.Crm.Admin.AdminService.CrmDeploymentService::Delete

- ea: `0x2f480`
- end: `0x2f52c`
- name: `Microsoft.Crm.Admin.AdminService.CrmDeploymentService::Delete`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x2f480`

## string_xrefs

- `0x2f4c2`: `Delete`
- `0x2f4c7`: `D:\a\1\s\src\CrmLive\Admin\Deployment\CrmDeploymentService.cs`
- `0x2f4e4`: `Deleted Deployment, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x2f480  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2f485  ldc.i4.s 0x14
0x2f487  ldstr    aDeletingDeploy// "Deleting Deployment, Id=({0})"
0x2f48c  ldc.i4.1
0x2f48d  newarr   [mscorlib]System.Object
0x2f492  dup
0x2f493  ldc.i4.0
0x2f494  ldarg.1
0x2f495  box      [mscorlib]System.Guid
0x2f49a  stelem.ref
0x2f49b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f4a0  ldarg.1
0x2f4a1  ldstr    aDeploymentIden// "Deployment identifier"
0x2f4a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2f4ab  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2f4b0  stloc.0
0x2f4b1  ldloc.0
0x2f4b2  ldstr    aDeployment// "Deployment"
0x2f4b7  ldarg.1
0x2f4b8  box      [mscorlib]System.Guid
0x2f4bd  ldc.i4   0x247
0x2f4c2  ldstr    aDelete// "Delete"
0x2f4c7  ldstr    aDA1SSrcCrmlive_58// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Deplo"...
0x2f4cc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x2f4d1  leave.s  loc_2F4DD
0x2f4d3  ldloc.0
0x2f4d4  brfalse.s loc_2F4DC
0x2f4d6  ldloc.0
0x2f4d7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f4dc  endfinally
0x2f4dd  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2f4e2  ldc.i4.s 0x14
0x2f4e4  ldstr    aDeletedDeploym// "Deleted Deployment, Id=({0})"
0x2f4e9  ldc.i4.1
0x2f4ea  newarr   [mscorlib]System.Object
0x2f4ef  dup
0x2f4f0  ldc.i4.0
0x2f4f1  ldarg.1
0x2f4f2  box      [mscorlib]System.Guid
0x2f4f7  stelem.ref
0x2f4f8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f4fd  leave.s  loc_2F52B
0x2f4ff  stloc.1
0x2f500  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2f505  ldc.i4.s 0x14
0x2f507  ldstr    aExceptionDelet_8// "Exception deleting Deployment, Id=({0} "...
0x2f50c  ldc.i4.2
0x2f50d  newarr   [mscorlib]System.Object
0x2f512  dup
0x2f513  ldc.i4.0
0x2f514  ldarg.1
0x2f515  box      [mscorlib]System.Guid
0x2f51a  stelem.ref
0x2f51b  dup
0x2f51c  ldc.i4.1
0x2f51d  ldloc.1
0x2f51e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2f523  stelem.ref
0x2f524  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f529  rethrow
0x2f52b  ret
```
