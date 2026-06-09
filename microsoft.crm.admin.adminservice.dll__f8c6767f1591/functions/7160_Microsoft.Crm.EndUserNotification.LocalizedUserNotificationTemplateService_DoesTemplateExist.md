# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::DoesTemplateExist

- ea: `0x7160`
- end: `0x71d6`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::DoesTemplateExist`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x7160`

## string_xrefs

- `0x7199`: `LocalizedUserNotificationTemplate`
- `0x71ab`: `DoesTemplateExist`
- `0x71b0`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationTemplateService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x7160  ldarg.1
0x7161  ldstr    aName_0// "name"
0x7166  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x716b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x7170  stloc.1
0x7171  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x7176  stloc.2
0x7177  ldloc.2
0x7178  ldstr    aName// "Name"
0x717d  ldarg.1
0x717e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x7183  ldloc.2
0x7184  ldstr    aLocale// "Locale"
0x7189  ldc.i4   0x409
0x718e  box      [mscorlib]System.Int32
0x7193  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x7198  ldloc.1
0x7199  ldstr    aLocalizedusern_0// "LocalizedUserNotificationTemplate"
0x719e  ldnull
0x719f  ldc.i4.1
0x71a0  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x71a5  dup
0x71a6  ldc.i4.0
0x71a7  ldloc.2
0x71a8  stelem.ref
0x71a9  ldc.i4.s 0x21
0x71ab  ldstr    aDoestemplateex// "DoesTemplateExist"
0x71b0  ldstr    aDA1SSrcCrmlive_10// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x71b5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x71ba  stloc.0
0x71bb  leave.s  loc_71C7
0x71bd  ldloc.1
0x71be  brfalse.s loc_71C6
0x71c0  ldloc.1
0x71c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x71c6  endfinally
0x71c7  ldloc.0
0x71c8  brfalse.s loc_71D2
0x71ca  ldloc.0
0x71cb  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x71d0  brtrue.s loc_71D4
0x71d2  ldc.i4.0
0x71d3  ret
0x71d4  ldc.i4.1
0x71d5  ret
```
