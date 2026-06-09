# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::GetLocalizedTemplate_0

- ea: `0x7260`
- end: `0x72ff`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::GetLocalizedTemplate_0`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x61e0`
- `0x7250`

## callees

- `0x7260`

## string_xrefs

- `0x72e6`: `LocalizedUserNotificationTemplate`
- `0x72f4`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationTemplateService.cs`
- `0x7261`: `templateName`
- `0x726c`: `templateVersion`
- `0x72ef`: `GetLocalizedTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x7260  ldarg.1
0x7261  ldstr    aTemplatename_0// "templateName"
0x7266  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x726b  ldarg.2
0x726c  ldstr    aTemplateversio// "templateVersion"
0x7271  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNegative(int32, string)
0x7276  ldarga.s 3
0x7278  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x727d  brfalse.s loc_7288
0x727f  ldarga.s 3
0x7281  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x7286  brtrue.s loc_7294
0x7288  ldarga.s 3
0x728a  ldc.i4   0x409
0x728f  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x7294  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x7299  stloc.0
0x729a  ldloc.0
0x729b  ldstr    aName// "Name"
0x72a0  ldarg.1
0x72a1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x72a6  ldloc.0
0x72a7  ldstr    aLocale// "Locale"
0x72ac  ldarga.s 3
0x72ae  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x72b3  box      [mscorlib]System.Int32
0x72b8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x72bd  ldloc.0
0x72be  ldstr    aVersion// "Version"
0x72c3  ldarg.2
0x72c4  box      [mscorlib]System.Int32
0x72c9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x72ce  ldloc.0
0x72cf  ldstr    aStatuscode// "StatusCode"
0x72d4  ldc.i4.1
0x72d5  box      [mscorlib]System.Int32
0x72da  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x72df  ldarg.s  4
0x72e1  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x72e6  ldstr    aLocalizedusern_0// "LocalizedUserNotificationTemplate"
0x72eb  ldnull
0x72ec  ldloc.0
0x72ed  ldc.i4.s 0x53
0x72ef  ldstr    aGetlocalizedte// "GetLocalizedTemplate"
0x72f4  ldstr    aDA1SSrcCrmlive_10// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x72f9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x72fe  ret
```
