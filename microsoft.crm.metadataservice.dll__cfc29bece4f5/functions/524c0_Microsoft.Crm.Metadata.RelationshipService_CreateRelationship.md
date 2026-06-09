# Microsoft.Crm.Metadata.RelationshipService::CreateRelationship

- ea: `0x524c0`
- end: `0x52d81`
- name: `Microsoft.Crm.Metadata.RelationshipService::CreateRelationship`
- size: `2241`
- prototype: ``
- caller_count: `26`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x50640`
- `0x50a20`
- `0x50c20`
- `0x50c80`
- `0x50cf0`
- `0x50d50`
- `0x50e20`
- `0x50e80`
- `0x50ee0`
- `0x50f40`
- `0x51000`
- `0x51190`
- `0x51200`
- `0x51260`
- `0x512c0`
- `0x51320`
- `0x51380`
- `0x513e0`
- `0x51440`
- `0x51eb0`
- `0x51f10`
- `0x51f70`
- `0x51ff0`
- `0x52080`
- `0x52160`
- `0x5b3d0`

## callees

- `0x52490`
- `0x524c0`
- `0x52d90`
- `0x55090`
- `0x55950`
- `0x55bd0`
- `0x58380`
- `0x58430`
- `0x584e0`
- `0x58550`
- `0x59340`
- `0x59360`

## string_xrefs

- `0x52c16`: `CheckExistingBeforeCreateForInternalSystemConvertedSolutions`
- `0x52c29`: `CheckExistingBeforeCreateForInternalSystemConvertedSolutions`
- `0x52791`: `PrincipalObjectAttributeAccess`
- `0x52870`: `PrincipalObjectAttributeAccess`
- `0x52784`: `BulkDeleteFailure`
- `0x5282f`: `BulkDeleteFailure`

## pseudocode

```c

```

## disassembly

```asm
0x524c0  ldc.i4.0
0x524c1  stloc.0
0x524c2  ldstr    asc_804C0// ""
0x524c7  stloc.1
0x524c8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x524cd  stloc.2
0x524ce  ldc.i4.0
0x524cf  stloc.3
0x524d0  ldarg.s  9
0x524d2  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x524d7  stloc.s  4
0x524d9  ldloc.s  4
0x524db  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x524e0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_RelationshipId(valuetype [mscorlib]System.Guid)
0x524e5  ldarg.3
0x524e6  ldstr    aEntityid// "entityid"
0x524eb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x524f0  unbox.any [mscorlib]System.Guid
0x524f5  stloc.s  5
0x524f7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::.ctor()
0x524fc  stloc.s  6
0x524fe  ldarg.3
0x524ff  ldstr    aOwnershiptypem// "ownershiptypemask"
0x52504  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x52509  brtrue.s loc_52525
0x5250b  ldarg.3
0x5250c  ldstr    aLogicalname// "logicalname"
0x52511  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x52516  brtrue.s loc_52525
0x52518  ldarg.3
0x52519  ldstr    aObjecttypecode_0// "objecttypecode"
0x5251e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x52523  brfalse.s loc_52570
0x52525  ldloc.s  6
0x52527  ldloc.s  5
0x52529  ldstr    aEntity_0// "Entity"
0x5252e  ldarg.s  9
0x52530  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x52535  ldstr    aEntity_0// "Entity"
0x5253a  ldc.i4.4
0x5253b  newarr   [mscorlib]System.String
0x52540  dup
0x52541  ldc.i4.0
0x52542  ldstr    aEntityid// "entityid"
0x52547  stelem.ref
0x52548  dup
0x52549  ldc.i4.1
0x5254a  ldstr    aOwnershiptypem// "ownershiptypemask"
0x5254f  stelem.ref
0x52550  dup
0x52551  ldc.i4.2
0x52552  ldstr    aLogicalname// "logicalname"
0x52557  stelem.ref
0x52558  dup
0x52559  ldc.i4.3
0x5255a  ldstr    aObjecttypecode_0// "objecttypecode"
0x5255f  stelem.ref
0x52560  ldarg.s  9
0x52562  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::CreateColumnsCollection(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x52567  ldarg.s  9
0x52569  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveAsIfPublished(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5256e  starg.s  3
0x52570  ldarg.s  9
0x52572  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.MetadataCacheUtil::IsStagedMetadataCacheAndPartialLoadMetadataCacheEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x52577  brfalse.s loc_525B6
0x52579  ldarg.s  9
0x5257b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x52580  ldarg.0
0x52581  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x52586  dup
0x52587  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x5258c  stloc.s  7
0x5258e  dup
0x5258f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CollectionName()
0x52594  stloc.s  8
0x52596  dup
0x52597  ldarg.1
0x52598  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x5259d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x525a2  stloc.s  9
0x525a4  ldarg.2
0x525a5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x525aa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x525af  stloc.s  0xA
0x525b1  br       loc_52689
0x525b6  ldloc.s  6
0x525b8  ldarg.0
0x525b9  ldstr    aEntity_0// "Entity"
0x525be  ldc.i4.2
0x525bf  newarr   [mscorlib]System.String
0x525c4  dup
0x525c5  ldc.i4.0
0x525c6  ldstr    aEntityid// "entityid"
0x525cb  stelem.ref
0x525cc  dup
0x525cd  ldc.i4.1
0x525ce  ldstr    aCollectionname// "collectionname"
0x525d3  stelem.ref
0x525d4  ldarg.s  9
0x525d6  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::CreateColumnsCollection(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x525db  ldarg.s  9
0x525dd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x525e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::RetrieveByNameAsIfPublished(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x525e7  dup
0x525e8  ldstr    aEntityid// "entityid"
0x525ed  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x525f2  unbox.any [mscorlib]System.Guid
0x525f7  stloc.s  7
0x525f9  ldstr    aCollectionname// "collectionname"
0x525fe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x52603  castclass [mscorlib]System.String
0x52608  stloc.s  8
0x5260a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.AttributeService::.ctor()
0x5260f  stloc.s  0x11
0x52611  ldloc.s  0x11
0x52613  ldarg.1
0x52614  ldloc.s  7
0x52616  ldstr    aAttribute// "Attribute"
0x5261b  ldc.i4.1
0x5261c  newarr   [mscorlib]System.String
0x52621  dup
0x52622  ldc.i4.0
0x52623  ldstr    aAttributeid// "attributeid"
0x52628  stelem.ref
0x52629  ldarg.s  9
0x5262b  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::CreateColumnsCollection(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x52630  ldarg.s  9
0x52632  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x52637  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.AttributeService::RetrieveAttributeByNameAndEntityIdAsIfPublished(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x5263c  ldstr    aAttributeid// "attributeid"
0x52641  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x52646  unbox.any [mscorlib]System.Guid
0x5264b  stloc.s  9
0x5264d  ldloc.s  0x11
0x5264f  ldarg.2
0x52650  ldloc.s  7
0x52652  ldstr    aAttribute// "Attribute"
0x52657  ldc.i4.1
0x52658  newarr   [mscorlib]System.String
0x5265d  dup
0x5265e  ldc.i4.0
0x5265f  ldstr    aAttributeid// "attributeid"
0x52664  stelem.ref
0x52665  ldarg.s  9
0x52667  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::CreateColumnsCollection(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5266c  ldarg.s  9
0x5266e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x52673  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.AttributeService::RetrieveAttributeByNameAndEntityIdAsIfPublished(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x52678  ldstr    aAttributeid// "attributeid"
0x5267d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x52682  unbox.any [mscorlib]System.Guid
0x52687  stloc.s  0xA
0x52689  ldloc.s  7
0x5268b  ldloc.s  9
0x5268d  ldarg.s  9
0x5268f  call     void Microsoft.Crm.Metadata.RelationshipService::TrackChangesForReferencingEntity(valuetype [mscorlib]System.Guid referencingEntityId, valuetype [mscorlib]System.Guid referencingAttributeId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x52694  ldarg.3
0x52695  ldstr    aLogicalname// "logicalname"
0x5269a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5269f  castclass [mscorlib]System.String
0x526a4  stloc.s  0xB
0x526a6  ldloc.s  4
0x526a8  ldloc.s  0xB
0x526aa  ldloc.s  8
0x526ac  ldarg.0
0x526ad  ldarg.1
0x526ae  call     string Microsoft.Crm.Metadata.RelationshipService::CreateRelationshipName(string referencedEntityLogicalName, string referencingEntityCollectionName, string referencingEntityName, string referencingAttributeName)
0x526b3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_Name(string)
0x526b8  ldarg.0
0x526b9  ldstr    aExternalpartyi// "ExternalPartyItem"
0x526be  callvirt instance bool [mscorlib]System.String::Equals(string)
0x526c3  brfalse.s loc_52721
0x526c5  ldarg.s  9
0x526c7  call     bool Microsoft.Crm.Metadata.UpgradeHelper::IsInUpdateViaCreateDuringUpgradeContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x526cc  brtrue.s loc_52721
0x526ce  ldloc.s  4
0x526d0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_Name()
0x526d5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x526da  brfalse.s loc_526EC
0x526dc  ldstr    aTheSchemaNameO// "The schema name of an entity relationsh"...
0x526e1  ldc.i4   0x8004432A
0x526e6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x526eb  throw
0x526ec  ldloc.s  4
0x526ee  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_Name()
0x526f3  newobj   instance void Microsoft.Crm.Metadata.SchemaNameValidator::.ctor(string schemaName)
0x526f8  dup
0x526f9  callvirt instance void Microsoft.Crm.Metadata.SchemaNameValidator::ValidateKeywordConflict()
0x526fe  dup
0x526ff  ldc.i4.s 0x64
0x52701  callvirt instance void Microsoft.Crm.Metadata.SchemaNameValidator::ValidateSchemaName(int32 len)
0x52706  ldstr    aEntityrelation_3// "EntityRelationship"
0x5270b  ldstr    aSchemaname// "schemaname"
0x52710  ldc.i4   0x8004432B
0x52715  ldarg.s  9
0x52717  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5271c  callvirt instance void Microsoft.Crm.Metadata.SchemaNameValidator::ValidateSchemaNameIsUnique(string metadataEntityName, string attributeName, int32 errorCodeToThrow, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x52721  ldloc.s  4
0x52723  ldloc.s  7
0x52725  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_ReferencingEntityId(valuetype [mscorlib]System.Guid)
0x5272a  ldloc.s  4
0x5272c  ldloc.s  9
0x5272e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_ReferencingAttributeId(valuetype [mscorlib]System.Guid)
0x52733  ldloc.s  4
0x52735  ldloc.s  5
0x52737  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_ReferencedEntityId(valuetype [mscorlib]System.Guid)
0x5273c  ldloc.s  4
0x5273e  ldarg.s  4
0x52740  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_ReferencedAttributeId(valuetype [mscorlib]System.Guid)
0x52745  ldarg.3
0x52746  ldstr    aIntroducedvers// "introducedversion"
0x5274b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x52750  brtrue.s loc_52772
0x52752  ldarg.s  8
0x52754  brtrue.s loc_52772
0x52756  ldloc.s  4
0x52758  ldarg.3
0x52759  ldstr    aIntroducedvers// "introducedversion"
0x5275e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x52763  castclass [mscorlib]System.String
0x52768  call     class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToVersionFromString(string)
0x5276d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x52772  ldloc.s  4
0x52774  ldc.i4.1
0x52775  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_IsLogical(bool)
0x5277a  ldloc.s  4
0x5277c  ldarg.s  8
0x5277e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_IsCustomRelationship(bool)
0x52783  ldarg.0
0x52784  ldstr    aBulkdeletefail// "BulkDeleteFailure"
0x52789  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5278e  brtrue.s loc_527B7
0x52790  ldarg.0
0x52791  ldstr    aPrincipalobjec// "PrincipalObjectAttributeAccess"
0x52796  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5279b  brtrue.s loc_527B7
0x5279d  ldarg.0
0x5279e  ldstr    aPostregarding_0// "PostRegarding"
0x527a3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x527a8  brtrue.s loc_527B7
0x527aa  ldarg.0
0x527ab  ldstr    aPostrole_0// "PostRole"
0x527b0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x527b5  brfalse.s loc_527C1
0x527b7  ldloc.s  4
0x527b9  ldc.i4.0
0x527ba  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_IsValidForAdvancedFind(bool)
0x527bf  br.s     loc_527C9
0x527c1  ldloc.s  4
0x527c3  ldc.i4.1
0x527c4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_IsValidForAdvancedFind(bool)
0x527c9  ldloc.s  4
0x527cb  ldarg.s  6
0x527cd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_RelationshipType(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipTypes)
0x527d2  ldarg.0
0x527d3  ldstr    aAsyncoperation_0// "AsyncOperation"
0x527d8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x527dd  brtrue.s loc_527F9
0x527df  ldarg.0
0x527e0  ldstr    aProcesssession_0// "ProcessSession"
0x527e5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x527ea  brtrue.s loc_527F9
0x527ec  ldarg.0
0x527ed  ldstr    aWorkflowlog// "WorkflowLog"
0x527f2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x527f7  brfalse.s loc_5282E
0x527f9  ldloc.s  4
0x527fb  ldc.i4.0
0x527fc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeAssign(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x52801  ldloc.s  4
0x52803  ldc.i4.0
0x52804  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeShare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x52809  ldloc.s  4
0x5280b  ldc.i4.0
0x5280c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeUnshare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x52811  ldloc.s  4
0x52813  ldc.i4.0
0x52814  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeReparent(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x52819  ldloc.s  4
0x5281b  ldc.i4.0
0x5281c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeDelete(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x52821  ldloc.s  4
0x52823  ldc.i4.0
0x52824  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeMerge(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x52829  br       loc_52A65
0x5282e  ldarg.0
0x5282f  ldstr    aBulkdeletefail// "BulkDeleteFailure"
0x52834  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52839  brtrue.s loc_528A3
0x5283b  ldarg.0
0x5283c  ldstr    aDuplicaterecor// "DuplicateRecord"
0x52841  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52846  brtrue.s loc_528A3
0x52848  ldarg.0
0x52849  ldstr    aQueueitem// "QueueItem"
0x5284e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52853  brtrue.s loc_528A3
0x52855  ldarg.0
0x52856  ldstr    aConnection_0// "Connection"
0x5285b  call     bool [mscorlib]System.String::op_Equality(string, string)
  ... truncated ...
```
