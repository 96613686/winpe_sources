# Microsoft.Crm.ServerLocatorService::GetDisabledAccessRights

- ea: `0x86f0`
- end: `0x8879`
- name: `Microsoft.Crm.ServerLocatorService::GetDisabledAccessRights`
- size: `393`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x86f0`
- `0xbfa0`
- `0x1be90`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x4d7e0`
- `0x64b10`

## string_xrefs

- `0x875d`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x87f1`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x8758`: `GetDisabledAccessRights`
- `0x87ec`: `GetDisabledAccessRights`
- `0x87c9`: `FeatureAccessRightMap`
- `0x87d6`: `AccessRight`
- `0x881d`: `AccessRight`

## pseudocode

```c

```

## disassembly

```asm
0x86f0  ldarg.1
0x86f1  ldstr    aOrganizationid_0// "organizationId"
0x86f6  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x86fb  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x8700  stloc.0
0x8701  call     class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x8706  stloc.1
0x8707  ldloc.1
0x8708  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0x870d  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x8712  stloc.2
0x8713  ldloc.2
0x8714  ldstr    aOrganizationid_1// "OrganizationId"
0x8719  ldarg.1
0x871a  box      [mscorlib]System.Guid
0x871f  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8724  ldloc.2
0x8725  ldstr    aEnabled// "Enabled"
0x872a  ldc.i4.0
0x872b  box      [mscorlib]System.Boolean
0x8730  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8735  ldloc.1
0x8736  ldstr    aOrganizationfe// "OrganizationFeatureMap"
0x873b  ldc.i4.1
0x873c  newarr   [mscorlib]System.String
0x8741  dup
0x8742  ldc.i4.0
0x8743  ldstr    aFeatureid// "FeatureId"
0x8748  stelem.ref
0x8749  ldc.i4.1
0x874a  newarr   Microsoft.Crm.Data.PropertyBag
0x874f  dup
0x8750  ldc.i4.0
0x8751  ldloc.2
0x8752  stelem.ref
0x8753  ldc.i4   0x4D8
0x8758  ldstr    aGetdisabledacc// "GetDisabledAccessRights"
0x875d  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x8762  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x8767  stloc.3
0x8768  ldloc.3
0x8769  brfalse  loc_8866
0x876e  ldloc.3
0x876f  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x8774  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x8779  stloc.s  4
0x877b  br       loc_884A
0x8780  ldloca.s 4
0x8782  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x8787  stloc.s  5
0x8789  ldloc.s  5
0x878b  ldstr    aFeatureid// "FeatureId"
0x8790  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x8795  unbox.any [mscorlib]System.Guid
0x879a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Config.Wrapper.OrganizationFeature::CreateEntity
0x879f  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x87a4  brtrue   loc_884A
0x87a9  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x87ae  stloc.s  6
0x87b0  ldloc.s  6
0x87b2  ldstr    aFeatureid// "FeatureId"
0x87b7  ldloc.s  5
0x87b9  ldstr    aFeatureid// "FeatureId"
0x87be  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x87c3  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x87c8  ldloc.1
0x87c9  ldstr    aFeatureaccessr// "FeatureAccessRightMap"
0x87ce  ldc.i4.1
0x87cf  newarr   [mscorlib]System.String
0x87d4  dup
0x87d5  ldc.i4.0
0x87d6  ldstr    aAccessright// "AccessRight"
0x87db  stelem.ref
0x87dc  ldc.i4.1
0x87dd  newarr   Microsoft.Crm.Data.PropertyBag
0x87e2  dup
0x87e3  ldc.i4.0
0x87e4  ldloc.s  6
0x87e6  stelem.ref
0x87e7  ldc.i4   0x4E8
0x87ec  ldstr    aGetdisabledacc// "GetDisabledAccessRights"
0x87f1  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x87f6  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x87fb  stloc.s  7
0x87fd  ldloc.s  7
0x87ff  brfalse.s loc_884A
0x8801  ldloc.s  7
0x8803  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x8808  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x880d  stloc.s  8
0x880f  br.s     loc_8831
0x8811  ldloca.s 8
0x8813  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x8818  stloc.s  9
0x881a  ldloc.0
0x881b  ldloc.s  9
0x881d  ldstr    aAccessright// "AccessRight"
0x8822  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x8827  unbox.any [mscorlib]System.Int32
0x882c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x8831  ldloca.s 8
0x8833  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x8838  brtrue.s loc_8811
0x883a  leave.s  loc_884A
0x883c  ldloca.s 8
0x883e  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x8844  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8849  endfinally
0x884a  ldloca.s 4
0x884c  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x8851  brtrue   loc_8780
0x8856  leave.s  loc_8872
0x8858  ldloca.s 4
0x885a  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x8860  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8865  endfinally
0x8866  leave.s  loc_8872
0x8868  ldloc.1
0x8869  brfalse.s loc_8871
0x886b  ldloc.1
0x886c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8871  endfinally
0x8872  ldloc.0
0x8873  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x8878  ret
```
