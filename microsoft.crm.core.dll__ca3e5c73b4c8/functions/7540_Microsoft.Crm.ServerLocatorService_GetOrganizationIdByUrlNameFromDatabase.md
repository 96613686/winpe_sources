# Microsoft.Crm.ServerLocatorService::GetOrganizationIdByUrlNameFromDatabase

- ea: `0x7540`
- end: `0x7682`
- name: `Microsoft.Crm.ServerLocatorService::GetOrganizationIdByUrlNameFromDatabase`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x73c0`

## callees

- `0x7540`
- `0x94f0`
- `0x44400`
- `0x444f0`
- `0x44510`

## string_xrefs

- `0x7582`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x7620`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x7540  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x7545  stloc.0
0x7546  ldloc.0
0x7547  ldstr    aDomainname// "DomainName"
0x754c  ldarg.1
0x754d  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x7552  ldarg.0
0x7553  ldstr    aOrganizationli// "OrganizationLifecycle"
0x7558  ldc.i4.2
0x7559  newarr   [mscorlib]System.String
0x755e  dup
0x755f  ldc.i4.0
0x7560  ldstr    aId// "Id"
0x7565  stelem.ref
0x7566  dup
0x7567  ldc.i4.1
0x7568  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x756d  stelem.ref
0x756e  ldc.i4.1
0x756f  newarr   Microsoft.Crm.Data.PropertyBag
0x7574  dup
0x7575  ldc.i4.0
0x7576  ldloc.0
0x7577  stelem.ref
0x7578  ldc.i4   0x256
0x757d  ldstr    aGetorganizatio_3// "GetOrganizationIdByUrlNameFromDatabase"
0x7582  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x7587  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x758c  stloc.1
0x758d  ldloc.1
0x758e  brfalse.s loc_75DB
0x7590  ldloc.1
0x7591  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x7596  brfalse.s loc_75DB
0x7598  ldloc.1
0x7599  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x759e  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x75a3  stloc.2
0x75a4  br.s     loc_75C2
0x75a6  ldloca.s 2
0x75a8  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x75ad  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x75b2  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x75b7  unbox.any [mscorlib]System.Guid
0x75bc  stloc.3
0x75bd  leave    loc_7680
0x75c2  ldloca.s 2
0x75c4  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x75c9  brtrue.s loc_75A6
0x75cb  leave.s  loc_75DB
0x75cd  ldloca.s 2
0x75cf  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x75d5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x75da  endfinally
0x75db  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x75e0  stloc.s  4
0x75e2  ldloc.s  4
0x75e4  ldstr    aPreviousdomain// "PreviousDomainName"
0x75e9  ldarg.1
0x75ea  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x75ef  ldarg.0
0x75f0  ldstr    aOrganizationli// "OrganizationLifecycle"
0x75f5  ldc.i4.2
0x75f6  newarr   [mscorlib]System.String
0x75fb  dup
0x75fc  ldc.i4.0
0x75fd  ldstr    aId// "Id"
0x7602  stelem.ref
0x7603  dup
0x7604  ldc.i4.1
0x7605  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x760a  stelem.ref
0x760b  ldc.i4.1
0x760c  newarr   Microsoft.Crm.Data.PropertyBag
0x7611  dup
0x7612  ldc.i4.0
0x7613  ldloc.s  4
0x7615  stelem.ref
0x7616  ldc.i4   0x266
0x761b  ldstr    aGetorganizatio_3// "GetOrganizationIdByUrlNameFromDatabase"
0x7620  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x7625  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x762a  stloc.s  5
0x762c  ldloc.s  5
0x762e  brfalse.s loc_767A
0x7630  ldloc.s  5
0x7632  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x7637  brfalse.s loc_767A
0x7639  ldloc.s  5
0x763b  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x7640  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x7645  stloc.2
0x7646  br.s     loc_7661
0x7648  ldloca.s 2
0x764a  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x764f  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x7654  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x7659  unbox.any [mscorlib]System.Guid
0x765e  stloc.3
0x765f  leave.s  loc_7680
0x7661  ldloca.s 2
0x7663  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x7668  brtrue.s loc_7648
0x766a  leave.s  loc_767A
0x766c  ldloca.s 2
0x766e  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x7674  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7679  endfinally
0x767a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x767f  ret
0x7680  ldloc.3
0x7681  ret
```
