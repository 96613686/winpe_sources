# Microsoft.Crm.ServerLocatorService::GetAzureResourceGroupId

- ea: `0xb4f0`
- end: `0xb60b`
- name: `Microsoft.Crm.ServerLocatorService::GetAzureResourceGroupId`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xaf70`
- `0xb140`

## callees

- `0xa00`
- `0xde0`
- `0x4640`
- `0x4c20`
- `0x9620`
- `0xb4f0`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x656b0`
- `0x656d0`

## string_xrefs

- `0xb537`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xb5e7`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xb4f0  newobj   instance void <>c__DisplayClass133_0::.ctor()
0xb4f5  stloc.0
0xb4f6  ldloc.0
0xb4f7  ldarg.1
0xb4f8  stfld    int32 <>c__DisplayClass133_0::orgType
0xb4fd  ldstr    aDefaultazurere// "DefaultAzureResourceGroup"
0xb502  stloc.1
0xb503  ldarg.0
0xb504  ldfld    bool Microsoft.Crm.ServerLocatorService::_isRetrieveConditionCacheEnabled
0xb509  brfalse.s loc_B587
0xb50b  newobj   instance void <>c__DisplayClass133_1::.ctor()
0xb510  stloc.s  4
0xb512  ldloc.s  4
0xb514  ldloc.0
0xb515  stfld    class <>c__DisplayClass133_0 <>c__DisplayClass133_1::CS$<>8__locals1
0xb51a  ldloc.s  4
0xb51c  call     class Microsoft.Crm.IDataCenterInfoProvider Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0xb521  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0xb526  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass133_1::datacenterId
0xb52b  ldarg.0
0xb52c  ldloc.1
0xb52d  ldc.i4   0xBF4
0xb532  ldstr    aGetazureresour// "GetAzureResourceGroupId"
0xb537  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xb53c  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xb541  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0xb546  ldloc.s  4
0xb548  ldftn    instance bool <>c__DisplayClass133_1::<GetAzureResourceGroupId>b__0(class Microsoft.Crm.Data.PropertyBag x)
0xb54e  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Data.PropertyBag, bool>::.ctor(object, native int)
0xb553  call     T0x2B00002E
0xb558  dup
0xb559  brtrue.s loc_B55F
0xb55b  pop
0xb55c  ldnull
0xb55d  br.s     loc_B569
0xb55f  ldstr    aDefaultazurere_0// "DefaultAzureResourceGroupId"
0xb564  call     instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xb569  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xb56e  stloc.s  5
0xb570  ldloca.s 5
0xb572  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xb577  brtrue.s loc_B57F
0xb579  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb57e  ret
0xb57f  ldloca.s 5
0xb581  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0xb586  ret
0xb587  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xb58c  stloc.2
0xb58d  ldloc.2
0xb58e  ldstr    aScopeid// "ScopeId"
0xb593  call     class Microsoft.Crm.IDataCenterInfoProvider Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0xb598  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0xb59d  box      [mscorlib]System.Guid
0xb5a2  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb5a7  ldloc.2
0xb5a8  ldstr    aOrgapplication// "OrgApplicationType"
0xb5ad  ldloc.0
0xb5ae  ldfld    int32 <>c__DisplayClass133_0::orgType
0xb5b3  box      [mscorlib]System.Int32
0xb5b8  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb5bd  ldc.i4.1
0xb5be  newarr   Microsoft.Crm.Data.PropertyBag
0xb5c3  dup
0xb5c4  ldc.i4.0
0xb5c5  ldloc.2
0xb5c6  stelem.ref
0xb5c7  stloc.3
0xb5c8  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0xb5cd  ldloc.1
0xb5ce  ldc.i4.1
0xb5cf  newarr   [mscorlib]System.String
0xb5d4  dup
0xb5d5  ldc.i4.0
0xb5d6  ldstr    aDefaultazurere_0// "DefaultAzureResourceGroupId"
0xb5db  stelem.ref
0xb5dc  ldloc.3
0xb5dd  ldc.i4   0xC00
0xb5e2  ldstr    aGetazureresour// "GetAzureResourceGroupId"
0xb5e7  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xb5ec  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.LocatorService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xb5f1  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0xb5f6  call     T0x2B00002F
0xb5fb  ldstr    aDefaultazurere_0// "DefaultAzureResourceGroupId"
0xb600  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xb605  unbox.any [mscorlib]System.Guid
0xb60a  ret
```
