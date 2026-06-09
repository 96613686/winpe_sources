# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::RetrieveTemplateNames

- ea: `0x76e0`
- end: `0x77c0`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::RetrieveTemplateNames`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5930`

## callees

- `0x76e0`

## string_xrefs

- `0x7713`: `LocalizedUserNotificationTemplate`
- `0x772d`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationTemplateService.cs`
- `0x7728`: `RetrieveTemplateNames`

## pseudocode

```c

```

## disassembly

```asm
0x76e0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x76e5  stloc.0
0x76e6  ldloc.0
0x76e7  ldstr    aNotificationty// "NotificationType"
0x76ec  ldarg.1
0x76ed  box      [mscorlib]System.Int32
0x76f2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x76f7  ldloc.0
0x76f8  ldstr    aLocale// "Locale"
0x76fd  ldc.i4   0x409
0x7702  box      [mscorlib]System.Int32
0x7707  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x770c  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x7711  stloc.3
0x7712  ldloc.3
0x7713  ldstr    aLocalizedusern_0// "LocalizedUserNotificationTemplate"
0x7718  ldnull
0x7719  ldc.i4.1
0x771a  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x771f  dup
0x7720  ldc.i4.0
0x7721  ldloc.0
0x7722  stelem.ref
0x7723  ldc.i4   0x107
0x7728  ldstr    aRetrievetempla// "RetrieveTemplateNames"
0x772d  ldstr    aDA1SSrcCrmlive_10// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x7732  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x7737  stloc.1
0x7738  leave.s  loc_7744
0x773a  ldloc.3
0x773b  brfalse.s loc_7743
0x773d  ldloc.3
0x773e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7743  endfinally
0x7744  ldloc.1
0x7745  brtrue.s loc_774E
0x7747  ldc.i4.0
0x7748  newarr   [mscorlib]System.String
0x774d  ret
0x774e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x7753  stloc.2
0x7754  ldloc.1
0x7755  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x775a  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x775f  stloc.s  4
0x7761  br.s     loc_77A0
0x7763  ldloca.s 4
0x7765  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x776a  stloc.s  5
0x776c  ldloc.s  5
0x776e  ldstr    aName// "Name"
0x7773  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x7778  castclass [mscorlib]System.String
0x777d  stloc.s  6
0x777f  ldloc.2
0x7780  ldloc.s  6
0x7782  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x7787  brtrue.s loc_77A0
0x7789  ldloc.2
0x778a  ldloc.s  5
0x778c  ldstr    aName// "Name"
0x7791  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x7796  castclass [mscorlib]System.String
0x779b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x77a0  ldloca.s 4
0x77a2  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x77a7  brtrue.s loc_7763
0x77a9  leave.s  loc_77B9
0x77ab  ldloca.s 4
0x77ad  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x77b3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x77b8  endfinally
0x77b9  ldloc.2
0x77ba  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x77bf  ret
```
