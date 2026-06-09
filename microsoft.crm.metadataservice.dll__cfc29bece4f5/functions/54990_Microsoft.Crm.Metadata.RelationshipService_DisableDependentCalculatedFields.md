# Microsoft.Crm.Metadata.RelationshipService::DisableDependentCalculatedFields

- ea: `0x54990`
- end: `0x54a38`
- name: `Microsoft.Crm.Metadata.RelationshipService::DisableDependentCalculatedFields`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x50330`

## callees

- `0x25e10`
- `0x503e0`
- `0x54990`

## string_xrefs

- `0x549bf`: `dependentcomponenttype`
- `0x549d2`: `dependentcomponentobjectId`

## pseudocode

```c

```

## disassembly

```asm
0x54990  ldarg.1
0x54991  ldarg.2
0x54992  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x54997  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.RelationshipService::RetrieveRelationshipIdFromEntityRelationshipId(valuetype [mscorlib]System.Guid entityRelationshipId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x5499c  stloc.0
0x5499d  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyService::.ctor()
0x549a2  ldloc.0
0x549a3  ldc.i4.3
0x549a4  ldarg.2
0x549a5  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyService::RetrieveDependentComponents(valuetype [mscorlib]System.Guid, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x549aa  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x549af  stloc.1
0x549b0  br.s     loc_54A19
0x549b2  ldloc.1
0x549b3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x549b8  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x549bd  stloc.2
0x549be  ldloc.2
0x549bf  ldstr    aDependentcompo// "dependentcomponenttype"
0x549c4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x549c9  unbox.any [mscorlib]System.Int32
0x549ce  ldc.i4.2
0x549cf  bne.un.s loc_54A19
0x549d1  ldloc.2
0x549d2  ldstr    aDependentcompo_0// "dependentcomponentobjectId"
0x549d7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x549dc  unbox.any [mscorlib]System.Guid
0x549e1  stloc.3
0x549e2  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x549e7  ldloc.3
0x549e8  ldstr    aAttribute// "Attribute"
0x549ed  ldarg.2
0x549ee  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x549f3  ldloca.s 4
0x549f5  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::TryRetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity&)
0x549fa  brfalse.s loc_54A19
0x549fc  ldloc.s  4
0x549fe  ldstr    aSourcetype// "sourcetype"
0x54a03  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x54a08  unbox.any [mscorlib]System.Int32
0x54a0d  ldc.i4.1
0x54a0e  bne.un.s loc_54A19
0x54a10  ldloc.s  4
0x54a12  ldc.i4.0
0x54a13  ldarg.2
0x54a14  call     void Microsoft.Crm.Metadata.AttributeService::RegenerateCalculatedColumn(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity attribute, bool formulaIsValid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x54a19  ldloc.1
0x54a1a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x54a1f  brtrue.s loc_549B2
0x54a21  leave.s  loc_54A37
0x54a23  ldloc.1
0x54a24  isinst   [mscorlib]System.IDisposable
0x54a29  stloc.s  5
0x54a2b  ldloc.s  5
0x54a2d  brfalse.s loc_54A36
0x54a2f  ldloc.s  5
0x54a31  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54a36  endfinally
0x54a37  ret
```
