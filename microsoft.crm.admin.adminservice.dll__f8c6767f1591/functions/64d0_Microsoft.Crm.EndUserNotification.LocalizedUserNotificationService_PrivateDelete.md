# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::PrivateDelete

- ea: `0x64d0`
- end: `0x65c9`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::PrivateDelete`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6360`
- `0x6440`

## callees

- `0x64d0`
- `0x65d0`

## string_xrefs

- `0x653b`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationService.cs`
- `0x6584`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationService.cs`
- `0x65bd`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationService.cs`
- `0x6536`: `PrivateDelete`
- `0x657f`: `PrivateDelete`
- `0x65b8`: `PrivateDelete`

## pseudocode

```c

```

## disassembly

```asm
0x64d0  ldarg.1
0x64d1  call     bool Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::IsNotificationDisabled(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x64d6  brtrue.s loc_64FC
0x64d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x64dd  ldstr    aTheNotificatio// "The notification {0} is not disabled. P"...
0x64e2  ldc.i4.1
0x64e3  newarr   [mscorlib]System.Object
0x64e8  dup
0x64e9  ldc.i4.0
0x64ea  ldarg.0
0x64eb  box      [mscorlib]System.Guid
0x64f0  stelem.ref
0x64f1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x64f6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x64fb  throw
0x64fc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x6501  stloc.0
0x6502  ldloc.0
0x6503  ldstr    aNotificationid_0// "NotificationId"
0x6508  ldarg.0
0x6509  box      [mscorlib]System.Guid
0x650e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6513  ldarg.2
0x6514  ldstr    aEndusernotific_1// "EndUserNotificationParameters"
0x6519  ldc.i4.1
0x651a  newarr   [mscorlib]System.String
0x651f  dup
0x6520  ldc.i4.0
0x6521  ldstr    aId// "Id"
0x6526  stelem.ref
0x6527  ldc.i4.1
0x6528  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x652d  dup
0x652e  ldc.i4.0
0x652f  ldloc.0
0x6530  stelem.ref
0x6531  ldc.i4   0x380
0x6536  ldstr    aPrivatedelete// "PrivateDelete"
0x653b  ldstr    aDA1SSrcCrmlive_9// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x6540  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x6545  stloc.1
0x6546  ldloc.1
0x6547  brfalse.s loc_65A7
0x6549  ldloc.1
0x654a  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x654f  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x6554  stloc.2
0x6555  br.s     loc_658E
0x6557  ldloca.s 2
0x6559  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x655e  stloc.3
0x655f  ldarg.2
0x6560  ldstr    aEndusernotific_1// "EndUserNotificationParameters"
0x6565  ldloc.3
0x6566  ldstr    aId// "Id"
0x656b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x6570  unbox.any [mscorlib]System.Guid
0x6575  box      [mscorlib]System.Guid
0x657a  ldc.i4   0x389
0x657f  ldstr    aPrivatedelete// "PrivateDelete"
0x6584  ldstr    aDA1SSrcCrmlive_9// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x6589  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x658e  ldloca.s 2
0x6590  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x6595  brtrue.s loc_6557
0x6597  leave.s  loc_65A7
0x6599  ldloca.s 2
0x659b  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x65a1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65a6  endfinally
0x65a7  ldarg.2
0x65a8  ldstr    aLocalizedusern// "LocalizedUserNotification"
0x65ad  ldarg.0
0x65ae  box      [mscorlib]System.Guid
0x65b3  ldc.i4   0x38E
0x65b8  ldstr    aPrivatedelete// "PrivateDelete"
0x65bd  ldstr    aDA1SSrcCrmlive_9// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x65c2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x65c7  ldarg.0
0x65c8  ret
```
