# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::Create

- ea: `0x7300`
- end: `0x7392`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::Create`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4cf0`
- `0x7300`

## string_xrefs

- `0x736f`: `Create`
- `0x732a`: `TemplateXml`
- `0x7337`: `TemplateXml`
- `0x7367`: `LocalizedUserNotificationTemplate`
- `0x7374`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationTemplateService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x7300  ldarg.1
0x7301  ldstr    aProperties// "properties"
0x7306  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x730b  ldarg.1
0x730c  ldstr    aStatuscode// "StatusCode"
0x7311  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x7316  brtrue.s loc_7329
0x7318  ldarg.1
0x7319  ldstr    aStatuscode// "StatusCode"
0x731e  ldc.i4.1
0x731f  box      [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationTemplateStatusCode
0x7324  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x7329  ldarg.1
0x732a  ldstr    aTemplatexml_0// "TemplateXml"
0x732f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x7334  brfalse.s loc_734B
0x7336  ldarg.1
0x7337  ldstr    aTemplatexml_0// "TemplateXml"
0x733c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x7341  castclass [mscorlib]System.String
0x7346  call     void Microsoft.Crm.EndUserNotification.EndUserNotificationTemplateSchemaUtility::ValidateTemplateXml(string templateXml)
0x734b  ldarg.1
0x734c  ldstr    aModifiedon// "ModifiedOn"
0x7351  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x7356  box      [mscorlib]System.DateTime
0x735b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x7360  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x7365  stloc.0
0x7366  ldloc.0
0x7367  ldstr    aLocalizedusern_0// "LocalizedUserNotificationTemplate"
0x736c  ldarg.1
0x736d  ldc.i4.s 0x6F
0x736f  ldstr    aCreate// "Create"
0x7374  ldstr    aDA1SSrcCrmlive_10// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x7379  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x737e  unbox.any [mscorlib]System.Guid
0x7383  stloc.1
0x7384  leave.s  loc_7390
0x7386  ldloc.0
0x7387  brfalse.s loc_738F
0x7389  ldloc.0
0x738a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x738f  endfinally
0x7390  ldloc.1
0x7391  ret
```
