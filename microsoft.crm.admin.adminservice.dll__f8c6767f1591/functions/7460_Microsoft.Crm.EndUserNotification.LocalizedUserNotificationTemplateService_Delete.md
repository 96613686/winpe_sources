# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::Delete

- ea: `0x7460`
- end: `0x7532`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::Delete`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x7460`

## string_xrefs

- `0x74a8`: `Delete`
- `0x74f1`: `Delete`
- `0x7478`: `TemplateName`
- `0x74e5`: `LocalizedUserNotificationTemplate`
- `0x74ad`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationTemplateService.cs`
- `0x74f6`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationTemplateService.cs`
- `0x7461`: `templateName`
- `0x7508`: `LocalizedUserNotificationTemplate with name ={0} has child records in LocalizedUserNotification`

## pseudocode

```c

```

## disassembly

```asm
0x7460  ldarg.1
0x7461  ldstr    aTemplatename_0// "templateName"
0x7466  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x746b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x7470  stloc.0
0x7471  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x7476  stloc.1
0x7477  ldloc.1
0x7478  ldstr    aTemplatename// "TemplateName"
0x747d  ldarg.1
0x747e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x7483  ldc.i4.1
0x7484  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x7489  dup
0x748a  ldc.i4.0
0x748b  ldloc.1
0x748c  stelem.ref
0x748d  stloc.2
0x748e  ldloc.0
0x748f  ldstr    aLocalizedusern// "LocalizedUserNotification"
0x7494  ldc.i4.1
0x7495  newarr   [mscorlib]System.String
0x749a  dup
0x749b  ldc.i4.0
0x749c  ldstr    aId// "Id"
0x74a1  stelem.ref
0x74a2  ldloc.2
0x74a3  ldc.i4   0xA2
0x74a8  ldstr    aDelete// "Delete"
0x74ad  ldstr    aDA1SSrcCrmlive_10// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x74b2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x74b7  stloc.3
0x74b8  ldloc.3
0x74b9  brfalse.s loc_74C3
0x74bb  ldloc.3
0x74bc  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x74c1  brtrue.s loc_7503
0x74c3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x74c8  stloc.s  4
0x74ca  ldloc.s  4
0x74cc  ldstr    aName// "Name"
0x74d1  ldarg.1
0x74d2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x74d7  ldc.i4.1
0x74d8  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x74dd  dup
0x74de  ldc.i4.0
0x74df  ldloc.s  4
0x74e1  stelem.ref
0x74e2  stloc.s  5
0x74e4  ldloc.0
0x74e5  ldstr    aLocalizedusern_0// "LocalizedUserNotificationTemplate"
0x74ea  ldloc.s  5
0x74ec  ldc.i4   0xA9
0x74f1  ldstr    aDelete// "Delete"
0x74f6  ldstr    aDA1SSrcCrmlive_10// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x74fb  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x7500  pop
0x7501  leave.s  loc_7531
0x7503  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7508  ldstr    aLocalizedusern_1// "LocalizedUserNotificationTemplate with "...
0x750d  ldc.i4.1
0x750e  newarr   [mscorlib]System.Object
0x7513  dup
0x7514  ldc.i4.0
0x7515  ldarg.1
0x7516  stelem.ref
0x7517  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x751c  ldc.i4   0x80040216
0x7521  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x7526  throw
0x7527  ldloc.0
0x7528  brfalse.s loc_7530
0x752a  ldloc.0
0x752b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7530  endfinally
0x7531  ret
```
