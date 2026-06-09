# Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GetRuntimeDependenciesByDependentComponentIdAndType

- ea: `0x64c00`
- end: `0x64ce3`
- name: `Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GetRuntimeDependenciesByDependentComponentIdAndType`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x63870`
- `0x64ba0`

## callees

- `0x64c00`

## string_xrefs

- `0x64c89`: `dependentcomponenttype`
- `0x64c9b`: `requiredcomponenttype`
- `0x64c77`: `dependentcomponentnodeid`
- `0x64cb3`: `requiredcomponentnodeid`

## pseudocode

```c

```

## disassembly

```asm
0x64c00  ldarg.1
0x64c01  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x64c06  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x64c0b  brtrue.s loc_64C11
0x64c0d  ldarg.2
0x64c0e  ldc.i4.0
0x64c0f  bgt.s    loc_64C13
0x64c11  ldnull
0x64c12  ret
0x64c13  ldstr    aRuntimedepende// "RuntimeDependency"
0x64c18  ldarg.3
0x64c19  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x64c1e  stloc.0
0x64c1f  ldarg.0
0x64c20  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RuntimeDependenciesCache Microsoft.Crm.Metadata.Dependency.DependencyProcessor::_runtimeDependenciesCache
0x64c25  ldarg.2
0x64c26  ldarg.3
0x64c27  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RuntimeDependenciesCacheData>::LookupEntry(void, var<u1>)
0x64c2c  stloc.1
0x64c2d  ldloc.1
0x64c2e  brfalse  loc_64CE1
0x64c33  ldloc.1
0x64c34  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRuntimeDependenciesRequiredComponent>> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RuntimeDependenciesCacheData::get_DependentComponents()
0x64c39  brfalse  loc_64CE1
0x64c3e  ldloc.1
0x64c3f  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRuntimeDependenciesRequiredComponent>> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RuntimeDependenciesCacheData::get_DependentComponents()
0x64c44  ldarg.1
0x64c45  ldloca.s 2
0x64c47  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRuntimeDependenciesRequiredComponent>>::TryGetValue(var<u1>, !!T0)
0x64c4c  brfalse  loc_64CE1
0x64c51  ldloc.2
0x64c52  brfalse  loc_64CE1
0x64c57  ldloc.2
0x64c58  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRuntimeDependenciesRequiredComponent>::GetEnumerator()
0x64c5d  stloc.3
0x64c5e  br.s     loc_64CCD
0x64c60  ldloc.3
0x64c61  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRuntimeDependenciesRequiredComponent>::get_Current()
0x64c66  stloc.s  4
0x64c68  ldarg.3
0x64c69  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x64c6e  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.RuntimeDependency::.ctor(valuetype [mscorlib]System.Guid)
0x64c73  stloc.s  5
0x64c75  ldloc.s  5
0x64c77  ldstr    aDependentcompo_3// "dependentcomponentnodeid"
0x64c7c  ldarg.1
0x64c7d  box      [mscorlib]System.Guid
0x64c82  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x64c87  ldloc.s  5
0x64c89  ldstr    aDependentcompo// "dependentcomponenttype"
0x64c8e  ldarg.2
0x64c8f  box      [mscorlib]System.Int32
0x64c94  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x64c99  ldloc.s  5
0x64c9b  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x64ca0  ldloc.s  4
0x64ca2  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRuntimeDependenciesRequiredComponent::get_Type()
0x64ca7  box      [mscorlib]System.Int32
0x64cac  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x64cb1  ldloc.s  5
0x64cb3  ldstr    aRequiredcompon_2// "requiredcomponentnodeid"
0x64cb8  ldloc.s  4
0x64cba  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRuntimeDependenciesRequiredComponent::get_NodeId()
0x64cbf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x64cc4  ldloc.0
0x64cc5  ldloc.s  5
0x64cc7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x64ccc  pop
0x64ccd  ldloc.3
0x64cce  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x64cd3  brtrue.s loc_64C60
0x64cd5  leave.s  loc_64CE1
0x64cd7  ldloc.3
0x64cd8  brfalse.s loc_64CE0
0x64cda  ldloc.3
0x64cdb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64ce0  endfinally
0x64ce1  ldloc.0
0x64ce2  ret
```
