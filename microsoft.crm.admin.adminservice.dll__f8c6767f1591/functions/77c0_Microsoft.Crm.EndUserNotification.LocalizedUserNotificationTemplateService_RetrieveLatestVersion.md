# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::RetrieveLatestVersion

- ea: `0x77c0`
- end: `0x7892`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::RetrieveLatestVersion`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5390`

## callees

- `0x77c0`

## string_xrefs

- `0x77f9`: `LocalizedUserNotificationTemplate`
- `0x7813`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationTemplateService.cs`
- `0x77c1`: `templateName`
- `0x7835`: `Could not find version number for template : `

## pseudocode

```c

```

## disassembly

```asm
0x77c0  ldarg.1
0x77c1  ldstr    aTemplatename_0// "templateName"
0x77c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x77cb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x77d0  stloc.0
0x77d1  ldloc.0
0x77d2  ldstr    aName// "Name"
0x77d7  ldarg.1
0x77d8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x77dd  ldloc.0
0x77de  ldstr    aLocale// "Locale"
0x77e3  ldc.i4   0x409
0x77e8  box      [mscorlib]System.Int32
0x77ed  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x77f2  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x77f7  stloc.3
0x77f8  ldloc.3
0x77f9  ldstr    aLocalizedusern_0// "LocalizedUserNotificationTemplate"
0x77fe  ldnull
0x77ff  ldc.i4.1
0x7800  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x7805  dup
0x7806  ldc.i4.0
0x7807  ldloc.0
0x7808  stelem.ref
0x7809  ldc.i4   0x128
0x780e  ldstr    aRetrievelatest_0// "RetrieveLatestVersion"
0x7813  ldstr    aDA1SSrcCrmlive_10// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x7818  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x781d  stloc.1
0x781e  leave.s  loc_782A
0x7820  ldloc.3
0x7821  brfalse.s loc_7829
0x7823  ldloc.3
0x7824  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7829  endfinally
0x782a  ldloc.1
0x782b  brfalse.s loc_7835
0x782d  ldloc.1
0x782e  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x7833  brtrue.s loc_7846
0x7835  ldstr    aCouldNotFindVe// "Could not find version number for templ"...
0x783a  ldarg.1
0x783b  call     string [mscorlib]System.String::Concat(string, string)
0x7840  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x7845  throw
0x7846  ldc.i4.0
0x7847  stloc.2
0x7848  ldloc.1
0x7849  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x784e  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x7853  stloc.s  4
0x7855  br.s     loc_7877
0x7857  ldloca.s 4
0x7859  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x785e  ldstr    aVersion// "Version"
0x7863  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x7868  unbox.any [mscorlib]System.Int32
0x786d  stloc.s  5
0x786f  ldloc.s  5
0x7871  ldloc.2
0x7872  ble.s    loc_7877
0x7874  ldloc.s  5
0x7876  stloc.2
0x7877  ldloca.s 4
0x7879  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x787e  brtrue.s loc_7857
0x7880  leave.s  loc_7890
0x7882  ldloca.s 4
0x7884  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x788a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x788f  endfinally
0x7890  ldloc.2
0x7891  ret
```
