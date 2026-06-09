# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::RetrieveSlugXml

- ea: `0x78a0`
- end: `0x792c`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::RetrieveSlugXml`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5df0`
- `0x7ce0`

## callees

- `0x78a0`

## string_xrefs

- `0x78f3`: `LocalizedUserNotificationTemplate`
- `0x7904`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationTemplateService.cs`
- `0x78a1`: `templateName`
- `0x78ff`: `RetrieveSlugXml`
- `0x7911`: `Template not found`
- `0x791c`: `SlugXml`

## pseudocode

```c

```

## disassembly

```asm
0x78a0  ldarg.1
0x78a1  ldstr    aTemplatename_0// "templateName"
0x78a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x78ab  ldarg.2
0x78ac  ldstr    aVersion_0// "version"
0x78b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNegative(int32, string)
0x78b6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x78bb  stloc.0
0x78bc  ldloc.0
0x78bd  ldstr    aName// "Name"
0x78c2  ldarg.1
0x78c3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x78c8  ldloc.0
0x78c9  ldstr    aVersion// "Version"
0x78ce  ldarg.2
0x78cf  box      [mscorlib]System.Int32
0x78d4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x78d9  ldloc.0
0x78da  ldstr    aLocale// "Locale"
0x78df  ldc.i4   0x409
0x78e4  box      [mscorlib]System.Int32
0x78e9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x78ee  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x78f3  ldstr    aLocalizedusern_0// "LocalizedUserNotificationTemplate"
0x78f8  ldnull
0x78f9  ldloc.0
0x78fa  ldc.i4   0x14B
0x78ff  ldstr    aRetrieveslugxm// "RetrieveSlugXml"
0x7904  ldstr    aDA1SSrcCrmlive_10// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x7909  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x790e  dup
0x790f  brtrue.s loc_791C
0x7911  ldstr    aTemplateNotFou// "Template not found"
0x7916  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x791b  throw
0x791c  ldstr    aSlugxml// "SlugXml"
0x7921  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x7926  castclass [mscorlib]System.String
0x792b  ret
```
