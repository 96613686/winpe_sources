# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::GetOneToManyRelationships

- ea: `0x690`
- end: `0x861`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::GetOneToManyRelationships`
- size: `465`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x690`
- `0x890`
- `0x8d0`

## pseudocode

```c

```

## disassembly

```asm
0x690  ldarg.0
0x691  ldarg.1
0x692  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.IRuleAdapter Microsoft.Crm.Application.WebServices.BusinessRulesWebService::CreateRuleAdapter(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.EditorPageType editorPageType)
0x697  stloc.0
0x698  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x69d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6a2  ldarg.2
0x6a3  ldc.i4.1
0x6a4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x6a9  stloc.1
0x6aa  ldloc.1
0x6ab  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x6b0  brtrue.s loc_6D5
0x6b2  ldloc.1
0x6b3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x6b8  ldstr    aActivitypointe// "activitypointer"
0x6bd  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x6c2  brfalse.s loc_6D5
0x6c4  ldarg.0
0x6c5  ldstr    aOnlyActivities// "Only activities are supported"
0x6ca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x6cf  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x6d4  throw
0x6d5  ldloc.1
0x6d6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRoleCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencedEntityRoles()
0x6db  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::GetEnumerator()
0x6e0  stloc.2
0x6e1  br       loc_845
0x6e6  ldloc.2
0x6e7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::get_Current()
0x6ec  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ReferencedEntityRelationshipRole
0x6f1  stloc.3
0x6f2  ldloc.3
0x6f3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ReferencedEntityRelationshipRole::get_OneToManyRelationship()
0x6f8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship::get_Relationship()
0x6fd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0x702  stloc.s  4
0x704  ldloc.s  4
0x706  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x70b  ldstr    aActivityparty// "activityparty"
0x710  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x715  brtrue   loc_845
0x71a  ldloc.3
0x71b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ReferencedEntityRelationshipRole::get_OneToManyRelationship()
0x720  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship::get_Relationship()
0x725  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x72a  stloc.s  5
0x72c  ldloc.0
0x72d  ldloc.s  4
0x72f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x734  ldloc.s  5
0x736  callvirt instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityFieldMetadataJsonWrapper [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.IRuleAdapter::BuildEntityFieldMetadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x73b  stloc.s  6
0x73d  ldloc.s  4
0x73f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x744  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0x749  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x74e  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x753  stloc.s  7
0x755  ldarg.0
0x756  ldarg.1
0x757  ldloc.s  4
0x759  ldloc.0
0x75a  call     instance class [System]System.Collections.Generic.SortedList`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityFieldMetadataJsonWrapper> Microsoft.Crm.Application.WebServices.BusinessRulesWebService::BuildEntityFieldsInfo(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.EditorPageType editorPageType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.IRuleAdapter ruleAdapter)
0x75f  stloc.s  8
0x761  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper::.ctor()
0x766  dup
0x767  ldloc.s  4
0x769  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x76e  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper::EntityLogicalName
0x773  dup
0x774  ldloc.s  4
0x776  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x77b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0x780  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper::EntityTypeCode
0x785  dup
0x786  ldloc.s  7
0x788  ldc.i4.2
0x789  ldnull
0x78a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x78f  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper::PluralName
0x794  dup
0x795  ldloc.s  4
0x797  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x79c  brtrue.s loc_7A5
0x79e  ldstr    asc_A26A// ""
0x7a3  br.s     loc_7B1
0x7a5  ldloc.s  4
0x7a7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x7ac  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x7b1  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper::PrimaryAttributeLogicName
0x7b6  dup
0x7b7  ldloc.s  4
0x7b9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x7be  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x7c3  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x7c8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7cd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7d2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x7d7  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper::DisplayName
0x7dc  dup
0x7dd  ldloc.s  8
0x7df  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [System]System.Collections.Generic.SortedList`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityFieldMetadataJsonWrapper>::get_Values()
0x7e4  call     T0x2B000006
0x7e9  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityFieldMetadataJsonWrapper[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper::Fields
0x7ee  stloc.s  9
0x7f0  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.RelationshipEntityMetadataJsonWrapper::.ctor()
0x7f5  dup
0x7f6  ldloc.3
0x7f7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ReferencedEntityRelationshipRole::get_OneToManyRelationship()
0x7fc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship::get_Relationship()
0x801  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_Name()
0x806  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.RelationshipEntityMetadataJsonWrapper::RelationshipName
0x80b  dup
0x80c  ldloc.s  6
0x80e  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityFieldMetadataJsonWrapper [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.RelationshipEntityMetadataJsonWrapper::RelationshipAttribute
0x813  dup
0x814  ldloc.s  9
0x816  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.RelationshipEntityMetadataJsonWrapper::RelationshipEntity
0x81b  stloc.s  0xA
0x81d  ldc.i4.1
0x81e  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.RelationshipEntityMetadataJsonWrapper
0x823  dup
0x824  ldc.i4.0
0x825  ldloc.s  0xA
0x827  stelem.ref
0x828  stloc.s  0xB
0x82a  ldstr    aFor// "for(;;);"
0x82f  ldloc.s  0xB
0x831  ldloc.0
0x832  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.IRuleAdapter::BuildKnownTypes()
0x837  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>)
0x83c  call     string [mscorlib]System.String::Concat(string, string)
0x841  stloc.s  0xC
0x843  leave.s  loc_85E
0x845  ldloc.2
0x846  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x84b  brtrue   loc_6E6
0x850  leave.s  loc_85C
0x852  ldloc.2
0x853  brfalse.s loc_85B
0x855  ldloc.2
0x856  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x85b  endfinally
0x85c  ldnull
0x85d  ret
0x85e  ldloc.s  0xC
0x860  ret
```
