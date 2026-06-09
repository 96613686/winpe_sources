# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::Create

- ea: `0x5390`
- end: `0x54db`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::Create`
- size: `331`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x5370`
- `0x5390`
- `0x6fa0`
- `0x77c0`
- `0x7940`
- `0x7b60`
- `0x7fb0`

## string_xrefs

- `0x5491`: `Create`
- `0x53ea`: `CreatedOn`
- `0x5438`: `TemplateName`
- `0x5496`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x5390  newobj   instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::.ctor()
0x5395  ldarg.s  4
0x5397  callvirt instance int32 Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::RetrieveLatestVersion(string templateName)
0x539c  stloc.0
0x539d  newobj   instance void Microsoft.Crm.EndUserNotification.SlugService::.ctor()
0x53a2  ldarg.s  4
0x53a4  ldloc.0
0x53a5  ldarg.s  5
0x53a7  ldarg.s  6
0x53a9  callvirt instance void Microsoft.Crm.EndUserNotification.SlugService::ValidateForCreate(string templateName, int32 version, string[] parameterNames, string[] parameterValues)
0x53ae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x53b3  stloc.1
0x53b4  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x53b9  stloc.2
0x53ba  ldloc.1
0x53bb  ldstr    aId// "Id"
0x53c0  ldloc.2
0x53c1  box      [mscorlib]System.Guid
0x53c6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x53cb  ldloc.1
0x53cc  ldstr    aDescription// "Description"
0x53d1  ldarg.1
0x53d2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x53d7  ldloc.1
0x53d8  ldstr    aStatuscode// "StatusCode"
0x53dd  ldarg.s  7
0x53df  box      [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationStatusCode
0x53e4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x53e9  ldloc.1
0x53ea  ldstr    aCreatedon// "CreatedOn"
0x53ef  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x53f4  box      [mscorlib]System.DateTime
0x53f9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x53fe  ldloc.1
0x53ff  ldstr    aModifiedon// "ModifiedOn"
0x5404  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5409  box      [mscorlib]System.DateTime
0x540e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5413  ldloc.1
0x5414  ldstr    aStartson// "StartsOn"
0x5419  ldarg.s  8
0x541b  box      [mscorlib]System.DateTime
0x5420  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5425  ldloc.1
0x5426  ldstr    aEndson// "EndsOn"
0x542b  ldarg.s  9
0x542d  box      [mscorlib]System.DateTime
0x5432  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5437  ldloc.1
0x5438  ldstr    aTemplatename// "TemplateName"
0x543d  ldarg.s  4
0x543f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5444  ldloc.1
0x5445  ldstr    aVersion// "Version"
0x544a  ldloc.0
0x544b  box      [mscorlib]System.Int32
0x5450  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5455  ldarg.2
0x5456  ldc.i4.1
0x5457  bne.un.s loc_546C
0x5459  ldloc.1
0x545a  ldstr    aOrganizationid_0// "OrganizationId"
0x545f  ldarg.3
0x5460  box      [mscorlib]System.Guid
0x5465  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x546a  br.s     loc_5481
0x546c  ldarg.2
0x546d  ldc.i4.2
0x546e  bne.un.s loc_5481
0x5470  ldloc.1
0x5471  ldstr    aScalegroupid_0// "ScaleGroupId"
0x5476  ldarg.3
0x5477  box      [mscorlib]System.Guid
0x547c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5481  ldarg.0
0x5482  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::GetDatabaseService()
0x5487  stloc.3
0x5488  ldloc.3
0x5489  ldstr    aLocalizedusern// "LocalizedUserNotification"
0x548e  ldloc.1
0x548f  ldc.i4.s 0x75
0x5491  ldstr    aCreate// "Create"
0x5496  ldstr    aDA1SSrcCrmlive_9// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x549b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x54a0  pop
0x54a1  leave.s  loc_54AD
0x54a3  ldloc.3
0x54a4  brfalse.s loc_54AC
0x54a6  ldloc.3
0x54a7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54ac  endfinally
0x54ad  ldc.i4.0
0x54ae  stloc.s  4
0x54b0  br.s     loc_54D1
0x54b2  ldarg.s  5
0x54b4  ldloc.s  4
0x54b6  ldelem.ref
0x54b7  stloc.s  5
0x54b9  ldarg.s  6
0x54bb  ldloc.s  4
0x54bd  ldelem.ref
0x54be  stloc.s  6
0x54c0  ldarg.0
0x54c1  ldloc.2
0x54c2  ldloc.s  5
0x54c4  ldloc.s  6
0x54c6  call     instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::CreateParameter(valuetype [mscorlib]System.Guid notificationId, string name, string value)
0x54cb  ldloc.s  4
0x54cd  ldc.i4.1
0x54ce  add
0x54cf  stloc.s  4
0x54d1  ldloc.s  4
0x54d3  ldarg.s  5
0x54d5  ldlen
0x54d6  conv.i4
0x54d7  blt.s    loc_54B2
0x54d9  ldloc.2
0x54da  ret
```
