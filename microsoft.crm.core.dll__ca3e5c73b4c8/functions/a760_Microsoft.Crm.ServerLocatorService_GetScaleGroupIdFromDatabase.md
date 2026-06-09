# Microsoft.Crm.ServerLocatorService::GetScaleGroupIdFromDatabase

- ea: `0xa760`
- end: `0xa8d7`
- name: `Microsoft.Crm.ServerLocatorService::GetScaleGroupIdFromDatabase`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa570`

## callees

- `0x9620`
- `0xa760`
- `0xbdf0`
- `0xbfa0`
- `0x2d9a0`
- `0x43b10`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x44670`
- `0x4d750`
- `0x61520`

## string_xrefs

- `0xa799`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xa86d`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xa760  ldc.i4.2
0xa761  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.ServerLocatorService::GetConfigSku()
0xa766  beq.s    loc_A76E
0xa768  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa76d  ret
0xa76e  call     string Microsoft.Crm.EnvironmentWrapper::get_MachineName()
0xa773  stloc.0
0xa774  ldarg.0
0xa775  ldfld    bool Microsoft.Crm.ServerLocatorService::_isRetrieveConditionCacheEnabled
0xa77a  brfalse  loc_A824
0xa77f  ldarg.0
0xa780  ldc.i4.3
0xa781  stloc.2
0xa782  ldloca.s 2
0xa784  constrained. Microsoft.Crm.CrmConfigDatabaseTable
0xa78a  callvirt instance string [mscorlib]System.Object::ToString()
0xa78f  ldc.i4   0x9F6
0xa794  ldstr    aGetscalegroupi// "GetScaleGroupIdFromDatabase"
0xa799  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xa79e  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xa7a3  dup
0xa7a4  brtrue.s loc_A7AC
0xa7a6  pop
0xa7a7  newobj   instance void Microsoft.Crm.Data.PropertyBagCollection::.ctor()
0xa7ac  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xa7b1  stloc.3
0xa7b2  br.s     loc_A80B
0xa7b4  ldloca.s 3
0xa7b6  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0xa7bb  stloc.s  4
0xa7bd  ldloca.s 4
0xa7bf  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0xa7c4  ldstr    aName// "Name"
0xa7c9  callvirt instance bool Microsoft.Crm.Data.PropertyBag::Contains(string propertyName)
0xa7ce  brfalse.s loc_A80B
0xa7d0  ldloca.s 4
0xa7d2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0xa7d7  ldstr    aName// "Name"
0xa7dc  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xa7e1  castclass [mscorlib]System.String
0xa7e6  ldloc.0
0xa7e7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa7ec  brfalse.s loc_A80B
0xa7ee  ldloca.s 4
0xa7f0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0xa7f5  ldstr    aScalegroupid_0// "ScaleGroupId"
0xa7fa  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xa7ff  unbox.any [mscorlib]System.Guid
0xa804  stloc.s  5
0xa806  leave    loc_A8D4
0xa80b  ldloca.s 3
0xa80d  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xa812  brtrue.s loc_A7B4
0xa814  leave.s  loc_A824
0xa816  ldloca.s 3
0xa818  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0xa81e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa823  endfinally
0xa824  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xa829  stloc.1
0xa82a  ldloc.1
0xa82b  ldstr    aName// "Name"
0xa830  ldloc.0
0xa831  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xa836  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xa83b  stloc.s  6
0xa83d  ldloc.s  6
0xa83f  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0xa844  ldloc.s  6
0xa846  ldstr    aServer// "Server"
0xa84b  ldc.i4.1
0xa84c  newarr   [mscorlib]System.String
0xa851  dup
0xa852  ldc.i4.0
0xa853  ldstr    aScalegroupid_0// "ScaleGroupId"
0xa858  stelem.ref
0xa859  ldc.i4.1
0xa85a  newarr   Microsoft.Crm.Data.PropertyBag
0xa85f  dup
0xa860  ldc.i4.0
0xa861  ldloc.1
0xa862  stelem.ref
0xa863  ldc.i4   0xA07
0xa868  ldstr    aGetscalegroupi// "GetScaleGroupIdFromDatabase"
0xa86d  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xa872  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xa877  stloc.s  7
0xa879  ldloc.s  7
0xa87b  brfalse.s loc_A8C0
0xa87d  ldloc.s  7
0xa87f  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0xa884  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xa889  stloc.s  8
0xa88b  br.s     loc_A8A7
0xa88d  ldloca.s 8
0xa88f  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0xa894  ldstr    aScalegroupid_0// "ScaleGroupId"
0xa899  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xa89e  unbox.any [mscorlib]System.Guid
0xa8a3  stloc.s  5
0xa8a5  leave.s  loc_A8D4
0xa8a7  ldloca.s 8
0xa8a9  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xa8ae  brtrue.s loc_A88D
0xa8b0  leave.s  loc_A8CE
0xa8b2  ldloca.s 8
0xa8b4  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0xa8ba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa8bf  endfinally
0xa8c0  leave.s  loc_A8CE
0xa8c2  ldloc.s  6
0xa8c4  brfalse.s loc_A8CD
0xa8c6  ldloc.s  6
0xa8c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa8cd  endfinally
0xa8ce  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa8d3  ret
0xa8d4  ldloc.s  5
0xa8d6  ret
```
