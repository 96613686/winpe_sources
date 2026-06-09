# Microsoft.Crm.ServerLocatorService::GetOrganizationSkuFromDatabase

- ea: `0x7ed0`
- end: `0x7fdc`
- name: `Microsoft.Crm.ServerLocatorService::GetOrganizationSkuFromDatabase`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7ea0`

## callees

- `0x7ed0`
- `0xbfa0`
- `0x43af0`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x4d7e0`
- `0x64b00`
- `0x64b10`

## string_xrefs

- `0x7f02`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x7f8a`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x7edd`: `ServiceComponentSku`
- `0x7ef2`: `ServiceComponentId`
- `0x7f4c`: `ServiceComponentId`
- `0x7f52`: `ServiceComponentId`

## pseudocode

```c

```

## disassembly

```asm
0x7ed0  call     class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x7ed5  stloc.0
0x7ed6  ldloc.0
0x7ed7  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0x7edc  ldloc.0
0x7edd  ldstr    aServicecompone// "ServiceComponentSku"
0x7ee2  ldc.i4.2
0x7ee3  newarr   [mscorlib]System.String
0x7ee8  dup
0x7ee9  ldc.i4.0
0x7eea  ldstr    aName// "Name"
0x7eef  stelem.ref
0x7ef0  dup
0x7ef1  ldc.i4.1
0x7ef2  ldstr    aServicecompone_0// "ServiceComponentId"
0x7ef7  stelem.ref
0x7ef8  ldc.i4   0x3B3
0x7efd  ldstr    aGetorganizatio_9// "GetOrganizationSkuFromDatabase"
0x7f02  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x7f07  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string tableName, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x7f0c  stloc.1
0x7f0d  ldloc.1
0x7f0e  call     bool Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class Microsoft.Crm.Data.PropertyBagCollection collection)
0x7f13  brtrue   loc_7FCB
0x7f18  ldloc.1
0x7f19  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x7f1e  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x7f23  stloc.2
0x7f24  br       loc_7FAF
0x7f29  ldloca.s 2
0x7f2b  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x7f30  stloc.3
0x7f31  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x7f36  stloc.s  4
0x7f38  ldloc.s  4
0x7f3a  ldstr    aOrganizationid_1// "OrganizationId"
0x7f3f  ldarg.0
0x7f40  box      [mscorlib]System.Guid
0x7f45  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x7f4a  ldloc.s  4
0x7f4c  ldstr    aServicecompone_0// "ServiceComponentId"
0x7f51  ldloc.3
0x7f52  ldstr    aServicecompone_0// "ServiceComponentId"
0x7f57  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x7f5c  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x7f61  ldloc.0
0x7f62  ldstr    aOrganizationre// "OrganizationResources"
0x7f67  ldc.i4.1
0x7f68  newarr   [mscorlib]System.String
0x7f6d  dup
0x7f6e  ldc.i4.0
0x7f6f  ldstr    aId// "Id"
0x7f74  stelem.ref
0x7f75  ldc.i4.1
0x7f76  newarr   Microsoft.Crm.Data.PropertyBag
0x7f7b  dup
0x7f7c  ldc.i4.0
0x7f7d  ldloc.s  4
0x7f7f  stelem.ref
0x7f80  ldc.i4   0x3BE
0x7f85  ldstr    aGetorganizatio_9// "GetOrganizationSkuFromDatabase"
0x7f8a  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x7f8f  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x7f94  call     bool Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class Microsoft.Crm.Data.PropertyBagCollection collection)
0x7f99  brtrue.s loc_7FAF
0x7f9b  ldloc.3
0x7f9c  ldstr    aName// "Name"
0x7fa1  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x7fa6  isinst   [mscorlib]System.String
0x7fab  stloc.s  5
0x7fad  leave.s  loc_7FD9
0x7faf  ldloca.s 2
0x7fb1  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x7fb6  brtrue   loc_7F29
0x7fbb  leave.s  loc_7FD7
0x7fbd  ldloca.s 2
0x7fbf  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x7fc5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7fca  endfinally
0x7fcb  leave.s  loc_7FD7
0x7fcd  ldloc.0
0x7fce  brfalse.s loc_7FD6
0x7fd0  ldloc.0
0x7fd1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7fd6  endfinally
0x7fd7  ldnull
0x7fd8  ret
0x7fd9  ldloc.s  5
0x7fdb  ret
```
