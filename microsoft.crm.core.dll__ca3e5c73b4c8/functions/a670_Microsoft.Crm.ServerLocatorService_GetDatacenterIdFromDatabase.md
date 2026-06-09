# Microsoft.Crm.ServerLocatorService::GetDatacenterIdFromDatabase

- ea: `0xa670`
- end: `0xa755`
- name: `Microsoft.Crm.ServerLocatorService::GetDatacenterIdFromDatabase`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa610`

## callees

- `0x4640`
- `0x4c40`
- `0xa670`
- `0xbb80`
- `0xbdf0`
- `0xbfa0`
- `0x444f0`
- `0x4d750`
- `0x613c0`

## string_xrefs

- `0xa6b5`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xa6fc`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xa670  ldc.i4.2
0xa671  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.ServerLocatorService::GetConfigSku()
0xa676  beq.s    loc_A67E
0xa678  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa67d  ret
0xa67e  nop
0xa67f  call     valuetype [mscorlib]System.Guid Microsoft.Crm.ServerLocatorService::GetServerIdFromDatabase()
0xa684  stloc.1
0xa685  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xa68a  stloc.2
0xa68b  ldloc.2
0xa68c  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0xa691  ldloc.2
0xa692  ldstr    aServer// "Server"
0xa697  ldloc.1
0xa698  box      [mscorlib]System.Guid
0xa69d  ldc.i4.1
0xa69e  newarr   [mscorlib]System.String
0xa6a3  dup
0xa6a4  ldc.i4.0
0xa6a5  ldstr    aDatacenterid// "DatacenterId"
0xa6aa  stelem.ref
0xa6ab  ldc.i4   0x9CC
0xa6b0  ldstr    aGetdatacenteri// "GetDatacenterIdFromDatabase"
0xa6b5  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xa6ba  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveById(string tableName, object id, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xa6bf  stloc.3
0xa6c0  ldloc.3
0xa6c1  brfalse.s loc_A6D7
0xa6c3  ldloc.3
0xa6c4  ldstr    aDatacenterid// "DatacenterId"
0xa6c9  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xa6ce  unbox.any [mscorlib]System.Guid
0xa6d3  stloc.s  4
0xa6d5  leave.s  loc_A752
0xa6d7  leave.s  loc_A6E3
0xa6d9  ldloc.2
0xa6da  brfalse.s loc_A6E2
0xa6dc  ldloc.2
0xa6dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa6e2  endfinally
0xa6e3  leave.s  loc_A6E8
0xa6e5  pop
0xa6e6  leave.s  loc_A6E8
0xa6e8  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0xa6ed  ldstr    aDatacenter// "Datacenter"
0xa6f2  ldc.i4   0x9D7
0xa6f7  ldstr    aGetdatacenteri// "GetDatacenterIdFromDatabase"
0xa6fc  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xa701  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.LocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xa706  stloc.0
0xa707  ldloc.0
0xa708  brfalse.s loc_A74C
0xa70a  ldloc.0
0xa70b  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0xa710  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xa715  stloc.s  5
0xa717  br.s     loc_A733
0xa719  ldloca.s 5
0xa71b  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0xa720  ldstr    aId// "Id"
0xa725  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xa72a  unbox.any [mscorlib]System.Guid
0xa72f  stloc.s  4
0xa731  leave.s  loc_A752
0xa733  ldloca.s 5
0xa735  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xa73a  brtrue.s loc_A719
0xa73c  leave.s  loc_A74C
0xa73e  ldloca.s 5
0xa740  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0xa746  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa74b  endfinally
0xa74c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa751  ret
0xa752  ldloc.s  4
0xa754  ret
```
