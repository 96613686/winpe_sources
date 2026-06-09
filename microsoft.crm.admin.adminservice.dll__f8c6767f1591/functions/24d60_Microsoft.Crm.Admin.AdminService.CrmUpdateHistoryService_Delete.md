# Microsoft.Crm.Admin.AdminService.CrmUpdateHistoryService::Delete

- ea: `0x24d60`
- end: `0x24e09`
- name: `Microsoft.Crm.Admin.AdminService.CrmUpdateHistoryService::Delete`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x24d60`

## string_xrefs

- `0x24d9f`: `Delete`
- `0x24d92`: `UpdateHistory`
- `0x24da4`: `D:\a\1\s\src\CrmLive\Admin\UpdateHistory\CrmUpdateHistoryService.cs`
- `0x24d61`: `UpdateHistory identifier`
- `0x24d72`: `Deleting UpdateHistory, Id=({0})`
- `0x24db5`: `Deleted UpdateHistory, Id=({0})`
- `0x24de4`: `Exception deleting UpdateHistory, Id=({0} : {1})`

## pseudocode

```c

```

## disassembly

```asm
0x24d60  ldarg.1
0x24d61  ldstr    aUpdatehistoryI_0// "UpdateHistory identifier"
0x24d66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x24d6b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x24d70  ldc.i4.s 9
0x24d72  ldstr    aDeletingUpdate// "Deleting UpdateHistory, Id=({0})"
0x24d77  ldc.i4.1
0x24d78  newarr   [mscorlib]System.Object
0x24d7d  dup
0x24d7e  ldc.i4.0
0x24d7f  ldarg.1
0x24d80  box      [mscorlib]System.Guid
0x24d85  stelem.ref
0x24d86  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24d8b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x24d90  stloc.0
0x24d91  ldloc.0
0x24d92  ldstr    aUpdatehistory// "UpdateHistory"
0x24d97  ldarg.1
0x24d98  box      [mscorlib]System.Guid
0x24d9d  ldc.i4.s 0x62
0x24d9f  ldstr    aDelete// "Delete"
0x24da4  ldstr    aDA1SSrcCrmlive_49// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Updat"...
0x24da9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x24dae  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x24db3  ldc.i4.s 9
0x24db5  ldstr    aDeletedUpdateh// "Deleted UpdateHistory, Id=({0})"
0x24dba  ldc.i4.1
0x24dbb  newarr   [mscorlib]System.Object
0x24dc0  dup
0x24dc1  ldc.i4.0
0x24dc2  ldarg.1
0x24dc3  box      [mscorlib]System.Guid
0x24dc8  stelem.ref
0x24dc9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24dce  leave.s  loc_24DDA
0x24dd0  ldloc.0
0x24dd1  brfalse.s loc_24DD9
0x24dd3  ldloc.0
0x24dd4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24dd9  endfinally
0x24dda  leave.s  loc_24E08
0x24ddc  stloc.1
0x24ddd  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x24de2  ldc.i4.s 9
0x24de4  ldstr    aExceptionDelet_6// "Exception deleting UpdateHistory, Id=({"...
0x24de9  ldc.i4.2
0x24dea  newarr   [mscorlib]System.Object
0x24def  dup
0x24df0  ldc.i4.0
0x24df1  ldarg.1
0x24df2  box      [mscorlib]System.Guid
0x24df7  stelem.ref
0x24df8  dup
0x24df9  ldc.i4.1
0x24dfa  ldloc.1
0x24dfb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x24e00  stelem.ref
0x24e01  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24e06  rethrow
0x24e08  ret
```
