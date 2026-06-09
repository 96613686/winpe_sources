# Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetRelationshipUpdateInfo

- ea: `0xa7f0`
- end: `0xa9ff`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetRelationshipUpdateInfo`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xa600`

## callees

- `0x190`
- `0x1a0`
- `0x200`
- `0x220`
- `0x270`
- `0x330`
- `0x360`
- `0xa7f0`
- `0xaa00`
- `0xaac0`

## pseudocode

```c

```

## disassembly

```asm
0xa7f0  ldarg.0
0xa7f1  ldstr    aRelationshipid// "relationshipid"
0xa7f6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0xa7fb  stloc.0
0xa7fc  ldarg.1
0xa7fd  ldloc.0
0xa7fe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetRelationship(valuetype [mscorlib]System.Guid)
0xa803  stloc.1
0xa804  ldarg.1
0xa805  ldarg.0
0xa806  ldstr    aEntityrelation// "entityrelationshipid"
0xa80b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0xa810  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntityRelationship(valuetype [mscorlib]System.Guid)
0xa815  stloc.2
0xa816  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa81b  stloc.3
0xa81c  ldloc.2
0xa81d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRoleCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_EntityRelationshipRoles()
0xa822  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::GetEnumerator()
0xa827  stloc.s  6
0xa829  br.s     loc_A848
0xa82b  ldloc.s  6
0xa82d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::get_Current()
0xa832  stloc.s  7
0xa834  ldloc.s  7
0xa836  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_RelationshipRoleType()
0xa83b  ldc.i4.1
0xa83c  bne.un.s loc_A848
0xa83e  ldloc.s  7
0xa840  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_EntityRelationshipRoleId()
0xa845  stloc.3
0xa846  leave.s  loc_A85F
0xa848  ldloc.s  6
0xa84a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa84f  brtrue.s loc_A82B
0xa851  leave.s  loc_A85F
0xa853  ldloc.s  6
0xa855  brfalse.s loc_A85E
0xa857  ldloc.s  6
0xa859  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa85e  endfinally
0xa85f  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::.ctor()
0xa864  stloc.s  4
0xa866  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa86b  stloc.s  5
0xa86d  ldloc.1
0xa86e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0xa873  call     bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeService::IsCustomizableAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0xa878  brfalse  loc_A94D
0xa87d  ldarg.0
0xa87e  ldstr    aReferencedinst// "referencedinstancename"
0xa883  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xa888  brfalse.s loc_A8B2
0xa88a  ldloc.s  4
0xa88c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::get_PrimaryEntityInstanceName()
0xa891  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xa896  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xa89b  ldarg.0
0xa89c  ldstr    aReferencedinst// "referencedinstancename"
0xa8a1  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xa8a6  ldloc.s  5
0xa8a8  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa8ad  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0xa8b2  ldarg.0
0xa8b3  ldstr    aReqlevel// "reqlevel"
0xa8b8  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xa8bd  brfalse.s loc_A8E7
0xa8bf  ldloc.s  4
0xa8c1  ldarg.0
0xa8c2  ldstr    aReqlevel// "reqlevel"
0xa8c7  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel
0xa8cc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa8d1  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xa8d6  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel
0xa8db  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>::.ctor(var<u1>)
0xa8e0  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_RelationshipAttributeRequiredLevel(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>)
0xa8e5  br.s     loc_A906
0xa8e7  ldloc.1
0xa8e8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0xa8ed  brfalse.s loc_A906
0xa8ef  ldloc.s  4
0xa8f1  ldloc.1
0xa8f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0xa8f7  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0xa8fc  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>::.ctor(var<u1>)
0xa901  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_RelationshipAttributeRequiredLevel(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>)
0xa906  ldloc.s  4
0xa908  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::get_Description()
0xa90d  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xa912  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xa917  ldarg.0
0xa918  ldstr    aDescription// "description"
0xa91d  ldsfld   string [mscorlib]System.String::Empty
0xa922  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0xa927  ldloc.s  5
0xa929  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa92e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0xa933  ldloc.1
0xa934  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0xa939  brfalse.s loc_A94D
0xa93b  ldloc.s  4
0xa93d  ldloc.1
0xa93e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0xa943  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsAuditEnabled()
0xa948  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_RelationshipAttributeIsAuditEnabled(bool)
0xa94d  ldarg.0
0xa94e  ldloc.s  4
0xa950  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetCascadingInfo(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo relationshipInfo)
0xa955  ldloc.s  4
0xa957  ldloc.s  5
0xa959  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa95e  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_ReferencingEntityRoleInfo(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo)
0xa963  ldloc.s  4
0xa965  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::get_ReferencingEntityRoleInfo()
0xa96a  ldloc.3
0xa96b  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::set_EntityRelationshipRoleId(valuetype [mscorlib]System.Guid)
0xa970  ldarg.0
0xa971  ldstr    aAssociatedmenu// "associatedmenu"
0xa976  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0xa97b  ldloc.s  4
0xa97d  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::get_ReferencingEntityRoleInfo()
0xa982  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetAssociatedMenuInfo(class Microsoft.Crm.Application.WebServices.ParameterBag menuBag, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo roleInfo)
0xa987  ldloc.2
0xa988  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_IsCustomRelationship()
0xa98d  brfalse.s loc_A9B1
0xa98f  ldarg.0
0xa990  ldstr    aIsvalidforadva// "isvalidforadvancedfind"
0xa995  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xa99a  brfalse.s loc_A9B1
0xa99c  ldloc.s  4
0xa99e  ldarg.0
0xa99f  ldstr    aIsvalidforadva// "isvalidforadvancedfind"
0xa9a4  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0xa9a9  ldc.i4.0
0xa9aa  cgt.un
0xa9ac  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_RelationshipValidForAdvancedFind(bool)
0xa9b1  ldloc.s  4
0xa9b3  ldloc.2
0xa9b4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_CanChangeHierarchicalSettings()
0xa9b9  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0xa9be  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CanChangeHierarchicalSettings(valuetype [mscorlib]System.Nullable`1<bool>)
0xa9c3  ldloc.s  4
0xa9c5  ldloc.2
0xa9c6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_IsCustomizable()
0xa9cb  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0xa9d0  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_IsCustomizable(valuetype [mscorlib]System.Nullable`1<bool>)
0xa9d5  ldarg.0
0xa9d6  ldstr    aIshierarchical_0// "ishierarchical"
0xa9db  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xa9e0  brfalse.s loc_A9FC
0xa9e2  ldloc.s  4
0xa9e4  ldarg.0
0xa9e5  ldstr    aIshierarchical_0// "ishierarchical"
0xa9ea  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0xa9ef  ldc.i4.0
0xa9f0  cgt.un
0xa9f2  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0xa9f7  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_IsHierarchical(valuetype [mscorlib]System.Nullable`1<bool>)
0xa9fc  ldloc.s  4
0xa9fe  ret
```
