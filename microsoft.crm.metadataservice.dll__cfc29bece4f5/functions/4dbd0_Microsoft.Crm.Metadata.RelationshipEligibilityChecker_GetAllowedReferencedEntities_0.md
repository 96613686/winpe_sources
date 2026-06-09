# Microsoft.Crm.Metadata.RelationshipEligibilityChecker::GetAllowedReferencedEntities_0

- ea: `0x4dbd0`
- end: `0x4ddc5`
- name: `Microsoft.Crm.Metadata.RelationshipEligibilityChecker::GetAllowedReferencedEntities_0`
- size: `501`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x2f2b0`
- `0x4db80`

## callees

- `0x4da50`
- `0x4dbd0`
- `0x4df90`
- `0x4e1c0`
- `0x4e2a0`
- `0x5a810`
- `0x5da50`

## string_xrefs

- `0x4dbd6`: `prvReadRelationship`
- `0x4dc63`: `issecurityintersect`

## pseudocode

```c

```

## disassembly

```asm
0x4dbd0  ldarg.2
0x4dbd1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x4dbd6  ldstr    aPrvreadrelatio// "prvReadRelationship"
0x4dbdb  ldarg.2
0x4dbdc  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4dbe1  ldarg.2
0x4dbe2  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4dbe7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x4dbec  stloc.0
0x4dbed  ldnull
0x4dbee  stloc.1
0x4dbef  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4dbf4  ldarg.1
0x4dbf5  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4dbfa  brfalse.s loc_4DC39
0x4dbfc  ldarg.0
0x4dbfd  ldarg.1
0x4dbfe  call     instance bool Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntityBeReferencingEntity(valuetype [mscorlib]System.Guid possibleReferencingEntityId)
0x4dc03  brtrue.s loc_4DC0C
0x4dc05  ldloc.0
0x4dc06  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x4dc0b  ret
0x4dc0c  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x4dc11  ldarg.1
0x4dc12  ldstr    aEntity_0// "Entity"
0x4dc17  ldc.i4.2
0x4dc18  newarr   [mscorlib]System.String
0x4dc1d  dup
0x4dc1e  ldc.i4.0
0x4dc1f  ldstr    aEntityid// "entityid"
0x4dc24  stelem.ref
0x4dc25  dup
0x4dc26  ldc.i4.1
0x4dc27  ldstr    aCanbeincustomr// "canbeincustomreflexiverelationship"
0x4dc2c  stelem.ref
0x4dc2d  ldarg.2
0x4dc2e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4dc33  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x4dc38  stloc.1
0x4dc39  ldstr    aEntity_0// "Entity"
0x4dc3e  ldarg.2
0x4dc3f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4dc44  stloc.2
0x4dc45  ldloc.2
0x4dc46  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x4dc4b  ldc.i4.7
0x4dc4c  newarr   [mscorlib]System.String
0x4dc51  dup
0x4dc52  ldc.i4.0
0x4dc53  ldstr    aEntityid// "entityid"
0x4dc58  stelem.ref
0x4dc59  dup
0x4dc5a  ldc.i4.1
0x4dc5b  ldstr    aIsintersect// "isintersect"
0x4dc60  stelem.ref
0x4dc61  dup
0x4dc62  ldc.i4.2
0x4dc63  ldstr    aIssecurityinte// "issecurityintersect"
0x4dc68  stelem.ref
0x4dc69  dup
0x4dc6a  ldc.i4.3
0x4dc6b  ldstr    aName// "name"
0x4dc70  stelem.ref
0x4dc71  dup
0x4dc72  ldc.i4.4
0x4dc73  ldstr    aObjecttypecode_0// "objecttypecode"
0x4dc78  stelem.ref
0x4dc79  dup
0x4dc7a  ldc.i4.5
0x4dc7b  ldstr    aIsshareableacr// "isshareableacrossorgs"
0x4dc80  stelem.ref
0x4dc81  dup
0x4dc82  ldc.i4.6
0x4dc83  ldstr    aCanbeprimaryen// "canbeprimaryentityinrelationship"
0x4dc88  stelem.ref
0x4dc89  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumns(string[])
0x4dc8e  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x4dc93  ldloc.2
0x4dc94  ldarg.2
0x4dc95  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4dc9a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x4dc9f  stloc.3
0x4dca0  ldc.i4.s 0x40
0x4dca2  ldarg.2
0x4dca3  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Metadata.SavedQueryHelper::GetEntitiesWithViewType(int32 queryType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4dca8  stloc.s  4
0x4dcaa  ldstr    aAttribute// "Attribute"
0x4dcaf  ldarg.2
0x4dcb0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4dcb5  stloc.s  5
0x4dcb7  ldloc.s  5
0x4dcb9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x4dcbe  ldc.i4.2
0x4dcbf  newarr   [mscorlib]System.String
0x4dcc4  dup
0x4dcc5  ldc.i4.0
0x4dcc6  ldstr    aIslogical// "islogical"
0x4dccb  stelem.ref
0x4dccc  dup
0x4dccd  ldc.i4.1
0x4dcce  ldstr    aEntityid// "entityid"
0x4dcd3  stelem.ref
0x4dcd4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumns(string[])
0x4dcd9  ldloc.s  5
0x4dcdb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x4dce0  ldstr    aDisplaymask// "displaymask"
0x4dce5  ldc.i4.5
0x4dce6  ldc.i4   0x100
0x4dceb  box      [mscorlib]System.Int32
0x4dcf0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, object)
0x4dcf5  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x4dcfa  ldloc.s  5
0x4dcfc  ldarg.2
0x4dcfd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4dd02  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x4dd07  stloc.s  6
0x4dd09  ldc.i4.0
0x4dd0a  stloc.s  7
0x4dd0c  ldnull
0x4dd0d  stloc.s  8
0x4dd0f  ldloc.3
0x4dd10  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x4dd15  stloc.s  9
0x4dd17  br       loc_4DDA4
0x4dd1c  ldloc.s  9
0x4dd1e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x4dd23  stloc.s  0xA
0x4dd25  ldloc.s  4
0x4dd27  ldloc.s  0xA
0x4dd29  ldstr    aObjecttypecode_0// "objecttypecode"
0x4dd2e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4dd33  unbox.any [mscorlib]System.Int32
0x4dd38  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::ContainsKey(var<u1>)
0x4dd3d  stloc.s  0xB
0x4dd3f  ldloc.s  0xA
0x4dd41  ldstr    aEntityid// "entityid"
0x4dd46  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4dd4b  unbox.any [mscorlib]System.Guid
0x4dd50  stloc.s  0xC
0x4dd52  ldarg.0
0x4dd53  ldloc.s  6
0x4dd55  ldloc.s  0xC
0x4dd57  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.RelationshipEligibilityChecker::GetAttributeDataByEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection attributes, valuetype [mscorlib]System.Guid entityId)
0x4dd5c  stloc.s  0xD
0x4dd5e  ldloc.s  0xD
0x4dd60  brfalse.s loc_4DD75
0x4dd62  ldloc.s  0xD
0x4dd64  ldstr    aIslogical// "islogical"
0x4dd69  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4dd6e  unbox.any [mscorlib]System.Boolean
0x4dd73  br.s     loc_4DD76
0x4dd75  ldc.i4.1
0x4dd76  stloc.s  0xE
0x4dd78  ldarg.0
0x4dd79  ldloc.s  0xA
0x4dd7b  ldloc.s  0xE
0x4dd7d  ldloc.s  0xB
0x4dd7f  ldloca.s 7
0x4dd81  ldloca.s 8
0x4dd83  call     instance bool Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntityBeReferencedEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity possibleReferencedEntityData, bool isPrimaryNameAttributeLogicalOrMissing, bool doesEntityHaveLookupView, [out] int32& errorCode, [out] string& exceptionMessage)
0x4dd88  brfalse.s loc_4DDA4
0x4dd8a  ldloc.1
0x4dd8b  brfalse.s loc_4DD9C
0x4dd8d  ldarg.0
0x4dd8e  ldloc.s  0xA
0x4dd90  ldloc.1
0x4dd91  ldloca.s 7
0x4dd93  ldloca.s 8
0x4dd95  call     instance bool Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntitiesFormRelationshipPair(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity possibleReferencedEntityData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity possibleReferencingEntityData, [out] int32& errorCode, [out] string& exceptionMessage)
0x4dd9a  brfalse.s loc_4DDA4
0x4dd9c  ldloc.0
0x4dd9d  ldloc.s  0xC
0x4dd9f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x4dda4  ldloc.s  9
0x4dda6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4ddab  brtrue   loc_4DD1C
0x4ddb0  leave.s  loc_4DDBE
0x4ddb2  ldloc.s  9
0x4ddb4  brfalse.s loc_4DDBD
0x4ddb6  ldloc.s  9
0x4ddb8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ddbd  endfinally
0x4ddbe  ldloc.0
0x4ddbf  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x4ddc4  ret
```
