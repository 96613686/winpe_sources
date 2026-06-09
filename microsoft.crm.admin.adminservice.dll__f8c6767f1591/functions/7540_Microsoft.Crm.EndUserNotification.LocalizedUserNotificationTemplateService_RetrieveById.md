# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::RetrieveById

- ea: `0x7540`
- end: `0x7581`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::RetrieveById`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x7540`

## string_xrefs

- `0x7552`: `LocalizedUserNotificationTemplate`
- `0x7568`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationTemplateService.cs`
- `0x7541`: `templateId`

## pseudocode

```c

```

## disassembly

```asm
0x7540  ldarg.1
0x7541  ldstr    aTemplateid// "templateId"
0x7546  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x754b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x7550  stloc.0
0x7551  ldloc.0
0x7552  ldstr    aLocalizedusern_0// "LocalizedUserNotificationTemplate"
0x7557  ldarg.1
0x7558  box      [mscorlib]System.Guid
0x755d  ldarg.2
0x755e  ldc.i4   0xBF
0x7563  ldstr    aRetrievebyid// "RetrieveById"
0x7568  ldstr    aDA1SSrcCrmlive_10// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x756d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x7572  stloc.1
0x7573  leave.s  loc_757F
0x7575  ldloc.0
0x7576  brfalse.s loc_757E
0x7578  ldloc.0
0x7579  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x757e  endfinally
0x757f  ldloc.1
0x7580  ret
```
