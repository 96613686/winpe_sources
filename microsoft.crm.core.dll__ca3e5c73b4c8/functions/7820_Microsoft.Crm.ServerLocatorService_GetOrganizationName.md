# Microsoft.Crm.ServerLocatorService::GetOrganizationName

- ea: `0x7820`
- end: `0x799b`
- name: `Microsoft.Crm.ServerLocatorService::GetOrganizationName`
- size: `379`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1f80`
- `0x3080`
- `0x3120`
- `0x7820`
- `0x79a0`
- `0x92c0`
- `0x94f0`
- `0x1be90`
- `0x44400`
- `0x444f0`
- `0x44510`

## string_xrefs

- `0x78c1`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x792a`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x7820  ldarg.1
0x7821  ldstr    aOrganizationid_0// "organizationId"
0x7826  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x782b  ldarg.0
0x782c  ldfld    bool Microsoft.Crm.ServerLocatorService::_isRetrieveConditionCacheEnabled
0x7831  brfalse.s loc_789D
0x7833  ldarg.0
0x7834  ldfld    class Microsoft.Crm.ILocatorCache Microsoft.Crm.ServerLocatorService::_cache
0x7839  ldc.i4.s 0x17
0x783b  ldc.i4.1
0x783c  newarr   [mscorlib]System.Object
0x7841  dup
0x7842  ldc.i4.0
0x7843  ldarg.1
0x7844  box      [mscorlib]System.Guid
0x7849  stelem.ref
0x784a  callvirt instance object Microsoft.Crm.ILocatorCache::LookupEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object[] keys)
0x784f  stloc.1
0x7850  ldloc.1
0x7851  brfalse.s loc_785A
0x7853  ldloc.1
0x7854  castclass [mscorlib]System.String
0x7859  ret
0x785a  ldarg.0
0x785b  call     instance void Microsoft.Crm.ServerLocatorService::ReloadAllOrganizationUniqueNames()
0x7860  ldarg.0
0x7861  ldfld    class Microsoft.Crm.ILocatorCache Microsoft.Crm.ServerLocatorService::_cache
0x7866  ldc.i4.s 0x17
0x7868  ldc.i4.1
0x7869  newarr   [mscorlib]System.Object
0x786e  dup
0x786f  ldc.i4.0
0x7870  ldarg.1
0x7871  box      [mscorlib]System.Guid
0x7876  stelem.ref
0x7877  callvirt instance object Microsoft.Crm.ILocatorCache::LookupEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object[] keys)
0x787c  stloc.1
0x787d  ldloc.1
0x787e  brfalse.s loc_7887
0x7880  ldloc.1
0x7881  castclass [mscorlib]System.String
0x7886  ret
0x7887  ldstr    aOrganization// "Organization"
0x788c  ldstr    aId// "Id"
0x7891  ldarg.1
0x7892  box      [mscorlib]System.Guid
0x7897  newobj   instance void Microsoft.Crm.CrmConfigObjectNotFoundException::.ctor(string tableName, string columnName, object id)
0x789c  throw
0x789d  ldarg.0
0x789e  ldstr    aOrganization// "Organization"
0x78a3  ldarg.1
0x78a4  box      [mscorlib]System.Guid
0x78a9  ldc.i4.1
0x78aa  newarr   [mscorlib]System.String
0x78af  dup
0x78b0  ldc.i4.0
0x78b1  ldstr    aUniquename// "UniqueName"
0x78b6  stelem.ref
0x78b7  ldc.i4   0x2D9
0x78bc  ldstr    aGetorganizatio_4// "GetOrganizationName"
0x78c1  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x78c6  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ServerLocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x78cb  stloc.0
0x78cc  ldloc.0
0x78cd  brfalse.s loc_78E0
0x78cf  ldloc.0
0x78d0  ldstr    aUniquename// "UniqueName"
0x78d5  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x78da  castclass [mscorlib]System.String
0x78df  ret
0x78e0  ldc.i4.2
0x78e1  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.BootstrapService::GetSku()
0x78e6  bne.un   loc_7982
0x78eb  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x78f0  stloc.2
0x78f1  ldloc.2
0x78f2  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x78f7  ldarg.1
0x78f8  box      [mscorlib]System.Guid
0x78fd  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x7902  ldarg.0
0x7903  ldstr    aOrganizationli// "OrganizationLifecycle"
0x7908  ldc.i4.1
0x7909  newarr   [mscorlib]System.String
0x790e  dup
0x790f  ldc.i4.0
0x7910  ldstr    aOrganizationun// "OrganizationUniqueName"
0x7915  stelem.ref
0x7916  ldc.i4.1
0x7917  newarr   Microsoft.Crm.Data.PropertyBag
0x791c  dup
0x791d  ldc.i4.0
0x791e  ldloc.2
0x791f  stelem.ref
0x7920  ldc.i4   0x2E5
0x7925  ldstr    aGetorganizatio_4// "GetOrganizationName"
0x792a  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x792f  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x7934  stloc.3
0x7935  ldloc.3
0x7936  brfalse.s loc_7982
0x7938  ldloc.3
0x7939  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x793e  brfalse.s loc_7982
0x7940  ldloc.3
0x7941  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x7946  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x794b  stloc.s  4
0x794d  br.s     loc_7969
0x794f  ldloca.s 4
0x7951  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x7956  ldstr    aOrganizationun// "OrganizationUniqueName"
0x795b  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x7960  castclass [mscorlib]System.String
0x7965  stloc.s  5
0x7967  leave.s  loc_7998
0x7969  ldloca.s 4
0x796b  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x7970  brtrue.s loc_794F
0x7972  leave.s  loc_7982
0x7974  ldloca.s 4
0x7976  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x797c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7981  endfinally
0x7982  ldstr    aOrganization// "Organization"
0x7987  ldstr    aId// "Id"
0x798c  ldarg.1
0x798d  box      [mscorlib]System.Guid
0x7992  newobj   instance void Microsoft.Crm.CrmConfigObjectNotFoundException::.ctor(string tableName, string columnName, object id)
0x7997  throw
0x7998  ldloc.s  5
0x799a  ret
```
