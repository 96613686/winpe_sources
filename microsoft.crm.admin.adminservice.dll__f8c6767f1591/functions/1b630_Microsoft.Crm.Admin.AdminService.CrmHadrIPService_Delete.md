# Microsoft.Crm.Admin.AdminService.CrmHadrIPService::Delete

- ea: `0x1b630`
- end: `0x1b6a6`
- name: `Microsoft.Crm.Admin.AdminService.CrmHadrIPService::Delete`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1b630`
- `0x1bb40`

## string_xrefs

- `0x1b66a`: `Delete`
- `0x1b66f`: `D:\a\1\s\src\CrmLive\Admin\HadrIPs\HadrIPService.cs`
- `0x1b680`: `Deleted HadrIP, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x1b630  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1b635  ldc.i4.s 9
0x1b637  ldstr    aDeletingHadrip// "Deleting HadrIP, IPAddress=({0})"
0x1b63c  ldc.i4.1
0x1b63d  newarr   [mscorlib]System.Object
0x1b642  dup
0x1b643  ldc.i4.0
0x1b644  ldarg.1
0x1b645  stelem.ref
0x1b646  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b64b  ldarg.0
0x1b64c  ldarg.1
0x1b64d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmHadrIPService::GetIdFromAddress(string ipAddress)
0x1b652  stloc.0
0x1b653  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1b658  stloc.1
0x1b659  ldloc.1
0x1b65a  ldstr    aHadrips// "HadrIPs"
0x1b65f  ldloc.0
0x1b660  box      [mscorlib]System.Guid
0x1b665  ldc.i4   0xB6
0x1b66a  ldstr    aDelete// "Delete"
0x1b66f  ldstr    aDA1SSrcCrmlive_37// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\HadrI"...
0x1b674  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x1b679  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1b67e  ldc.i4.s 9
0x1b680  ldstr    aDeletedHadripI// "Deleted HadrIP, Id=({0})"
0x1b685  ldc.i4.1
0x1b686  newarr   [mscorlib]System.Object
0x1b68b  dup
0x1b68c  ldc.i4.0
0x1b68d  ldloc.0
0x1b68e  box      [mscorlib]System.Guid
0x1b693  stelem.ref
0x1b694  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b699  leave.s  loc_1B6A5
0x1b69b  ldloc.1
0x1b69c  brfalse.s loc_1B6A4
0x1b69e  ldloc.1
0x1b69f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b6a4  endfinally
0x1b6a5  ret
```
