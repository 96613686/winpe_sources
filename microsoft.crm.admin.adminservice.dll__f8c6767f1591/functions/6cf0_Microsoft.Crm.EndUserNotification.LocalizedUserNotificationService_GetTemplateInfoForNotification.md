# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::GetTemplateInfoForNotification

- ea: `0x6cf0`
- end: `0x6d80`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::GetTemplateInfoForNotification`
- size: `144`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5c40`
- `0x5df0`
- `0x6290`

## callees

- `0x6cf0`

## string_xrefs

- `0x6cf8`: `TemplateName`
- `0x6d65`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationService.cs`
- `0x6d60`: `GetTemplateInfoForNotification`

## pseudocode

```c

```

## disassembly

```asm
0x6cf0  ldc.i4.2
0x6cf1  newarr   [mscorlib]System.String
0x6cf6  dup
0x6cf7  ldc.i4.0
0x6cf8  ldstr    aTemplatename// "TemplateName"
0x6cfd  stelem.ref
0x6cfe  dup
0x6cff  ldc.i4.1
0x6d00  ldstr    aVersion// "Version"
0x6d05  stelem.ref
0x6d06  stloc.0
0x6d07  ldc.i4.1
0x6d08  stloc.1
0x6d09  ldloc.0
0x6d0a  stloc.3
0x6d0b  ldc.i4.0
0x6d0c  stloc.s  4
0x6d0e  br.s     loc_6D2A
0x6d10  ldloc.3
0x6d11  ldloc.s  4
0x6d13  ldelem.ref
0x6d14  stloc.s  5
0x6d16  ldarg.0
0x6d17  ldloc.s  5
0x6d19  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x6d1e  brtrue.s loc_6D24
0x6d20  ldc.i4.0
0x6d21  stloc.1
0x6d22  br.s     loc_6D31
0x6d24  ldloc.s  4
0x6d26  ldc.i4.1
0x6d27  add
0x6d28  stloc.s  4
0x6d2a  ldloc.s  4
0x6d2c  ldloc.3
0x6d2d  ldlen
0x6d2e  conv.i4
0x6d2f  blt.s    loc_6D10
0x6d31  ldarg.0
0x6d32  stloc.2
0x6d33  ldloc.1
0x6d34  brtrue.s loc_6D7E
0x6d36  ldarg.1
0x6d37  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x6d3c  stloc.s  6
0x6d3e  ldloc.s  6
0x6d40  ldstr    aLocalizedusern// "LocalizedUserNotification"
0x6d45  ldarg.0
0x6d46  ldstr    aId// "Id"
0x6d4b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x6d50  unbox.any [mscorlib]System.Guid
0x6d55  box      [mscorlib]System.Guid
0x6d5a  ldloc.0
0x6d5b  ldc.i4   0x4B1
0x6d60  ldstr    aGettemplateinf// "GetTemplateInfoForNotification"
0x6d65  ldstr    aDA1SSrcCrmlive_9// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x6d6a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x6d6f  stloc.2
0x6d70  leave.s  loc_6D7E
0x6d72  ldloc.s  6
0x6d74  brfalse.s loc_6D7D
0x6d76  ldloc.s  6
0x6d78  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d7d  endfinally
0x6d7e  ldloc.2
0x6d7f  ret
```
