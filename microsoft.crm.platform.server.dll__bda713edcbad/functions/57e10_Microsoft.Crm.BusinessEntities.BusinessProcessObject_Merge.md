# Microsoft.Crm.BusinessEntities.BusinessProcessObject::Merge

- ea: `0x57e10`
- end: `0x580fa`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::Merge`
- size: `746`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `broker_com_uri`

## callees

- `0x18530`
- `0x18800`
- `0x56d40`
- `0x56f60`
- `0x57630`
- `0x57da0`
- `0x57dc0`
- `0x57dd0`
- `0x57de0`
- `0x57e10`
- `0x58100`
- `0x581f0`
- `0x58210`
- `0x58300`
- `0x58440`
- `0x584b0`
- `0x586d0`
- `0x587c0`
- `0x5f010`
- `0x5f340`
- `0x61130`
- `0x61310`
- `0x61330`
- `0x61340`
- `0x66b10`
- `0x67cf0`
- `0x68b40`
- `0x6e140`
- `0x6e390`
- `0x77890`
- `0x77cd0`

## string_xrefs

- `0x57fb3`: `GrantFullAccessForMergeToMasterOwner`
- `0x58034`: `GrantSharedAccessForMergeToSubordinateOwner`

## pseudocode

```c

```

## disassembly

```asm
0x57e10  ldarg.0
0x57e11  ldarg.s  5
0x57e13  call     instance class [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.IMergeOperationParameters Microsoft.Crm.BusinessEntities.BusinessProcessObject::GetMergeOperationParameters(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57e18  stloc.0
0x57e19  ldarg.s  5
0x57e1b  ldstr    aMergeoperation// "MergeOperationParameters are not specif"...
0x57e20  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x57e25  ldarg.1
0x57e26  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x57e2b  stloc.1
0x57e2c  ldarg.2
0x57e2d  ldarg.1
0x57e2e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x57e33  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x57e38  ldarg.s  5
0x57e3a  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x57e3f  stloc.2
0x57e40  ldarg.3
0x57e41  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x57e46  stloc.3
0x57e47  ldarg.s  5
0x57e49  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x57e4e  pop
0x57e4f  ldarg.s  5
0x57e51  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x57e56  pop
0x57e57  ldarg.3
0x57e58  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x57e5d  call     class Microsoft.Crm.BusinessEntities.SecurityTraits Microsoft.Crm.BusinessEntities.SecurityTraitsFactory::Get(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0x57e62  stloc.s  4
0x57e64  ldloc.1
0x57e65  ldarg.2
0x57e66  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x57e6b  brfalse.s loc_57E7E
0x57e6d  ldc.i4   0x80045305
0x57e72  ldc.i4.0
0x57e73  newarr   [mscorlib]System.Object
0x57e78  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x57e7d  throw
0x57e7e  ldarg.0
0x57e7f  ldloc.3
0x57e80  ldarg.s  5
0x57e82  call     instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.BusinessEntities.BusinessProcessObject::GetMasterEntityColumnSet(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57e87  stloc.s  5
0x57e89  ldarg.0
0x57e8a  ldarg.3
0x57e8b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x57e90  ldarg.s  5
0x57e92  call     instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeCreateColumnSetExpression(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57e97  stloc.s  6
0x57e99  ldarg.1
0x57e9a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x57e9f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x57ea4  ldarg.s  5
0x57ea6  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x57eab  stloc.s  7
0x57ead  ldloc.s  7
0x57eaf  ldloc.s  5
0x57eb1  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class Microsoft.Crm.Query.ColumnSetExpression value)
0x57eb6  ldloc.2
0x57eb7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x57ebc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x57ec1  ldarg.s  5
0x57ec3  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x57ec8  stloc.s  8
0x57eca  ldloc.s  8
0x57ecc  ldloc.s  6
0x57ece  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class Microsoft.Crm.Query.ColumnSetExpression value)
0x57ed3  ldarg.0
0x57ed4  ldarg.1
0x57ed5  ldloc.s  7
0x57ed7  ldarg.s  5
0x57ed9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class Microsoft.Crm.Query.EntityExpression entityExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57ede  stloc.s  9
0x57ee0  ldarg.0
0x57ee1  ldloc.2
0x57ee2  ldloc.s  8
0x57ee4  ldarg.s  5
0x57ee6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class Microsoft.Crm.Query.EntityExpression entityExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57eeb  stloc.s  0xA
0x57eed  ldarg.0
0x57eee  ldloc.s  9
0x57ef0  ldloc.s  0xA
0x57ef2  ldloc.0
0x57ef3  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeCheckActiveState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity masterEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity subordinateEntity, class [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.IMergeOperationParameters mergeOperationParameters)
0x57ef8  ldarg.0
0x57ef9  ldarg.s  5
0x57efb  ldarg.1
0x57efc  ldloc.2
0x57efd  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeBasicSecurityCheck(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker masterMoniker, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker subordinateMoniker)
0x57f02  ldarg.1
0x57f03  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x57f08  ldarg.s  5
0x57f0a  call     void Microsoft.Crm.BusinessEntities.ExternalPartyExtension::CheckIfInvalidRequest(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57f0f  ldarg.0
0x57f10  ldloc.s  9
0x57f12  ldloc.s  0xA
0x57f14  ldarg.s  5
0x57f16  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeCheckForParents(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity masterEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity subordinateEntity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57f1b  ldarg.0
0x57f1c  ldloc.s  9
0x57f1e  ldloc.s  0xA
0x57f20  ldarg.s  5
0x57f22  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeCheckForMaxChildren(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity masterEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity subordinateEntity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57f27  ldarg.0
0x57f28  ldloc.1
0x57f29  ldarg.2
0x57f2a  ldarg.s  5
0x57f2c  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeCheckEntityLoop(valuetype [mscorlib]System.Guid parentId, valuetype [mscorlib]System.Guid childId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57f31  ldarg.s  4
0x57f33  brfalse.s loc_57F3F
0x57f35  ldarg.0
0x57f36  ldloc.s  9
0x57f38  ldloc.s  0xA
0x57f3a  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeCheckParenting(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity masterEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity subordinateEntity)
0x57f3f  ldloc.0
0x57f40  callvirt instance bool [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.IMergeOperationParameters::get_UseSystemContextForMerge()
0x57f45  stloc.s  0xB
0x57f47  ldloc.1
0x57f48  ldarg.2
0x57f49  ldarg.1
0x57f4a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x57f4f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x57f54  ldloc.s  0xB
0x57f56  ldarg.s  5
0x57f58  call     void Microsoft.Crm.BusinessEntities.CascadeEngine::CascadeMerge(valuetype [mscorlib]System.Guid masterId, valuetype [mscorlib]System.Guid subId, int32 parentTypeCode, bool useSystemContext, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57f5d  ldarg.0
0x57f5e  ldloc.s  9
0x57f60  ldloc.1
0x57f61  ldarg.2
0x57f62  ldarg.s  5
0x57f64  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeUpdateActivityParty(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity masterEntity, valuetype [mscorlib]System.Guid masterEntityId, valuetype [mscorlib]System.Guid subordinateEntityId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57f69  ldloc.s  9
0x57f6b  ldstr    aOwneridtype// "owneridtype"
0x57f70  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x57f75  unbox.any [mscorlib]System.Int32
0x57f7a  ldloc.s  9
0x57f7c  ldstr    aOwnerid// "ownerid"
0x57f81  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x57f86  unbox.any [mscorlib]System.Guid
0x57f8b  newobj   instance void Microsoft.Crm.BusinessEntities.SecurityPrincipal::.ctor(int32 type, valuetype [mscorlib]System.Guid principalId)
0x57f90  stloc.s  0xC
0x57f92  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x57f97  ldarg.s  5
0x57f99  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x57f9e  ldarg.s  5
0x57fa0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x57fa5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x57faa  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x57faf  stloc.s  0xD
0x57fb1  ldloc.s  0xD
0x57fb3  ldstr    aGrantfullacces// "GrantFullAccessForMergeToMasterOwner"
0x57fb8  ldc.i4.1
0x57fb9  box      [mscorlib]System.Boolean
0x57fbe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x57fc3  unbox.any [mscorlib]System.Boolean
0x57fc8  brfalse.s loc_58009
0x57fca  newobj   instance void Microsoft.Crm.BusinessEntities.PrincipalAccess::.ctor()
0x57fcf  stloc.s  0xF
0x57fd1  ldloc.s  0xF
0x57fd3  ldloc.s  0xC
0x57fd5  callvirt instance void Microsoft.Crm.BusinessEntities.PrincipalAccess::set_Principal(class Microsoft.Crm.BusinessEntities.SecurityPrincipal value)
0x57fda  ldloc.s  0xF
0x57fdc  ldc.i4   0xD0037
0x57fe1  callvirt instance void Microsoft.Crm.BusinessEntities.PrincipalAccess::set_AccessMask(int32 value)
0x57fe6  ldarg.s  5
0x57fe8  ldc.i4.1
0x57fe9  newobj   instance void Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class Microsoft.Crm.BusinessEntities.ExecutionContext context, bool switchAuditingInfo)
0x57fee  stloc.s  0x10
0x57ff0  ldarg.0
0x57ff1  ldarg.1
0x57ff2  ldloc.s  0xF
0x57ff4  ldarg.s  5
0x57ff6  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::ModifyAccess(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class Microsoft.Crm.BusinessEntities.PrincipalAccess grantee, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57ffb  leave.s  loc_58009
0x57ffd  ldloc.s  0x10
0x57fff  brfalse.s loc_58008
0x58001  ldloc.s  0x10
0x58003  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x58008  endfinally
0x58009  ldloc.s  0xA
0x5800b  ldstr    aOwneridtype// "owneridtype"
0x58010  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x58015  unbox.any [mscorlib]System.Int32
0x5801a  ldloc.s  0xA
0x5801c  ldstr    aOwnerid// "ownerid"
0x58021  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x58026  unbox.any [mscorlib]System.Guid
0x5802b  newobj   instance void Microsoft.Crm.BusinessEntities.SecurityPrincipal::.ctor(int32 type, valuetype [mscorlib]System.Guid principalId)
0x58030  stloc.s  0xE
0x58032  ldloc.s  0xD
0x58034  ldstr    aGrantsharedacc// "GrantSharedAccessForMergeToSubordinateO"...
0x58039  ldc.i4.1
0x5803a  box      [mscorlib]System.Boolean
0x5803f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x58044  unbox.any [mscorlib]System.Boolean
0x58049  brfalse.s loc_58082
0x5804b  ldloc.1
0x5804c  ldarg.1
0x5804d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x58052  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x58057  ldarg.2
0x58058  ldloc.2
0x58059  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x5805e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x58063  ldloc.s  0xC
0x58065  ldloc.s  0xE
0x58067  ldarg.s  5
0x58069  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantInheritedAccessForMerge(valuetype [mscorlib]System.Guid referencingId, int32 referencingOTC, valuetype [mscorlib]System.Guid referencedId, int32 referencedOTC, class Microsoft.Crm.BusinessEntities.SecurityPrincipal referencingOwner, class Microsoft.Crm.BusinessEntities.SecurityPrincipal referencedOwner, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5806e  ldarg.2
0x5806f  ldloc.1
0x58070  ldarg.1
0x58071  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x58076  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x5807b  ldarg.s  5
0x5807d  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::UpdateSharedAccess(valuetype [mscorlib]System.Guid subordinateObjectId, valuetype [mscorlib]System.Guid masterObjectId, int32 masterOTC, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x58082  ldloc.s  4
0x58084  ldloc.s  9
0x58086  newobj   instance void Microsoft.Crm.BusinessEntities.SecurityAttributes::.ctor(class Microsoft.Crm.BusinessEntities.SecurityTraits traits, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity)
0x5808b  ldarg.s  5
0x5808d  call     void Microsoft.Crm.BusinessEntities.CascadeEngine::Reparent(class Microsoft.Crm.BusinessEntities.SecurityAttributes securityAttributes, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x58092  ldarg.0
0x58093  ldloc.2
0x58094  ldarg.s  5
0x58096  ldloc.0
0x58097  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeDeactivate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.IMergeOperationParameters mergeOperationParameters)
0x5809c  ldarg.0
0x5809d  ldloc.2
0x5809e  ldloc.1
0x5809f  ldarg.s  5
0x580a1  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeSetMergeFields(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker subordinateMoniker, valuetype [mscorlib]System.Guid masterId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x580a6  ldloc.3
0x580a7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x580ac  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Count()
0x580b1  ldc.i4.0
0x580b2  ble.s    loc_580F9
0x580b4  ldloc.3
0x580b5  ldloc.s  9
0x580b7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::CreateDifferenceEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x580bc  stloc.3
0x580bd  ldloc.3
0x580be  ldstr    aModifiedby// "modifiedby"
0x580c3  ldarg.s  5
0x580c5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x580ca  box      [mscorlib]System.Guid
0x580cf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x580d4  ldloc.3
0x580d5  ldloc.3
0x580d6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x580db  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x580e0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x580e5  ldloc.1
0x580e6  box      [mscorlib]System.Guid
0x580eb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x580f0  ldarg.0
0x580f1  ldloc.3
0x580f2  ldarg.s  5
0x580f4  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x580f9  ret
```
