# Microsoft.Crm.Metadata.RelationshipService::CreateActivityRelationship

- ea: `0x50a20`
- end: `0x50c1c`
- name: `Microsoft.Crm.Metadata.RelationshipService::CreateActivityRelationship`
- size: `508`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x33180`
- `0x5db70`
- `0x61ca0`
- `0x64fb0`
- `0x65400`
- `0x78530`

## callees

- `0x4edf0`
- `0x50a20`
- `0x524c0`
- `0x52d90`
- `0x53d80`
- `0x55c80`
- `0x56440`
- `0x56450`

## string_xrefs

- `0x50ba8`: `Cannot create relationships that result in a cycle`

## pseudocode

```c

```

## disassembly

```asm
0x50a20  ldarg.0
0x50a21  ldstr    aActivitynames// "activityNames"
0x50a26  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x50a2b  ldarg.1
0x50a2c  ldstr    aEntitydata// "entityData"
0x50a31  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x50a36  ldarg.2
0x50a37  ldstr    aPrimarykeyid// "primaryKeyId"
0x50a3c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x50a41  ldarg.3
0x50a42  ldstr    aMetadatahelper// "metadataHelper"
0x50a47  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x50a4c  ldarg.s  4
0x50a4e  ldstr    aContext// "context"
0x50a53  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x50a58  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::.ctor()
0x50a5d  stloc.0
0x50a5e  ldstr    aEntity_0// "Entity"
0x50a63  ldc.i4.2
0x50a64  newarr   [mscorlib]System.String
0x50a69  dup
0x50a6a  ldc.i4.0
0x50a6b  ldstr    aEntityid// "entityid"
0x50a70  stelem.ref
0x50a71  dup
0x50a72  ldc.i4.1
0x50a73  ldstr    aName// "name"
0x50a78  stelem.ref
0x50a79  ldarg.s  4
0x50a7b  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::CreateColumnsCollection(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x50a80  stloc.1
0x50a81  newobj   instance void Microsoft.Crm.Metadata.RelationshipService::.ctor()
0x50a86  stloc.2
0x50a87  ldarg.0
0x50a88  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x50a8d  stloc.3
0x50a8e  br       loc_50BFF
0x50a93  ldloca.s 3
0x50a95  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x50a9a  stloc.s  4
0x50a9c  ldnull
0x50a9d  stloc.s  5
0x50a9f  ldc.i4.1
0x50aa0  stloc.s  6
0x50aa2  ldloc.s  4
0x50aa4  ldstr    aActivitypointe// "ActivityPointer"
0x50aa9  callvirt instance bool [mscorlib]System.String::Equals(string)
0x50aae  brfalse  loc_50B6B
0x50ab3  ldc.i4.0
0x50ab4  stloc.s  6
0x50ab6  ldstr    aEntityrelation_2// "EntityRelationshipRole"
0x50abb  ldarg.s  4
0x50abd  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x50ac2  stloc.s  5
0x50ac4  ldloc.s  5
0x50ac6  ldstr    aNavpanedisplay// "navpanedisplayoption"
0x50acb  ldc.i4.0
0x50acc  box      [mscorlib]System.Byte
0x50ad1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x50ad6  ldloc.s  5
0x50ad8  ldstr    aNavpanearea// "navpanearea"
0x50add  ldc.i4.0
0x50ade  box      [mscorlib]System.Byte
0x50ae3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x50ae8  ldloc.s  5
0x50aea  ldstr    aNavpaneorder// "navpaneorder"
0x50aef  ldc.i4.0
0x50af0  box      [mscorlib]System.Int32
0x50af5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x50afa  ldloc.s  5
0x50afc  ldstr    aNavpaneoffline// "navpaneoffline"
0x50b01  ldc.i4.1
0x50b02  box      [mscorlib]System.Boolean
0x50b07  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x50b0c  ldloc.s  5
0x50b0e  ldstr    aNavpaneiscusto// "navpaneiscustomizable"
0x50b13  ldc.i4.1
0x50b14  box      [mscorlib]System.Boolean
0x50b19  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x50b1e  ldarg.3
0x50b1f  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x50b24  brfalse.s loc_50B6B
0x50b26  ldarg.s  4
0x50b28  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRoleOverrider::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x50b2d  ldarg.s  4
0x50b2f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x50b34  ldloc.s  4
0x50b36  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x50b3b  stloc.s  9
0x50b3d  ldarg.1
0x50b3e  ldstr    aLogicalname// "logicalname"
0x50b43  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x50b48  castclass [mscorlib]System.String
0x50b4d  ldloc.s  9
0x50b4f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CollectionName()
0x50b54  ldloc.s  4
0x50b56  ldstr    aRegardingobjec// "regardingobjectid"
0x50b5b  call     string Microsoft.Crm.Metadata.RelationshipService::CreateRelationshipName(string referencedEntityLogicalName, string referencingEntityCollectionName, string referencingEntityName, string referencingAttributeName)
0x50b60  stloc.s  0xA
0x50b62  ldloc.s  0xA
0x50b64  ldloc.s  5
0x50b66  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleOverrider::OverrideEntityRelationshipRole(string schemaName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity)
0x50b6b  ldloc.0
0x50b6c  ldloc.s  4
0x50b6e  ldloc.1
0x50b6f  ldarg.s  4
0x50b71  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x50b76  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::RetrieveByNameAsIfPublished(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x50b7b  stloc.s  7
0x50b7d  ldloc.2
0x50b7e  ldarg.1
0x50b7f  ldstr    aEntityid// "entityid"
0x50b84  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x50b89  unbox.any [mscorlib]System.Guid
0x50b8e  ldloc.s  7
0x50b90  ldstr    aEntityid// "entityid"
0x50b95  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x50b9a  unbox.any [mscorlib]System.Guid
0x50b9f  ldarg.s  4
0x50ba1  callvirt instance bool Microsoft.Crm.Metadata.RelationshipService::LoopDetected(valuetype [mscorlib]System.Guid sourceEntityId, valuetype [mscorlib]System.Guid destinationEntityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x50ba6  brfalse.s loc_50BB8
0x50ba8  ldstr    aCannotCreateRe_0// "Cannot create relationships that result"...
0x50bad  ldc.i4   0x80047004
0x50bb2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x50bb7  throw
0x50bb8  ldloca.s 8
0x50bba  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption>
0x50bc0  ldarg.s  4
0x50bc2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x50bc7  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInSystemConvertedSolutionUpgradeContext(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x50bcc  brfalse.s loc_50BE1
0x50bce  ldloc.s  4
0x50bd0  ldarg.s  4
0x50bd2  call     bool Microsoft.Crm.Metadata.RelationshipService::IsCustomActivity(string entityName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x50bd7  brfalse.s loc_50BE1
0x50bd9  ldloca.s 8
0x50bdb  ldc.i4.1
0x50bdc  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption>::.ctor(var<u1>)
0x50be1  ldloc.s  4
0x50be3  ldstr    aRegardingobjec// "regardingobjectid"
0x50be8  ldstr    aRegardingobjec_0// "regardingobjecttypecode"
0x50bed  ldarg.1
0x50bee  ldarg.2
0x50bef  ldarg.3
0x50bf0  ldloc.s  6
0x50bf2  ldloc.s  5
0x50bf4  ldc.i4.0
0x50bf5  ldarg.s  4
0x50bf7  ldloc.s  8
0x50bf9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag Microsoft.Crm.Metadata.RelationshipService::CreateRelationship(string referencingEntityName, string referencingAttributeName, string referencingExtraAttributeName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity referencedEntityData, valuetype [mscorlib]System.Guid primaryKeyId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipTypes relationType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity referencingEntityRoleUIData, bool isRelationshipCustom, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption> specifiedModifierOption)
0x50bfe  pop
0x50bff  ldloca.s 3
0x50c01  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x50c06  brtrue   loc_50A93
0x50c0b  leave.s  loc_50C1B
0x50c0d  ldloca.s 3
0x50c0f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x50c15  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x50c1a  endfinally
0x50c1b  ret
```
