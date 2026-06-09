# Microsoft.Crm.Metadata.DynamicMetadataContainer::GetDeepSize

- ea: `0x59450`
- end: `0x59782`
- name: `Microsoft.Crm.Metadata.DynamicMetadataContainer::GetDeepSize`
- size: `818`
- prototype: ``
- caller_count: `1`
- callee_count: `43`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x59410`

## callees

- `0x54ae0`
- `0x54b00`
- `0x54b20`
- `0x54b40`
- `0x54b60`
- `0x54b80`
- `0x54ba0`
- `0x54bc0`
- `0x54be0`
- `0x54c00`
- `0x54c20`
- `0x54c40`
- `0x54c60`
- `0x54c80`
- `0x54ca0`
- `0x54cc0`
- `0x54ce0`
- `0x54d00`
- `0x54d20`
- `0x54d40`
- `0x54d60`
- `0x54d80`
- `0x54da0`
- `0x54dc0`
- `0x54de0`
- `0x54e00`
- `0x54e20`
- `0x54e40`
- `0x54e60`
- `0x54e80`
- `0x54ea0`
- `0x54ec0`
- `0x54ee0`
- `0x54f00`
- `0x54f20`
- `0x54f40`
- `0x54f60`
- `0x54fa0`
- `0x54fd0`
- `0x59450`
- `0x5e1e0`
- `0x5e4f0`
- `0x5ed80`

## string_xrefs

- `0x594f4`: `ContainerPrivilegeOTCs`
- `0x59506`: `ContainerRoleTemplatePrivileges`
- `0x59614`: `ContainerPrivileges`

## pseudocode

```c

```

## disassembly

```asm
0x59450  ldarg.0
0x59451  ldarg.1
0x59452  ldstr    aContainermanag// "ContainerManagedProperties"
0x59457  ldarg.0
0x59458  call     instance class Microsoft.Crm.Metadata.ManagedPropertyByIdDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_ManagedProperties()
0x5945d  call     T0x2B000086
0x59462  ldarg.0
0x59463  ldarg.1
0x59464  ldstr    aContaineroptio// "ContainerOptionSets"
0x59469  ldarg.0
0x5946a  call     instance class Microsoft.Crm.Metadata.OptionSetByIdDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_OptionSets()
0x5946f  call     T0x2B000087
0x59474  ldarg.0
0x59475  ldarg.1
0x59476  ldstr    aContainerentit// "ContainerEntities"
0x5947b  ldarg.0
0x5947c  call     instance class Microsoft.Crm.Metadata.EntityMetadataDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_Entities()
0x59481  call     T0x2B000088
0x59486  ldarg.0
0x59487  ldarg.1
0x59488  ldstr    aContainerattri// "ContainerAttributes"
0x5948d  ldarg.0
0x5948e  call     instance class Microsoft.Crm.Metadata.AttributeMetadataDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_Attributes()
0x59493  call     T0x2B000089
0x59498  ldarg.0
0x59499  ldarg.1
0x5949a  ldstr    aContainerrelat// "ContainerRelationships"
0x5949f  ldarg.0
0x594a0  call     instance class Microsoft.Crm.Metadata.RelationshipHashtable Microsoft.Crm.Metadata.DynamicMetadataContainer::get_Relationships()
0x594a5  call     T0x2B00008A
0x594aa  ldarg.0
0x594ab  ldarg.1
0x594ac  ldstr    aContainerrelat_0// "ContainerRelationshipExtraConditions"
0x594b1  ldarg.0
0x594b2  call     instance class Microsoft.Crm.Metadata.RelationshipExtraConditionDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_RelationshipExtraConditions()
0x594b7  call     T0x2B00008B
0x594bc  ldarg.0
0x594bd  ldarg.1
0x594be  ldstr    aContainerviewa// "ContainerViewAttributes"
0x594c3  ldarg.0
0x594c4  call     instance class Microsoft.Crm.Metadata.ViewAttributeDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_ViewAttributes()
0x594c9  call     T0x2B00008C
0x594ce  ldarg.0
0x594cf  ldarg.1
0x594d0  ldstr    aContainerlooku// "ContainerLookupValues"
0x594d5  ldarg.0
0x594d6  call     instance class Microsoft.Crm.Metadata.AttributeLookupValueDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_LookupValues()
0x594db  call     T0x2B00008D
0x594e0  ldarg.0
0x594e1  ldarg.1
0x594e2  ldstr    aContainerpickl// "ContainerPicklistValues"
0x594e7  ldarg.0
0x594e8  call     instance class Microsoft.Crm.Metadata.EnumOptionDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_PicklistValues()
0x594ed  call     T0x2B00008E
0x594f2  ldarg.0
0x594f3  ldarg.1
0x594f4  ldstr    aContainerprivi// "ContainerPrivilegeOTCs"
0x594f9  ldarg.0
0x594fa  call     instance class Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_PrivilegeObjectTypeCodes()
0x594ff  call     T0x2B00008F
0x59504  ldarg.0
0x59505  ldarg.1
0x59506  ldstr    aContainerrolet// "ContainerRoleTemplatePrivileges"
0x5950b  ldarg.0
0x5950c  call     instance class Microsoft.Crm.Metadata.RoleTemplatePrivilegeDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_RoleTemplatePrivileges()
0x59511  call     T0x2B000090
0x59516  ldarg.0
0x59517  ldarg.1
0x59518  ldstr    aContainerentit_0// "ContainerEntityRelationships"
0x5951d  ldarg.0
0x5951e  call     instance class Microsoft.Crm.Metadata.EntityRelationshipByIdDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_EntityRelationships()
0x59523  call     T0x2B000091
0x59528  ldarg.0
0x59529  ldarg.1
0x5952a  ldstr    aContainerentit_1// "ContainerEntityRelationshipRoles"
0x5952f  ldarg.0
0x59530  call     instance class Microsoft.Crm.Metadata.EntityRelationshipRoleDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_EntityRelationshipRoles()
0x59535  call     T0x2B000092
0x5953a  ldarg.0
0x5953b  ldarg.1
0x5953c  ldstr    aContainerentit_2// "ContainerEntityRelationshipRelationship"...
0x59541  ldarg.0
0x59542  call     instance class Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_EntityRelationshipRelationships()
0x59547  call     T0x2B000093
0x5954c  ldarg.0
0x5954d  ldarg.1
0x5954e  ldstr    aContainerentit_3// "ContainerEntityKeys"
0x59553  ldarg.0
0x59554  call     instance class Microsoft.Crm.Metadata.EntityKeyByIdCollection Microsoft.Crm.Metadata.DynamicMetadataContainer::get_EntityKeys()
0x59559  call     T0x2B000094
0x5955e  ldarg.0
0x5955f  ldarg.1
0x59560  ldstr    aContainerentit_4// "ContainerEntityKeyAttributes"
0x59565  ldarg.0
0x59566  call     instance class Microsoft.Crm.Metadata.EntityKeyAttributeMetadataDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_EntityKeyAttributes()
0x5956b  call     T0x2B000095
0x59570  ldarg.0
0x59571  ldarg.1
0x59572  ldstr    aAttributesbyen// "AttributesByEntityId"
0x59577  ldarg.0
0x59578  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AttributeMetadataCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_AttributesByEntityId()
0x5957d  call     T0x2B000096
0x59582  ldarg.0
0x59583  ldarg.1
0x59584  ldstr    aAssociatedsecu// "AssociatedSecuredAttributes"
0x59589  ldarg.0
0x5958a  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AttributeCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_AssociatedSecuredAttributes()
0x5958f  call     T0x2B000097
0x59594  ldarg.0
0x59595  ldarg.1
0x59596  ldstr    aViewattributes_0// "ViewAttributesFrom"
0x5959b  ldarg.0
0x5959c  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.ViewAttributeDictionary> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_ViewAttributesFrom()
0x595a1  call     T0x2B000098
0x595a6  ldarg.0
0x595a7  ldarg.1
0x595a8  ldstr    aViewattributes_1// "ViewAttributesTo"
0x595ad  ldarg.0
0x595ae  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.ViewAttributeDictionary> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_ViewAttributesTo()
0x595b3  call     T0x2B000098
0x595b8  ldarg.0
0x595b9  ldarg.1
0x595ba  ldstr    aPicklistvalues// "PicklistValuesByOptionSet"
0x595bf  ldarg.0
0x595c0  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EnumOptionByValueDictionary> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_PicklistValuesByOptionSet()
0x595c5  call     T0x2B000099
0x595ca  ldarg.0
0x595cb  ldarg.1
0x595cc  ldstr    aReferencesfrom// "ReferencesFromEntity"
0x595d1  ldarg.0
0x595d2  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.RelationshipCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_ReferencesFromEntity()
0x595d7  call     T0x2B00009A
0x595dc  ldarg.0
0x595dd  ldarg.1
0x595de  ldstr    aReferencestoen// "ReferencesToEntity"
0x595e3  ldarg.0
0x595e4  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.RelationshipCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_ReferencesToEntity()
0x595e9  call     T0x2B00009A
0x595ee  ldarg.0
0x595ef  ldarg.1
0x595f0  ldstr    aRelationshipsb// "RelationshipsByEntityRelationship"
0x595f5  ldarg.0
0x595f6  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.RelationshipCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_RelationshipsByEntityRelationship()
0x595fb  call     T0x2B00009A
0x59600  ldarg.0
0x59601  ldarg.1
0x59602  ldstr    aChildattribute// "ChildAttributes"
0x59607  ldarg.0
0x59608  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AttributeCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_ChildAttributes()
0x5960d  call     T0x2B000097
0x59612  ldarg.0
0x59613  ldarg.1
0x59614  ldstr    aContainerprivi_0// "ContainerPrivileges"
0x59619  ldarg.0
0x5961a  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Metadata.PrivilegeCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_privilegesByOtc()
0x5961f  call     T0x2B00009B
0x59624  ldarg.0
0x59625  ldarg.1
0x59626  ldstr    aAssociationint// "AssociationIntersectRoles"
0x5962b  ldarg.0
0x5962c  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EntityRelationshipRoleCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_AssociationIntersectRoles()
0x59631  call     T0x2B00009C
0x59636  ldarg.0
0x59637  ldarg.1
0x59638  ldstr    aDenormalizedat// "DenormalizedAttributesFromAttribute"
0x5963d  ldarg.0
0x5963e  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AttributeCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_DenormalizedAttributesFromAttribute()
0x59643  call     T0x2B000097
0x59648  ldarg.0
0x59649  ldarg.1
0x5964a  ldstr    aAttributelooku_5// "AttributeLookupValuesByAttribute"
0x5964f  ldarg.0
0x59650  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.AttributeLookupValue>> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_AttributeLookupValuesByAttribute()
0x59655  call     T0x2B00009D
0x5965a  ldarg.0
0x5965b  ldarg.1
0x5965c  ldstr    aReferencingent_2// "ReferencingEntityRoles"
0x59661  ldarg.0
0x59662  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EntityRelationshipRoleCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_ReferencingEntityRoles()
0x59667  call     T0x2B00009C
0x5966c  ldarg.0
0x5966d  ldarg.1
0x5966e  ldstr    aReferencedenti_4// "ReferencedEntityRoles"
0x59673  ldarg.0
0x59674  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EntityRelationshipRoleCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_ReferencedEntityRoles()
0x59679  call     T0x2B00009C
0x5967e  ldarg.0
0x5967f  ldarg.1
0x59680  ldstr    aAssociationent// "AssociationEntityRoles"
0x59685  ldarg.0
0x59686  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EntityRelationshipRoleCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_AssociationEntityRoles()
0x5968b  call     T0x2B00009C
0x59690  ldarg.0
0x59691  ldarg.1
0x59692  ldstr    aReferencingatt_2// "ReferencingAttributesForOptionSet"
0x59697  ldarg.0
0x59698  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EnumAttributeCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_ReferencingAttributesForOptionSet()
0x5969d  call     T0x2B00009E
0x596a2  ldarg.0
0x596a3  ldarg.1
0x596a4  ldstr    aRelationshipex_7// "RelationshipExtraConditionsByRelationsh"...
0x596a9  ldarg.0
0x596aa  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.RelationshipExtraConditionCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_RelationshipExtraConditionsByRelationshipId()
0x596af  call     T0x2B00009F
0x596b4  ldarg.0
0x596b5  ldarg.1
0x596b6  ldstr    aEntityrelation_26// "EntityRelationshipRolesByEntityRelation"...
0x596bb  ldarg.0
0x596bc  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EntityRelationshipRoleCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_EntityRelationshipRolesByEntityRelationshipId()
0x596c1  call     T0x2B00009C
0x596c6  ldarg.0
0x596c7  ldarg.1
0x596c8  ldstr    aEntitiesbyobje// "EntitiesByObjectTypeCode"
0x596cd  ldarg.0
0x596ce  call     instance class Microsoft.Crm.Metadata.EntityMetadataCollection Microsoft.Crm.Metadata.DynamicMetadataContainer::get_EntitiesByObjectTypeCode()
0x596d3  call     T0x2B0000A0
0x596d8  ldarg.0
0x596d9  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Metadata.PrivilegeCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_privilegesByOtc()
0x596de  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Metadata.PrivilegeCollection>::get_Values()
0x596e3  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<int32, class Microsoft.Crm.Metadata.PrivilegeCollection>::GetEnumerator()
0x596e8  stloc.0
0x596e9  br.s     loc_59727
0x596eb  ldloca.s 0
0x596ed  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class Microsoft.Crm.Metadata.PrivilegeCollection>::get_Current()
0x596f2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x596f7  stloc.1
0x596f8  br.s     loc_5970C
0x596fa  ldloc.1
0x596fb  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x59700  castclass Microsoft.Crm.Metadata.Privilege
0x59705  ldarg.1
0x59706  ldc.i4.1
0x59707  callvirt instance void Microsoft.Crm.Metadata.MetadataSizeCollectable::GetSize(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, bool collectDeep)
0x5970c  ldloc.1
0x5970d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x59712  brtrue.s loc_596FA
0x59714  leave.s  loc_59727
0x59716  ldloc.1
0x59717  isinst   [mscorlib]System.IDisposable
0x5971c  stloc.2
0x5971d  ldloc.2
0x5971e  brfalse.s loc_59726
0x59720  ldloc.2
0x59721  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59726  endfinally
0x59727  ldloca.s 0
0x59729  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class Microsoft.Crm.Metadata.PrivilegeCollection>::MoveNext()
0x5972e  brtrue.s loc_596EB
0x59730  leave.s  loc_59740
0x59732  ldloca.s 0
0x59734  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class Microsoft.Crm.Metadata.PrivilegeCollection>
0x5973a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5973f  endfinally
0x59740  ldarg.0
0x59741  call     instance class Microsoft.Crm.Metadata.Organization Microsoft.Crm.Metadata.DynamicMetadataContainer::get_OrganizationSettings()
0x59746  brfalse.s loc_59755
0x59748  ldarg.0
0x59749  call     instance class Microsoft.Crm.Metadata.Organization Microsoft.Crm.Metadata.DynamicMetadataContainer::get_OrganizationSettings()
0x5974e  ldarg.1
0x5974f  ldc.i4.1
0x59750  callvirt instance void Microsoft.Crm.Metadata.MetadataSizeCollectable::GetSize(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, bool collectDeep)
0x59755  ldarg.1
0x59756  ldstr    aEntitiesbylogi// "EntitiesByLogicalName"
0x5975b  ldarg.0
0x5975c  call     instance class Microsoft.Crm.Metadata.EntityMetadataCollection Microsoft.Crm.Metadata.DynamicMetadataContainer::get_EntitiesByLogicalName()
0x59761  call     int64 Microsoft.Crm.Metadata.SizeCalculationHelper::GetSize(class [mscorlib]System.Collections.Hashtable table)
0x59766  callvirt instance void Microsoft.Crm.Metadata.IMetadataCacheSizeCollector::AddCollectionSize(string type, int64 size)
0x5976b  ldarg.1
0x5976c  ldstr    aPartylistassoc// "PartyListAssociatedSecuredAttributes"
0x59771  ldarg.0
0x59772  call     instance class Microsoft.Crm.Metadata.AttributeCollection Microsoft.Crm.Metadata.DynamicMetadataContainer::get_PartyListAssociatedSecuredAttributes()
0x59777  call     T0x2B0000A1
0x5977c  callvirt instance void Microsoft.Crm.Metadata.IMetadataCacheSizeCollector::AddCollectionSize(string type, int64 size)
0x59781  ret
```
