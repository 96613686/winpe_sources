# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::TryUpdateNotificationStatusCodeInAllDatacenters

- ea: `0x5ab0`
- end: `0x5b46`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::TryUpdateNotificationStatusCodeInAllDatacenters`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x5370`
- `0x5ab0`
- `0x19e90`
- `0x1a300`
- `0x1a6b0`

## string_xrefs

- `0x5b22`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationService.cs`
- `0x5b1d`: `TryUpdateNotificationStatusCodeInAllDatacenters`

## pseudocode

```c

```

## disassembly

```asm
0x5ab0  ldarg.1
0x5ab1  ldstr    aNotificationid// "notificationId"
0x5ab6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x5abb  ldarg.2
0x5abc  box      [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationStatusCode
0x5ac1  ldstr    aStatuscode_0// "statusCode"
0x5ac6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5acb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x5ad0  stloc.0
0x5ad1  ldloc.0
0x5ad2  ldstr    aStatuscode// "StatusCode"
0x5ad7  ldarg.2
0x5ad8  box      [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationStatusCode
0x5add  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5ae2  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmDatacenterService::.ctor()
0x5ae7  callvirt instance class Microsoft.Crm.Admin.AdminService.DatacenterData[] Microsoft.Crm.Admin.AdminService.CrmDatacenterService::RetrieveMultiple()
0x5aec  stloc.1
0x5aed  ldc.i4.0
0x5aee  stloc.2
0x5aef  br.s     loc_5B3F
0x5af1  ldloc.1
0x5af2  ldloc.2
0x5af3  ldelem.ref
0x5af4  stloc.3
0x5af5  ldarg.0
0x5af6  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::GetDatabaseService()
0x5afb  stloc.s  4
0x5afd  ldloc.s  4
0x5aff  ldloc.3
0x5b00  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.DatacenterData::get_Id()
0x5b05  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::set_DatacenterId(valuetype [mscorlib]System.Guid)
0x5b0a  ldloc.s  4
0x5b0c  ldstr    aLocalizedusern// "LocalizedUserNotification"
0x5b11  ldarg.1
0x5b12  box      [mscorlib]System.Guid
0x5b17  ldloc.0
0x5b18  ldc.i4   0x191
0x5b1d  ldstr    aTryupdatenotif// "TryUpdateNotificationStatusCodeInAllDat"...
0x5b22  ldstr    aDA1SSrcCrmlive_9// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x5b27  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x5b2c  pop
0x5b2d  leave.s  loc_5B3B
0x5b2f  ldloc.s  4
0x5b31  brfalse.s loc_5B3A
0x5b33  ldloc.s  4
0x5b35  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b3a  endfinally
0x5b3b  ldloc.2
0x5b3c  ldc.i4.1
0x5b3d  add
0x5b3e  stloc.2
0x5b3f  ldloc.2
0x5b40  ldloc.1
0x5b41  ldlen
0x5b42  conv.i4
0x5b43  blt.s    loc_5AF1
0x5b45  ret
```
