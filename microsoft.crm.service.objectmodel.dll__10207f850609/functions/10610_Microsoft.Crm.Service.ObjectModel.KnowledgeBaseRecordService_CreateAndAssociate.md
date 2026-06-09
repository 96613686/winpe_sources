# Microsoft.Crm.Service.ObjectModel.KnowledgeBaseRecordService::CreateAndAssociate

- ea: `0x10610`
- end: `0x107c5`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeBaseRecordService::CreateAndAssociate`
- size: `437`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10610`

## string_xrefs

- `0x10795`: `KBInvalidCreateAssociation`

## pseudocode

```c

```

## disassembly

```asm
0x10610  ldstr    aKnowledgebaser// "KnowledgeBaseRecord"
0x10615  ldarg.s  5
0x10617  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1061c  stloc.0
0x1061d  ldloc.0
0x1061e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x10623  ldstr    aKnowledgebaser_0// "knowledgebaserecordid"
0x10628  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1062d  ldloc.0
0x1062e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x10633  ldstr    aUniqueid// "uniqueid"
0x10638  ldc.i4.0
0x10639  ldarg.s  4
0x1063b  ldstr    aUniqueid// "uniqueid"
0x10640  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10645  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1064a  pop
0x1064b  ldarg.0
0x1064c  ldloc.0
0x1064d  ldarg.s  5
0x1064f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x10654  stloc.1
0x10655  ldnull
0x10656  stloc.2
0x10657  ldloc.1
0x10658  brfalse.s loc_106B4
0x1065a  ldloc.1
0x1065b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x10660  brtrue.s loc_106B4
0x10662  ldarg.s  4
0x10664  ldstr    aTitle// "title"
0x10669  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1066e  callvirt instance string [mscorlib]System.Object::ToString()
0x10673  callvirt instance int32 [mscorlib]System.String::get_Length()
0x10678  ldc.i4   0xC8
0x1067d  ble.s    loc_106A7
0x1067f  ldarg.s  4
0x10681  ldstr    aTitle// "title"
0x10686  ldarg.s  4
0x10688  ldstr    aTitle// "title"
0x1068d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10692  callvirt instance string [mscorlib]System.Object::ToString()
0x10697  ldc.i4.0
0x10698  ldc.i4   0xC8
0x1069d  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x106a2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x106a7  ldarg.0
0x106a8  ldarg.s  4
0x106aa  ldarg.s  5
0x106ac  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x106b1  stloc.2
0x106b2  br.s     loc_106DC
0x106b4  ldloc.1
0x106b5  ldc.i4.0
0x106b6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x106bb  ldstr    aKnowledgebaser_0// "knowledgebaserecordid"
0x106c0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x106c5  callvirt instance string [mscorlib]System.Object::ToString()
0x106ca  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x106cf  ldstr    aKnowledgebaser// "KnowledgeBaseRecord"
0x106d4  ldarg.s  5
0x106d6  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x106db  stloc.2
0x106dc  ldarg.s  5
0x106de  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x106e3  ldarg.2
0x106e4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x106e9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x106ee  stloc.3
0x106ef  ldarg.1
0x106f0  ldloc.3
0x106f1  ldarg.s  5
0x106f3  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x106f8  stloc.s  4
0x106fa  ldarg.0
0x106fb  ldarg.3
0x106fc  ldarg.s  5
0x106fe  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::GetAssociationEntityRelationship(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10703  ldloc.s  4
0x10705  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x1070a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x1070f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship::GetRelationshipInvolvingEntity(valuetype [mscorlib]System.Guid)
0x10714  stloc.s  5
0x10716  ldloc.s  5
0x10718  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0x1071d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x10722  ldarg.s  5
0x10724  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x10729  stloc.0
0x1072a  ldloc.0
0x1072b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x10730  ldstr    aKnowledgebaser_0// "knowledgebaserecordid"
0x10735  ldc.i4.0
0x10736  ldloc.2
0x10737  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x1073c  stloc.s  7
0x1073e  ldloca.s 7
0x10740  constrained. [mscorlib]System.Guid
0x10746  callvirt instance string [mscorlib]System.Object::ToString()
0x1074b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x10750  pop
0x10751  ldloc.0
0x10752  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x10757  ldloc.s  5
0x10759  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingColumnName()
0x1075e  ldc.i4.0
0x1075f  ldarg.1
0x10760  box      [mscorlib]System.Guid
0x10765  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1076a  pop
0x1076b  ldarg.0
0x1076c  ldloc.0
0x1076d  ldarg.s  5
0x1076f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x10774  stloc.s  6
0x10776  ldloc.s  6
0x10778  brfalse.s loc_10790
0x1077a  ldloc.s  6
0x1077c  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x10781  brtrue.s loc_10790
0x10783  ldarg.0
0x10784  ldloc.s  4
0x10786  ldloc.2
0x10787  ldarg.3
0x10788  ldarg.s  5
0x1078a  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::CreateAssociation(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1078f  ret
0x10790  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10795  ldstr    aKbinvalidcreat// "KBInvalidCreateAssociation"
0x1079a  ldarg.s  5
0x1079c  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x107a1  ldc.i4.1
0x107a2  newarr   [mscorlib]System.Object
0x107a7  dup
0x107a8  ldc.i4.0
0x107a9  ldloc.3
0x107aa  stelem.ref
0x107ab  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x107b0  ldc.i4   0x80060861
0x107b5  ldc.i4.1
0x107b6  newarr   [mscorlib]System.Object
0x107bb  dup
0x107bc  ldc.i4.0
0x107bd  ldloc.3
0x107be  stelem.ref
0x107bf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32, object[])
0x107c4  throw
```
