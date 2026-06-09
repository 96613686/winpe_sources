# Microsoft.Crm.Service.ObjectModel.KbArticleService::UnPublish

- ea: `0x7170`
- end: `0x733b`
- name: `Microsoft.Crm.Service.ObjectModel.KbArticleService::UnPublish`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6b10`

## callees

- `0x61a0`
- `0x7170`

## pseudocode

```c

```

## disassembly

```asm
0x7170  ldarg.1
0x7171  ldstr    aStatecode// "statecode"
0x7176  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x717b  unbox.any [mscorlib]System.Int32
0x7180  ldc.i4.3
0x7181  beq.s    loc_71DC
0x7183  ldarg.1
0x7184  ldstr    aStatecode// "statecode"
0x7189  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x718e  unbox.any [mscorlib]System.Int32
0x7193  ldc.i4.1
0x7194  bne.un.s loc_71A7
0x7196  ldc.i4   0x80048DFC
0x719b  ldc.i4.0
0x719c  newarr   [mscorlib]System.Object
0x71a1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x71a6  throw
0x71a7  ldarg.1
0x71a8  ldstr    aStatecode// "statecode"
0x71ad  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x71b2  unbox.any [mscorlib]System.Int32
0x71b7  ldc.i4.2
0x71b8  bne.un.s loc_71CB
0x71ba  ldc.i4   0x80048DFE
0x71bf  ldc.i4.0
0x71c0  newarr   [mscorlib]System.Object
0x71c5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x71ca  throw
0x71cb  ldc.i4   0x800404FC
0x71d0  ldc.i4.0
0x71d1  newarr   [mscorlib]System.Object
0x71d6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x71db  throw
0x71dc  ldarg.2
0x71dd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x71e2  ldarg.2
0x71e3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x71e8  ldarg.0
0x71e9  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x71ee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x71f3  ldc.i4.2
0x71f4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType)
0x71f9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x71fe  ldarg.2
0x71ff  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x7204  ldarg.2
0x7205  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x720a  ldarg.2
0x720b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7210  ldarg.0
0x7211  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x7216  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x721b  ldstr    aPrvpublisharti// "prvPublishArticle"
0x7220  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(string)
0x7225  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x722a  ldarg.2
0x722b  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x7230  ldarg.2
0x7231  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x7236  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.DocumentIndex::.ctor(valuetype [mscorlib]System.Guid)
0x723b  stloc.0
0x723c  newobj   instance void Microsoft.Crm.Service.ObjectModel.DocumentIndexService::.ctor()
0x7241  ldloc.0
0x7242  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x7247  ldarg.2
0x7248  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x724d  stloc.1
0x724e  ldloc.1
0x724f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x7254  ldloc.1
0x7255  ldstr    aIspublished// "ispublished"
0x725a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x725f  ldloc.0
0x7260  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x7265  ldarg.2
0x7266  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x726b  ldloc.1
0x726c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0x7271  ldloc.0
0x7272  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x7277  ldarg.2
0x7278  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x727d  stloc.2
0x727e  ldloc.2
0x727f  ldstr    aDocumentid// "documentid"
0x7284  ldc.i4.0
0x7285  ldarg.1
0x7286  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x728b  unbox.any [mscorlib]System.Guid
0x7290  box      [mscorlib]System.Guid
0x7295  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x729a  pop
0x729b  dup
0x729c  ldloc.2
0x729d  ldloc.1
0x729e  ldarg.2
0x729f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x72a4  dup
0x72a5  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x72aa  ldc.i4.1
0x72ab  beq.s    loc_72C2
0x72ad  ldc.i4   0x80042C05
0x72b2  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x72b7  ldc.i4   0x80042C05
0x72bc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x72c1  throw
0x72c2  ldc.i4.0
0x72c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x72c8  isinst   [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.DocumentIndex
0x72cd  stloc.0
0x72ce  ldloc.0
0x72cf  ldstr    aIspublished// "ispublished"
0x72d4  ldc.i4.0
0x72d5  box      [mscorlib]System.Boolean
0x72da  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x72df  ldloc.0
0x72e0  ldarg.2
0x72e1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x72e6  ldarg.0
0x72e7  ldarg.1
0x72e8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x72ed  unbox.any [mscorlib]System.Guid
0x72f2  ldstr    aKbarticle// "KbArticle"
0x72f7  ldarg.2
0x72f8  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x72fd  ldc.i4.2
0x72fe  ldc.i4.m1
0x72ff  ldarg.2
0x7300  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x7305  ldarg.2
0x7306  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x730b  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KbArticle::.ctor(valuetype [mscorlib]System.Guid)
0x7310  stloc.3
0x7311  ldloc.3
0x7312  ldstr    aKbarticleid// "kbarticleid"
0x7317  ldarg.1
0x7318  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x731d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7322  ldloc.3
0x7323  ldstr    aContent// "content"
0x7328  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x732d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7332  ldarg.0
0x7333  ldloc.3
0x7334  ldarg.2
0x7335  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x733a  ret
```
