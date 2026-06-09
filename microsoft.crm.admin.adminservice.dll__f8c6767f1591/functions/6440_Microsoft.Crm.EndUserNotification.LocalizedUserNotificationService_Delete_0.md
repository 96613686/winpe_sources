# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::Delete_0

- ea: `0x6440`
- end: `0x64c7`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::Delete_0`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x5370`
- `0x6440`
- `0x64d0`
- `0x19e90`
- `0x1a300`
- `0x1a6b0`

## string_xrefs

- `0x6490`: `Delete`
- `0x6495`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x6440  ldarg.1
0x6441  ldstr    aNotificationid// "notificationId"
0x6446  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x644b  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmDatacenterService::.ctor()
0x6450  callvirt instance class Microsoft.Crm.Admin.AdminService.DatacenterData[] Microsoft.Crm.Admin.AdminService.CrmDatacenterService::RetrieveMultiple()
0x6455  stloc.0
0x6456  ldc.i4.0
0x6457  stloc.1
0x6458  br.s     loc_64C0
0x645a  ldloc.0
0x645b  ldloc.1
0x645c  ldelem.ref
0x645d  stloc.2
0x645e  ldarg.0
0x645f  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::GetDatabaseService()
0x6464  stloc.3
0x6465  ldloc.3
0x6466  ldloc.2
0x6467  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.DatacenterData::get_Id()
0x646c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::set_DatacenterId(valuetype [mscorlib]System.Guid)
0x6471  ldloc.3
0x6472  ldstr    aLocalizedusern// "LocalizedUserNotification"
0x6477  ldarg.1
0x6478  box      [mscorlib]System.Guid
0x647d  ldc.i4.1
0x647e  newarr   [mscorlib]System.String
0x6483  dup
0x6484  ldc.i4.0
0x6485  ldstr    aStatuscode// "StatusCode"
0x648a  stelem.ref
0x648b  ldc.i4   0x364
0x6490  ldstr    aDelete// "Delete"
0x6495  ldstr    aDA1SSrcCrmlive_9// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x649a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x649f  stloc.s  4
0x64a1  ldloc.s  4
0x64a3  brfalse.s loc_64B0
0x64a5  ldarg.1
0x64a6  ldloc.s  4
0x64a8  ldloc.3
0x64a9  call     valuetype [mscorlib]System.Guid Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::PrivateDelete(valuetype [mscorlib]System.Guid notificationId, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag notification, class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService service)
0x64ae  starg.s  1
0x64b0  leave.s  loc_64BC
0x64b2  ldloc.3
0x64b3  brfalse.s loc_64BB
0x64b5  ldloc.3
0x64b6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64bb  endfinally
0x64bc  ldloc.1
0x64bd  ldc.i4.1
0x64be  add
0x64bf  stloc.1
0x64c0  ldloc.1
0x64c1  ldloc.0
0x64c2  ldlen
0x64c3  conv.i4
0x64c4  blt.s    loc_645A
0x64c6  ret
```
