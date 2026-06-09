# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::SetRelationshipAsHierarchical

- ea: `0xb960`
- end: `0xbab4`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::SetRelationshipAsHierarchical`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xb960`

## pseudocode

```c

```

## disassembly

```asm
0xb960  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb965  stloc.0
0xb966  ldloc.0
0xb967  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb96c  dup
0xb96d  ldarg.1
0xb96e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb973  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntityRelationship(valuetype [mscorlib]System.Guid)
0xb978  stloc.1
0xb979  ldloc.1
0xb97a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_Relationships()
0xb97f  ldc.i4.0
0xb980  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataArrayList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship>::get_Item(!!T0)
0xb985  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_Id()
0xb98a  stloc.2
0xb98b  ldloc.2
0xb98c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetRelationship(valuetype [mscorlib]System.Guid)
0xb991  stloc.3
0xb992  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb997  stloc.s  4
0xb999  ldloc.1
0xb99a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRoleCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_EntityRelationshipRoles()
0xb99f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::GetEnumerator()
0xb9a4  stloc.s  6
0xb9a6  br.s     loc_B9C6
0xb9a8  ldloc.s  6
0xb9aa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::get_Current()
0xb9af  stloc.s  7
0xb9b1  ldloc.s  7
0xb9b3  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_RelationshipRoleType()
0xb9b8  ldc.i4.1
0xb9b9  bne.un.s loc_B9C6
0xb9bb  ldloc.s  7
0xb9bd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_EntityRelationshipRoleId()
0xb9c2  stloc.s  4
0xb9c4  br.s     loc_B9CF
0xb9c6  ldloc.s  6
0xb9c8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb9cd  brtrue.s loc_B9A8
0xb9cf  leave.s  loc_B9DD
0xb9d1  ldloc.s  6
0xb9d3  brfalse.s loc_B9DC
0xb9d5  ldloc.s  6
0xb9d7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb9dc  endfinally
0xb9dd  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::.ctor()
0xb9e2  stloc.s  5
0xb9e4  ldloc.s  5
0xb9e6  ldc.i4.1
0xb9e7  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0xb9ec  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_IsCustomizable(valuetype [mscorlib]System.Nullable`1<bool>)
0xb9f1  ldloc.3
0xb9f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0xb9f7  call     bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeService::IsCustomizableAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0xb9fc  brfalse.s loc_BA1D
0xb9fe  ldloc.3
0xb9ff  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0xba04  brfalse.s loc_BA1D
0xba06  ldloc.s  5
0xba08  ldloc.3
0xba09  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0xba0e  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0xba13  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>::.ctor(var<u1>)
0xba18  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_RelationshipAttributeRequiredLevel(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>)
0xba1d  ldloc.s  5
0xba1f  ldloc.0
0xba20  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xba25  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_ReferencingEntityRoleInfo(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo)
0xba2a  ldloc.s  5
0xba2c  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::get_ReferencingEntityRoleInfo()
0xba31  ldloc.s  4
0xba33  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::set_EntityRelationshipRoleId(valuetype [mscorlib]System.Guid)
0xba38  ldloc.s  5
0xba3a  ldloc.1
0xba3b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_CanChangeHierarchicalSettings()
0xba40  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0xba45  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CanChangeHierarchicalSettings(valuetype [mscorlib]System.Nullable`1<bool>)
0xba4a  ldloc.s  5
0xba4c  ldloc.1
0xba4d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_IsCustomizable()
0xba52  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0xba57  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_IsCustomizable(valuetype [mscorlib]System.Nullable`1<bool>)
0xba5c  ldloc.s  5
0xba5e  ldc.i4.1
0xba5f  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0xba64  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_IsHierarchical(valuetype [mscorlib]System.Nullable`1<bool>)
0xba69  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipService::.ctor()
0xba6e  ldarg.1
0xba6f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xba74  ldloc.s  5
0xba76  ldc.i4.1
0xba77  ldarg.0
0xba78  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xba7d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xba82  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xba87  brtrue.s loc_BA91
0xba89  ldarg.0
0xba8a  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xba8f  br.s     loc_BA96
0xba91  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0xba96  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipService::Update(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.IRelationshipUpdateInfo, bool, valuetype [mscorlib]System.Guid)
0xba9b  pop
0xba9c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbaa1  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbaa6  leave.s  loc_BAB3
0xbaa8  stloc.s  8
0xbaaa  ldarg.0
0xbaab  ldloc.s  8
0xbaad  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xbab2  throw
0xbab3  ret
```
