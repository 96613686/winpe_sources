# Microsoft.Crm.Metadata.RelationshipEligibilityChecker::GetAllowedReferencingEntities_0

- ea: `0x4de20`
- end: `0x4df8e`
- name: `Microsoft.Crm.Metadata.RelationshipEligibilityChecker::GetAllowedReferencingEntities_0`
- size: `366`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x2f2d0`
- `0x4ddd0`

## callees

- `0x4d940`
- `0x4de20`
- `0x4e010`
- `0x4e1c0`
- `0x5a810`
- `0x5da50`

## string_xrefs

- `0x4de26`: `prvReadRelationship`
- `0x4dea4`: `issecurityintersect`

## pseudocode

```c

```

## disassembly

```asm
0x4de20  ldarg.2
0x4de21  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x4de26  ldstr    aPrvreadrelatio// "prvReadRelationship"
0x4de2b  ldarg.2
0x4de2c  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4de31  ldarg.2
0x4de32  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4de37  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x4de3c  stloc.0
0x4de3d  ldnull
0x4de3e  stloc.1
0x4de3f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4de44  ldarg.1
0x4de45  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4de4a  brfalse.s loc_4DE79
0x4de4c  ldarg.0
0x4de4d  ldarg.1
0x4de4e  call     instance bool Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntityBeReferencedEntity(valuetype [mscorlib]System.Guid possibleReferencedEntityId)
0x4de53  brtrue.s loc_4DE5C
0x4de55  ldloc.0
0x4de56  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x4de5b  ret
0x4de5c  ldstr    aEntity_0// "Entity"
0x4de61  ldarg.2
0x4de62  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4de67  stloc.1
0x4de68  ldloc.1
0x4de69  ldstr    aEntityid// "entityid"
0x4de6e  ldarg.1
0x4de6f  box      [mscorlib]System.Guid
0x4de74  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x4de79  ldstr    aEntity_0// "Entity"
0x4de7e  ldarg.2
0x4de7f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4de84  stloc.2
0x4de85  ldloc.2
0x4de86  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x4de8b  ldc.i4.s 0xA
0x4de8d  newarr   [mscorlib]System.String
0x4de92  dup
0x4de93  ldc.i4.0
0x4de94  ldstr    aEntityid// "entityid"
0x4de99  stelem.ref
0x4de9a  dup
0x4de9b  ldc.i4.1
0x4de9c  ldstr    aIsintersect// "isintersect"
0x4dea1  stelem.ref
0x4dea2  dup
0x4dea3  ldc.i4.2
0x4dea4  ldstr    aIssecurityinte// "issecurityintersect"
0x4dea9  stelem.ref
0x4deaa  dup
0x4deab  ldc.i4.3
0x4deac  ldstr    aName// "name"
0x4deb1  stelem.ref
0x4deb2  dup
0x4deb3  ldc.i4.4
0x4deb4  ldstr    aIscustomizable// "iscustomizable"
0x4deb9  stelem.ref
0x4deba  dup
0x4debb  ldc.i4.5
0x4debc  ldstr    aIsmanaged// "ismanaged"
0x4dec1  stelem.ref
0x4dec2  dup
0x4dec3  ldc.i4.6
0x4dec4  ldstr    aCanbeincustomr// "canbeincustomreflexiverelationship"
0x4dec9  stelem.ref
0x4deca  dup
0x4decb  ldc.i4.7
0x4decc  ldstr    aObjecttypecode_0// "objecttypecode"
0x4ded1  stelem.ref
0x4ded2  dup
0x4ded3  ldc.i4.8
0x4ded4  ldstr    aIssolutionawar// "issolutionaware"
0x4ded9  stelem.ref
0x4deda  dup
0x4dedb  ldc.i4.s 9
0x4dedd  ldstr    aCanberelateden// "canberelatedentityinrelationship"
0x4dee2  stelem.ref
0x4dee3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumns(string[])
0x4dee8  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x4deed  ldloc.2
0x4deee  ldarg.2
0x4deef  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4def4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x4def9  ldc.i4.2
0x4defa  ldarg.2
0x4defb  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Metadata.SavedQueryHelper::GetEntitiesWithViewType(int32 queryType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4df00  stloc.3
0x4df01  ldc.i4.0
0x4df02  stloc.s  4
0x4df04  ldnull
0x4df05  stloc.s  5
0x4df07  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x4df0c  stloc.s  6
0x4df0e  br.s     loc_4DF70
0x4df10  ldloc.s  6
0x4df12  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x4df17  stloc.s  7
0x4df19  ldloc.s  7
0x4df1b  ldstr    aEntityid// "entityid"
0x4df20  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4df25  unbox.any [mscorlib]System.Guid
0x4df2a  stloc.s  8
0x4df2c  ldloc.s  7
0x4df2e  ldstr    aObjecttypecode_0// "objecttypecode"
0x4df33  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4df38  unbox.any [mscorlib]System.Int32
0x4df3d  stloc.s  9
0x4df3f  ldarg.0
0x4df40  ldloc.s  7
0x4df42  ldloc.3
0x4df43  ldloc.s  9
0x4df45  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::ContainsKey(var<u1>)
0x4df4a  ldarg.2
0x4df4b  ldloca.s 4
0x4df4d  ldloca.s 5
0x4df4f  call     instance bool Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntityBeReferencingEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity possibleReferencingEntityData, bool doesEntityHaveAssociationGrid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] int32& errorCode, [out] string& exceptionMessage)
0x4df54  brfalse.s loc_4DF70
0x4df56  ldloc.1
0x4df57  brfalse.s loc_4DF68
0x4df59  ldarg.0
0x4df5a  ldloc.1
0x4df5b  ldloc.s  7
0x4df5d  ldloca.s 4
0x4df5f  ldloca.s 5
0x4df61  call     instance bool Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntitiesFormRelationshipPair(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity possibleReferencedEntityData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity possibleReferencingEntityData, [out] int32& errorCode, [out] string& exceptionMessage)
0x4df66  brfalse.s loc_4DF70
0x4df68  ldloc.0
0x4df69  ldloc.s  8
0x4df6b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x4df70  ldloc.s  6
0x4df72  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4df77  brtrue.s loc_4DF10
0x4df79  leave.s  loc_4DF87
0x4df7b  ldloc.s  6
0x4df7d  brfalse.s loc_4DF86
0x4df7f  ldloc.s  6
0x4df81  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4df86  endfinally
0x4df87  ldloc.0
0x4df88  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x4df8d  ret
```
