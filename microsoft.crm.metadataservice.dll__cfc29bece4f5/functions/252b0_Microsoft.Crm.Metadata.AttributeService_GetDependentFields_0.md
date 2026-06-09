# Microsoft.Crm.Metadata.AttributeService::GetDependentFields_0

- ea: `0x252b0`
- end: `0x2537c`
- name: `Microsoft.Crm.Metadata.AttributeService::GetDependentFields_0`
- size: `204`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x25220`
- `0x25290`
- `0x25c70`

## callees

- `0x252b0`

## string_xrefs

- `0x252bc`: `service`
- `0x252f5`: `dependentcomponenttype`
- `0x25308`: `dependentcomponentobjectId`

## pseudocode

```c

```

## disassembly

```asm
0x252b0  ldarg.0
0x252b1  ldstr    aAttributeid_0// "attributeId"
0x252b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x252bb  ldarg.2
0x252bc  ldstr    aService// "service"
0x252c1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x252c6  ldarg.3
0x252c7  ldstr    aContext// "context"
0x252cc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x252d1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag>::.ctor()
0x252d6  stloc.0
0x252d7  ldarg.2
0x252d8  ldarg.0
0x252d9  ldc.i4.2
0x252da  ldarg.3
0x252db  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyService::RetrieveDependentComponents(valuetype [mscorlib]System.Guid, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x252e0  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x252e5  stloc.1
0x252e6  br.s     loc_2535C
0x252e8  ldloc.1
0x252e9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x252ee  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x252f3  stloc.2
0x252f4  ldloc.2
0x252f5  ldstr    aDependentcompo// "dependentcomponenttype"
0x252fa  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x252ff  unbox.any [mscorlib]System.Int32
0x25304  ldc.i4.2
0x25305  bne.un.s loc_2535C
0x25307  ldloc.2
0x25308  ldstr    aDependentcompo_0// "dependentcomponentobjectId"
0x2530d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x25312  unbox.any [mscorlib]System.Guid
0x25317  stloc.3
0x25318  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x2531d  ldloc.3
0x2531e  ldstr    aAttribute// "Attribute"
0x25323  ldarg.3
0x25324  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x25329  ldloca.s 4
0x2532b  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::TryRetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity&)
0x25330  brfalse.s loc_2535C
0x25332  ldarg.1
0x25333  ldloc.s  4
0x25335  ldstr    aSourcetype// "sourcetype"
0x2533a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2533f  unbox.any [mscorlib]System.Int32
0x25344  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<int32>::Contains(var<u1>)
0x25349  brfalse.s loc_2535C
0x2534b  ldloc.s  4
0x2534d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x25352  stloc.s  5
0x25354  ldloc.0
0x25355  ldloc.s  5
0x25357  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag>::Add(var<u1>)
0x2535c  ldloc.1
0x2535d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x25362  brtrue.s loc_252E8
0x25364  leave.s  loc_2537A
0x25366  ldloc.1
0x25367  isinst   [mscorlib]System.IDisposable
0x2536c  stloc.s  6
0x2536e  ldloc.s  6
0x25370  brfalse.s loc_25379
0x25372  ldloc.s  6
0x25374  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25379  endfinally
0x2537a  ldloc.0
0x2537b  ret
```
