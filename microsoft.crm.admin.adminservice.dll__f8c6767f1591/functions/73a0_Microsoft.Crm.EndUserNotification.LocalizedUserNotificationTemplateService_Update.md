# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::Update

- ea: `0x73a0`
- end: `0x7451`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::Update`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x4cf0`
- `0x73a0`

## string_xrefs

- `0x7408`: `Update`
- `0x73b7`: `TemplateXml`
- `0x73c4`: `TemplateXml`
- `0x73fc`: `LocalizedUserNotificationTemplate`
- `0x740d`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationTemplateService.cs`
- `0x73a1`: `templateName`
- `0x73ac`: `updatedProperties`
- `0x7420`: `EndUserNotificationTemplate with name {0} does not exist.`

## pseudocode

```c

```

## disassembly

```asm
0x73a0  ldarg.1
0x73a1  ldstr    aTemplatename_0// "templateName"
0x73a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x73ab  ldarg.2
0x73ac  ldstr    aUpdatedpropert// "updatedProperties"
0x73b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x73b6  ldarg.2
0x73b7  ldstr    aTemplatexml_0// "TemplateXml"
0x73bc  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x73c1  brfalse.s loc_73D8
0x73c3  ldarg.2
0x73c4  ldstr    aTemplatexml_0// "TemplateXml"
0x73c9  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x73ce  castclass [mscorlib]System.String
0x73d3  call     void Microsoft.Crm.EndUserNotification.EndUserNotificationTemplateSchemaUtility::ValidateTemplateXml(string templateXml)
0x73d8  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x73dd  stloc.0
0x73de  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x73e3  stloc.1
0x73e4  ldloc.1
0x73e5  ldstr    aName// "Name"
0x73ea  ldarg.1
0x73eb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x73f0  ldc.i4.1
0x73f1  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x73f6  dup
0x73f7  ldc.i4.0
0x73f8  ldloc.1
0x73f9  stelem.ref
0x73fa  stloc.2
0x73fb  ldloc.0
0x73fc  ldstr    aLocalizedusern_0// "LocalizedUserNotificationTemplate"
0x7401  ldarg.2
0x7402  ldloc.2
0x7403  ldc.i4   0x8A
0x7408  ldstr    aUpdate// "Update"
0x740d  ldstr    aDA1SSrcCrmlive_10// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x7412  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x7417  stloc.3
0x7418  ldloc.3
0x7419  brtrue.s loc_743F
0x741b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7420  ldstr    aEndusernotific_5// "EndUserNotificationTemplate with name {"...
0x7425  ldc.i4.1
0x7426  newarr   [mscorlib]System.Object
0x742b  dup
0x742c  ldc.i4.0
0x742d  ldarg.1
0x742e  stelem.ref
0x742f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7434  ldc.i4   0x80040217
0x7439  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x743e  throw
0x743f  ldloc.3
0x7440  stloc.s  4
0x7442  leave.s  loc_744E
0x7444  ldloc.0
0x7445  brfalse.s loc_744D
0x7447  ldloc.0
0x7448  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x744d  endfinally
0x744e  ldloc.s  4
0x7450  ret
```
