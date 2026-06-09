# Microsoft.Crm.CrmLive.Services.CategoryService::RetrieveAllCategoryNames

- ea: `0x11b70`
- end: `0x11cab`
- name: `Microsoft.Crm.CrmLive.Services.CategoryService::RetrieveAllCategoryNames`
- size: `315`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x11b70`

## string_xrefs

- `0x11b8a`: `D:\a\1\s\src\CrmLive\Admin\RestrictedOffers\CategoryService.cs`
- `0x11bb9`: `D:\a\1\s\src\CrmLive\Admin\RestrictedOffers\CategoryService.cs`
- `0x11bee`: `D:\a\1\s\src\CrmLive\Admin\RestrictedOffers\CategoryService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x11b70  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor()
0x11b75  stloc.0
0x11b76  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x11b7b  ldstr    aOffer// "Offer"
0x11b80  ldc.i4   0xA7
0x11b85  ldstr    aRetrieveallcat// "RetrieveAllCategoryNames"
0x11b8a  ldstr    aDA1SSrcCrmlive_22// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Restr"...
0x11b8f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Retrieve(string, int32, string, string)
0x11b94  stloc.1
0x11b95  ldloc.1
0x11b96  brtrue   loc_11C2B
0x11b9b  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x11ba0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Flush()
0x11ba5  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x11baa  ldstr    aOffer// "Offer"
0x11baf  ldc.i4   0xAD
0x11bb4  ldstr    aRetrieveallcat// "RetrieveAllCategoryNames"
0x11bb9  ldstr    aDA1SSrcCrmlive_22// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Restr"...
0x11bbe  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Retrieve(string, int32, string, string)
0x11bc3  stloc.1
0x11bc4  ldloc.1
0x11bc5  brtrue.s loc_11C05
0x11bc7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x11bcc  stloc.2
0x11bcd  ldc.i4.1
0x11bce  newarr   [mscorlib]System.String
0x11bd3  dup
0x11bd4  ldc.i4.0
0x11bd5  ldstr    aCategory_0// "Category"
0x11bda  stelem.ref
0x11bdb  stloc.3
0x11bdc  ldloc.2
0x11bdd  ldstr    aOffer// "Offer"
0x11be2  ldloc.3
0x11be3  ldnull
0x11be4  ldc.i4   0xB5
0x11be9  ldstr    aRetrieveallcat// "RetrieveAllCategoryNames"
0x11bee  ldstr    aDA1SSrcCrmlive_22// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Restr"...
0x11bf3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x11bf8  stloc.1
0x11bf9  leave.s  loc_11C05
0x11bfb  ldloc.2
0x11bfc  brfalse.s loc_11C04
0x11bfe  ldloc.2
0x11bff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11c04  endfinally
0x11c05  ldloc.1
0x11c06  brtrue.s loc_11C2B
0x11c08  ldnull
0x11c09  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x11c0e  ldc.i4.s 0xB
0x11c10  ldstr    aNoOffersFound// "No offers found"
0x11c15  ldc.i4.0
0x11c16  newarr   [mscorlib]System.Object
0x11c1b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11c20  ldstr    aNoOffersFound// "No offers found"
0x11c25  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x11c2a  throw
0x11c2b  ldloc.1
0x11c2c  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x11c31  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x11c36  stloc.s  4
0x11c38  br.s     loc_11C81
0x11c3a  ldloca.s 4
0x11c3c  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x11c41  ldstr    aCategory_0// "Category"
0x11c46  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x11c4b  isinst   [mscorlib]System.String
0x11c50  stloc.s  5
0x11c52  ldloc.0
0x11c53  ldloc.s  5
0x11c55  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::ContainsKey(var<u1>)
0x11c5a  brtrue.s loc_11C81
0x11c5c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x11c61  ldc.i4.s 0xB
0x11c63  ldstr    aFoundCategory// "Found category: "
0x11c68  ldc.i4.1
0x11c69  newarr   [mscorlib]System.Object
0x11c6e  dup
0x11c6f  ldc.i4.0
0x11c70  ldloc.s  5
0x11c72  stelem.ref
0x11c73  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11c78  ldloc.0
0x11c79  ldloc.s  5
0x11c7b  ldc.i4.1
0x11c7c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0x11c81  ldloca.s 4
0x11c83  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x11c88  brtrue.s loc_11C3A
0x11c8a  leave.s  loc_11C9A
0x11c8c  ldloca.s 4
0x11c8e  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x11c94  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11c99  endfinally
0x11c9a  ldloc.0
0x11c9b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Keys()
0x11ca0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x11ca5  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x11caa  ret
```
