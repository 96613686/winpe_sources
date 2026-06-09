# Microsoft.Crm.LiveResourceLimitRetriever::Retrieve

- ea: `0xc600`
- end: `0xc897`
- name: `Microsoft.Crm.LiveResourceLimitRetriever::Retrieve`
- size: `663`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8a90`
- `0xc580`

## callees

- `0x4640`
- `0x4c60`
- `0xc600`
- `0xc8a0`
- `0xc9b0`
- `0xca10`
- `0xcae0`
- `0x1be90`
- `0x43af0`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x4d7e0`
- `0x64b10`

## string_xrefs

- `0xc640`: `ServiceComponentId`
- `0xc6fa`: `ServiceComponentId`
- `0xc701`: `ServiceComponentId`
- `0xc657`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\LiveResourceLimitRetriever.cs`
- `0xc739`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\LiveResourceLimitRetriever.cs`
- `0xc715`: `ServiceComponentResourceLimits`

## pseudocode

```c

```

## disassembly

```asm
0xc600  ldarg.1
0xc601  ldstr    aOrganizationid_0// "organizationId"
0xc606  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xc60b  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xc610  stloc.1
0xc611  ldloc.1
0xc612  ldstr    aOrganizationid_1// "OrganizationId"
0xc617  ldarg.1
0xc618  box      [mscorlib]System.Guid
0xc61d  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xc622  call     class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xc627  stloc.s  0xA
0xc629  ldloc.s  0xA
0xc62b  ldstr    aOrganizationre// "OrganizationResources"
0xc630  ldc.i4.2
0xc631  newarr   [mscorlib]System.String
0xc636  dup
0xc637  ldc.i4.0
0xc638  ldstr    aCount// "Count"
0xc63d  stelem.ref
0xc63e  dup
0xc63f  ldc.i4.1
0xc640  ldstr    aServicecompone_0// "ServiceComponentId"
0xc645  stelem.ref
0xc646  ldc.i4.1
0xc647  newarr   Microsoft.Crm.Data.PropertyBag
0xc64c  dup
0xc64d  ldc.i4.0
0xc64e  ldloc.1
0xc64f  stelem.ref
0xc650  ldc.i4.s 0x2E
0xc652  ldstr    aRetrieve// "Retrieve"
0xc657  ldstr    aDA1SSrcPlatfor_2// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xc65c  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xc661  stloc.0
0xc662  leave.s  loc_C670
0xc664  ldloc.s  0xA
0xc666  brfalse.s loc_C66F
0xc668  ldloc.s  0xA
0xc66a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc66f  endfinally
0xc670  ldloc.0
0xc671  ldarg.2
0xc672  call     valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.LiveResourceLimitRetriever::GetOrgLimit(class Microsoft.Crm.Data.PropertyBagCollection orgResources, valuetype Microsoft.Crm.Config.Wrapper.ResourceType resourceType)
0xc677  stloc.2
0xc678  ldloca.s 3
0xc67a  ldloca.s 2
0xc67c  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc681  brtrue.s loc_C686
0xc683  ldc.i4.0
0xc684  br.s     loc_C68D
0xc686  ldloca.s 2
0xc688  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xc68d  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xc692  ldarg.1
0xc693  ldarg.2
0xc694  call     int32 Microsoft.Crm.LiveResourceLimitRetriever::GetResourceOverride(valuetype [mscorlib]System.Guid organizationId, valuetype Microsoft.Crm.Config.Wrapper.ResourceType resourceType)
0xc699  stloc.s  4
0xc69b  ldloca.s 5
0xc69d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xc6a3  ldloca.s 6
0xc6a5  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xc6ab  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0xc6b0  stloc.s  7
0xc6b2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0xc6b7  stloc.s  8
0xc6b9  ldloc.0
0xc6ba  call     bool Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class Microsoft.Crm.Data.PropertyBagCollection collection)
0xc6bf  brtrue   loc_C7C8
0xc6c4  ldloc.0
0xc6c5  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0xc6ca  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xc6cf  stloc.s  0xB
0xc6d1  br       loc_C77C
0xc6d6  ldloca.s 0xB
0xc6d8  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0xc6dd  stloc.s  0xC
0xc6df  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xc6e4  stloc.s  0xD
0xc6e6  ldloc.s  0xD
0xc6e8  ldstr    aResourcetypeid// "ResourceTypeId"
0xc6ed  ldarg.2
0xc6ee  box      [mscorlib]System.Int32
0xc6f3  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xc6f8  ldloc.s  0xD
0xc6fa  ldstr    aServicecompone_0// "ServiceComponentId"
0xc6ff  ldloc.s  0xC
0xc701  ldstr    aServicecompone_0// "ServiceComponentId"
0xc706  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xc70b  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xc710  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0xc715  ldstr    aServicecompone_1// "ServiceComponentResourceLimits"
0xc71a  ldc.i4.2
0xc71b  newarr   [mscorlib]System.String
0xc720  dup
0xc721  ldc.i4.0
0xc722  ldstr    aMaximum// "Maximum"
0xc727  stelem.ref
0xc728  dup
0xc729  ldc.i4.1
0xc72a  ldstr    aMinimum// "Minimum"
0xc72f  stelem.ref
0xc730  ldloc.s  0xD
0xc732  ldc.i4.s 0x45
0xc734  ldstr    aRetrieve// "Retrieve"
0xc739  ldstr    aDA1SSrcPlatfor_2// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xc73e  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xc743  stloc.s  0xE
0xc745  ldloc.s  0xE
0xc747  brfalse.s loc_C77C
0xc749  ldloc.s  8
0xc74b  ldloc.s  0xE
0xc74d  ldstr    aMaximum// "Maximum"
0xc752  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xc757  unbox.any [mscorlib]System.Int32
0xc75c  ldloc.s  4
0xc75e  add
0xc75f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0xc764  ldloc.s  7
0xc766  ldloc.s  0xE
0xc768  ldstr    aMinimum// "Minimum"
0xc76d  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xc772  unbox.any [mscorlib]System.Int32
0xc777  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0xc77c  ldloca.s 0xB
0xc77e  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xc783  brtrue   loc_C6D6
0xc788  leave.s  loc_C798
0xc78a  ldloca.s 0xB
0xc78c  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0xc792  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc797  endfinally
0xc798  ldloc.s  7
0xc79a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0xc79f  ldc.i4.0
0xc7a0  ble.s    loc_C7B0
0xc7a2  ldloca.s 5
0xc7a4  ldloc.s  7
0xc7a6  call     int32 [System.Core]System.Linq.Enumerable::Max(class [mscorlib]System.Collections.Generic.IEnumerable`1<int32>)
0xc7ab  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xc7b0  ldloc.s  8
0xc7b2  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0xc7b7  ldc.i4.0
0xc7b8  ble.s    loc_C7C8
0xc7ba  ldloca.s 6
0xc7bc  ldloc.s  8
0xc7be  call     int32 [System.Core]System.Linq.Enumerable::Min(class [mscorlib]System.Collections.Generic.IEnumerable`1<int32>)
0xc7c3  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xc7c8  ldloca.s 2
0xc7ca  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc7cf  brfalse.s loc_C7D9
0xc7d1  ldarg.2
0xc7d2  ldc.i4.4
0xc7d3  beq.s    loc_C7D9
0xc7d5  ldarg.2
0xc7d6  ldc.i4.5
0xc7d7  bne.un.s loc_C7DE
0xc7d9  ldloc.s  6
0xc7db  stloc.3
0xc7dc  br.s     loc_C83A
0xc7de  ldloc.3
0xc7df  stloc.s  0xF
0xc7e1  ldloc.s  5
0xc7e3  stloc.s  0x10
0xc7e5  ldloca.s 0xF
0xc7e7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0xc7ec  ldloca.s 0x10
0xc7ee  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0xc7f3  clt
0xc7f5  ldloca.s 0xF
0xc7f7  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc7fc  ldloca.s 0x10
0xc7fe  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc803  and
0xc804  and
0xc805  brfalse.s loc_C80E
0xc807  ldarg.2
0xc808  ldc.i4.2
0xc809  beq.s    loc_C80E
0xc80b  ldloc.s  5
0xc80d  stloc.3
0xc80e  ldloc.3
0xc80f  stloc.s  0x10
0xc811  ldloc.s  6
0xc813  stloc.s  0xF
0xc815  ldloca.s 0x10
0xc817  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0xc81c  ldloca.s 0xF
0xc81e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0xc823  cgt
0xc825  ldloca.s 0x10
0xc827  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc82c  ldloca.s 0xF
0xc82e  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc833  and
0xc834  and
0xc835  brfalse.s loc_C83A
0xc837  ldloc.s  6
0xc839  stloc.3
0xc83a  ldloca.s 2
0xc83c  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc841  brtrue.s loc_C85E
0xc843  ldloca.s 5
0xc845  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc84a  brtrue.s loc_C85E
0xc84c  ldloca.s 6
0xc84e  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc853  brtrue.s loc_C85E
0xc855  ldarg.2
0xc856  ldloc.s  4
0xc858  call     valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.LiveResourceLimitRetriever::GetLimitOfDefaultSku(valuetype Microsoft.Crm.Config.Wrapper.ResourceType resourceType, int32 resourceOverride)
0xc85d  stloc.3
0xc85e  ldarg.2
0xc85f  call     int32 Microsoft.Crm.LiveResourceLimitRetriever::GetSystemMaximum(valuetype Microsoft.Crm.Config.Wrapper.ResourceType resourceType)
0xc864  stloc.s  9
0xc866  ldloc.3
0xc867  stloc.s  0xF
0xc869  ldloc.s  9
0xc86b  stloc.s  0x11
0xc86d  ldloca.s 0xF
0xc86f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0xc874  ldloc.s  0x11
0xc876  cgt
0xc878  ldloca.s 0xF
0xc87a  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc87f  and
0xc880  brfalse.s loc_C88F
0xc882  ldloc.s  4
0xc884  brtrue.s loc_C88F
0xc886  ldloca.s 3
0xc888  ldloc.s  9
0xc88a  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xc88f  ldloca.s 3
0xc891  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xc896  ret
```
