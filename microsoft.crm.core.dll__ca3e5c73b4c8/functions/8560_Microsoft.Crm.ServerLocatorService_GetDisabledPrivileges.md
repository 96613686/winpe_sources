# Microsoft.Crm.ServerLocatorService::GetDisabledPrivileges

- ea: `0x8560`
- end: `0x86e9`
- name: `Microsoft.Crm.ServerLocatorService::GetDisabledPrivileges`
- size: `393`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x8560`
- `0xbfa0`
- `0x1be90`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x4d7e0`
- `0x64b10`

## string_xrefs

- `0x85cd`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x8661`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x85c8`: `GetDisabledPrivileges`
- `0x865c`: `GetDisabledPrivileges`
- `0x8639`: `FeaturePrivilegeMap`
- `0x8646`: `PrivilegeId`
- `0x868d`: `PrivilegeId`

## pseudocode

```c

```

## disassembly

```asm
0x8560  ldarg.1
0x8561  ldstr    aOrganizationid_0// "organizationId"
0x8566  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x856b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x8570  stloc.0
0x8571  call     class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x8576  stloc.1
0x8577  ldloc.1
0x8578  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0x857d  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x8582  stloc.2
0x8583  ldloc.2
0x8584  ldstr    aOrganizationid_1// "OrganizationId"
0x8589  ldarg.1
0x858a  box      [mscorlib]System.Guid
0x858f  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8594  ldloc.2
0x8595  ldstr    aEnabled// "Enabled"
0x859a  ldc.i4.0
0x859b  box      [mscorlib]System.Boolean
0x85a0  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x85a5  ldloc.1
0x85a6  ldstr    aOrganizationfe// "OrganizationFeatureMap"
0x85ab  ldc.i4.1
0x85ac  newarr   [mscorlib]System.String
0x85b1  dup
0x85b2  ldc.i4.0
0x85b3  ldstr    aFeatureid// "FeatureId"
0x85b8  stelem.ref
0x85b9  ldc.i4.1
0x85ba  newarr   Microsoft.Crm.Data.PropertyBag
0x85bf  dup
0x85c0  ldc.i4.0
0x85c1  ldloc.2
0x85c2  stelem.ref
0x85c3  ldc.i4   0x4A9
0x85c8  ldstr    aGetdisabledpri// "GetDisabledPrivileges"
0x85cd  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x85d2  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x85d7  stloc.3
0x85d8  ldloc.3
0x85d9  brfalse  loc_86D6
0x85de  ldloc.3
0x85df  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x85e4  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x85e9  stloc.s  4
0x85eb  br       loc_86BA
0x85f0  ldloca.s 4
0x85f2  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x85f7  stloc.s  5
0x85f9  ldloc.s  5
0x85fb  ldstr    aFeatureid// "FeatureId"
0x8600  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x8605  unbox.any [mscorlib]System.Guid
0x860a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Config.Wrapper.OrganizationFeature::CreateEntity
0x860f  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8614  brtrue   loc_86BA
0x8619  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x861e  stloc.s  6
0x8620  ldloc.s  6
0x8622  ldstr    aFeatureid// "FeatureId"
0x8627  ldloc.s  5
0x8629  ldstr    aFeatureid// "FeatureId"
0x862e  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x8633  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8638  ldloc.1
0x8639  ldstr    aFeatureprivile// "FeaturePrivilegeMap"
0x863e  ldc.i4.1
0x863f  newarr   [mscorlib]System.String
0x8644  dup
0x8645  ldc.i4.0
0x8646  ldstr    aPrivilegeid// "PrivilegeId"
0x864b  stelem.ref
0x864c  ldc.i4.1
0x864d  newarr   Microsoft.Crm.Data.PropertyBag
0x8652  dup
0x8653  ldc.i4.0
0x8654  ldloc.s  6
0x8656  stelem.ref
0x8657  ldc.i4   0x4B9
0x865c  ldstr    aGetdisabledpri// "GetDisabledPrivileges"
0x8661  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x8666  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x866b  stloc.s  7
0x866d  ldloc.s  7
0x866f  brfalse.s loc_86BA
0x8671  ldloc.s  7
0x8673  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x8678  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x867d  stloc.s  8
0x867f  br.s     loc_86A1
0x8681  ldloca.s 8
0x8683  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x8688  stloc.s  9
0x868a  ldloc.0
0x868b  ldloc.s  9
0x868d  ldstr    aPrivilegeid// "PrivilegeId"
0x8692  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x8697  unbox.any [mscorlib]System.Guid
0x869c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x86a1  ldloca.s 8
0x86a3  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x86a8  brtrue.s loc_8681
0x86aa  leave.s  loc_86BA
0x86ac  ldloca.s 8
0x86ae  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x86b4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x86b9  endfinally
0x86ba  ldloca.s 4
0x86bc  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x86c1  brtrue   loc_85F0
0x86c6  leave.s  loc_86E2
0x86c8  ldloca.s 4
0x86ca  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x86d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x86d5  endfinally
0x86d6  leave.s  loc_86E2
0x86d8  ldloc.1
0x86d9  brfalse.s loc_86E1
0x86db  ldloc.1
0x86dc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x86e1  endfinally
0x86e2  ldloc.0
0x86e3  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype [mscorlib]System.Guid>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x86e8  ret
```
