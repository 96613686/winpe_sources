# Microsoft.Crm.LiveResourceLimitRetriever::GetOrgLimit

- ea: `0xc8a0`
- end: `0xc989`
- name: `Microsoft.Crm.LiveResourceLimitRetriever::GetOrgLimit`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xc600`

## callees

- `0x4640`
- `0x4c60`
- `0xc8a0`
- `0xc990`
- `0x43af0`
- `0x44400`
- `0x444f0`
- `0x44510`

## string_xrefs

- `0xc8e4`: `ServiceComponentId`
- `0xc8ea`: `ServiceComponentId`
- `0xc91c`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\LiveResourceLimitRetriever.cs`
- `0xc8fe`: `ServiceComponentSettings`
- `0xc90b`: `AmountProvided`
- `0xc956`: `AmountProvided`

## pseudocode

```c

```

## disassembly

```asm
0xc8a0  ldloca.s 0
0xc8a2  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xc8a8  ldarg.0
0xc8a9  call     bool Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class Microsoft.Crm.Data.PropertyBagCollection collection)
0xc8ae  brtrue   loc_C987
0xc8b3  ldarg.0
0xc8b4  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0xc8b9  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xc8be  stloc.1
0xc8bf  br       loc_C96B
0xc8c4  ldloca.s 1
0xc8c6  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0xc8cb  stloc.2
0xc8cc  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xc8d1  stloc.3
0xc8d2  ldloc.3
0xc8d3  ldstr    aResourcetypeid// "ResourceTypeId"
0xc8d8  ldarg.1
0xc8d9  box      [mscorlib]System.Int32
0xc8de  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xc8e3  ldloc.3
0xc8e4  ldstr    aServicecompone_0// "ServiceComponentId"
0xc8e9  ldloc.2
0xc8ea  ldstr    aServicecompone_0// "ServiceComponentId"
0xc8ef  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xc8f4  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xc8f9  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0xc8fe  ldstr    aServicecompone_2// "ServiceComponentSettings"
0xc903  ldc.i4.1
0xc904  newarr   [mscorlib]System.String
0xc909  dup
0xc90a  ldc.i4.0
0xc90b  ldstr    aAmountprovided// "AmountProvided"
0xc910  stelem.ref
0xc911  ldloc.3
0xc912  ldc.i4   0x89
0xc917  ldstr    aGetorglimit// "GetOrgLimit"
0xc91c  ldstr    aDA1SSrcPlatfor_2// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xc921  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xc926  stloc.s  4
0xc928  ldloc.s  4
0xc92a  brfalse.s loc_C96B
0xc92c  ldloca.s 0
0xc92e  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xc933  brtrue.s loc_C93C
0xc935  ldc.i4.0
0xc936  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xc93b  stloc.0
0xc93c  ldarg.1
0xc93d  ldloca.s 0
0xc93f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xc944  ldloc.2
0xc945  ldstr    aCount// "Count"
0xc94a  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xc94f  unbox.any [mscorlib]System.Int32
0xc954  ldloc.s  4
0xc956  ldstr    aAmountprovided// "AmountProvided"
0xc95b  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xc960  unbox.any [mscorlib]System.Int32
0xc965  call     valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.LiveResourceLimitRetriever::IncrementOrgLimit(valuetype Microsoft.Crm.Config.Wrapper.ResourceType resourceType, int32 orgLimit, int32 count, int32 amountProvided)
0xc96a  stloc.0
0xc96b  ldloca.s 1
0xc96d  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xc972  brtrue   loc_C8C4
0xc977  leave.s  loc_C987
0xc979  ldloca.s 1
0xc97b  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0xc981  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc986  endfinally
0xc987  ldloc.0
0xc988  ret
```
