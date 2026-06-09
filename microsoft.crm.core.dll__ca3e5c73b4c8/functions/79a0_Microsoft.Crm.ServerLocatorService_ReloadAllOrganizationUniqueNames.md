# Microsoft.Crm.ServerLocatorService::ReloadAllOrganizationUniqueNames

- ea: `0x79a0`
- end: `0x7acb`
- name: `Microsoft.Crm.ServerLocatorService::ReloadAllOrganizationUniqueNames`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7820`

## callees

- `0x1f80`
- `0x3100`
- `0x79a0`
- `0x9620`
- `0x444f0`

## string_xrefs

- `0x79b2`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x7a51`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x79a0  ldstr    aOrganization// "Organization"
0x79a5  stloc.0
0x79a6  ldarg.0
0x79a7  ldloc.0
0x79a8  ldc.i4   0x2F8
0x79ad  ldstr    aReloadallorgan_1// "ReloadAllOrganizationUniqueNames"
0x79b2  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x79b7  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x79bc  stloc.1
0x79bd  ldloc.1
0x79be  brfalse.s loc_7A36
0x79c0  ldloc.1
0x79c1  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x79c6  brfalse.s loc_7A36
0x79c8  ldloc.1
0x79c9  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x79ce  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x79d3  stloc.2
0x79d4  br.s     loc_7A1D
0x79d6  ldloca.s 2
0x79d8  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x79dd  dup
0x79de  ldstr    aUniquename// "UniqueName"
0x79e3  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x79e8  castclass [mscorlib]System.String
0x79ed  stloc.3
0x79ee  ldstr    aId// "Id"
0x79f3  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x79f8  unbox.any [mscorlib]System.Guid
0x79fd  stloc.s  4
0x79ff  ldarg.0
0x7a00  ldfld    class Microsoft.Crm.ILocatorCache Microsoft.Crm.ServerLocatorService::_cache
0x7a05  ldc.i4.s 0x17
0x7a07  ldloc.3
0x7a08  ldc.i4.1
0x7a09  newarr   [mscorlib]System.Object
0x7a0e  dup
0x7a0f  ldc.i4.0
0x7a10  ldloc.s  4
0x7a12  box      [mscorlib]System.Guid
0x7a17  stelem.ref
0x7a18  callvirt instance void Microsoft.Crm.ILocatorCache::AddEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object value, object[] keys)
0x7a1d  ldloca.s 2
0x7a1f  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x7a24  brtrue.s loc_79D6
0x7a26  leave.s  loc_7A36
0x7a28  ldloca.s 2
0x7a2a  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x7a30  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7a35  endfinally
0x7a36  ldc.i4.2
0x7a37  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.BootstrapService::GetSku()
0x7a3c  bne.un   loc_7ACA
0x7a41  ldarg.0
0x7a42  ldstr    aOrganizationli// "OrganizationLifecycle"
0x7a47  ldc.i4   0x307
0x7a4c  ldstr    aReloadallorgan_1// "ReloadAllOrganizationUniqueNames"
0x7a51  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x7a56  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x7a5b  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x7a60  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x7a65  stloc.2
0x7a66  br.s     loc_7AB1
0x7a68  ldloca.s 2
0x7a6a  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x7a6f  dup
0x7a70  ldstr    aOrganizationun// "OrganizationUniqueName"
0x7a75  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x7a7a  castclass [mscorlib]System.String
0x7a7f  stloc.s  5
0x7a81  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x7a86  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x7a8b  unbox.any [mscorlib]System.Guid
0x7a90  stloc.s  6
0x7a92  ldarg.0
0x7a93  ldfld    class Microsoft.Crm.ILocatorCache Microsoft.Crm.ServerLocatorService::_cache
0x7a98  ldc.i4.s 0x17
0x7a9a  ldloc.s  5
0x7a9c  ldc.i4.1
0x7a9d  newarr   [mscorlib]System.Object
0x7aa2  dup
0x7aa3  ldc.i4.0
0x7aa4  ldloc.s  6
0x7aa6  box      [mscorlib]System.Guid
0x7aab  stelem.ref
0x7aac  callvirt instance void Microsoft.Crm.ILocatorCache::AddEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object value, object[] keys)
0x7ab1  ldloca.s 2
0x7ab3  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x7ab8  brtrue.s loc_7A68
0x7aba  leave.s  loc_7ACA
0x7abc  ldloca.s 2
0x7abe  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x7ac4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7ac9  endfinally
0x7aca  ret
```
