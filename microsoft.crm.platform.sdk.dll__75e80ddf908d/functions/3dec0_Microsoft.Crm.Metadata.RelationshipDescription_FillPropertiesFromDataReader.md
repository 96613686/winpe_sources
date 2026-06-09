# Microsoft.Crm.Metadata.RelationshipDescription::FillPropertiesFromDataReader

- ea: `0x3dec0`
- end: `0x3e2f3`
- name: `Microsoft.Crm.Metadata.RelationshipDescription::FillPropertiesFromDataReader`
- size: `1075`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x3eef0`

## callees

- `0xbc80`
- `0x18a90`
- `0x3dea0`
- `0x3dec0`
- `0x3e7a0`
- `0x3e7c0`
- `0x3e7e0`
- `0x3e800`
- `0x3e820`
- `0x3e840`
- `0x3e860`
- `0x3e880`
- `0x3e8a0`
- `0x3e8c0`
- `0x3e8e0`
- `0x3e900`
- `0x3e920`
- `0x3e940`
- `0x3e960`
- `0x3e980`
- `0x3e9a0`
- `0x3e9c0`
- `0x3ea20`
- `0x708f0`
- `0x709b0`
- `0x71110`

## string_xrefs

- `0x3e0b8`: `CascadeDelete`
- `0x3e0da`: `CascadeDelete`
- `0x3e276`: `CascadeLinkMask`

## pseudocode

```c

```

## disassembly

```asm
0x3dec0  ldarg.0
0x3dec1  ldarg.1
0x3dec2  ldarg.2
0x3dec3  call     instance void Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::FillPropertiesFromDataReader(class [System.Data]System.Data.IDataReader reader, [opt] class Microsoft.Crm.Metadata.MetadataForMetadata metadataForMetadata)
0x3dec8  ldarg.1
0x3dec9  ldstr    aRelationshipid_0// "RelationshipId"
0x3dece  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3ded3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3ded8  ldtoken  [mscorlib]System.DBNull
0x3dedd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3dee2  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3dee7  brfalse.s loc_3DEFF
0x3dee9  ldarg.0
0x3deea  ldarg.1
0x3deeb  ldstr    aRelationshipid_0// "RelationshipId"
0x3def0  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3def5  unbox.any [mscorlib]System.Guid
0x3defa  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_RelationshipId(valuetype [mscorlib]System.Guid value)
0x3deff  ldarg.1
0x3df00  ldstr    aName// "Name"
0x3df05  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3df0a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3df0f  ldtoken  [mscorlib]System.DBNull
0x3df14  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3df19  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3df1e  brfalse.s loc_3DF36
0x3df20  ldarg.0
0x3df21  ldarg.1
0x3df22  ldstr    aName// "Name"
0x3df27  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3df2c  castclass [mscorlib]System.String
0x3df31  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_Name(string value)
0x3df36  ldarg.1
0x3df37  ldstr    aReferencingent// "ReferencingEntityId"
0x3df3c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3df41  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3df46  ldtoken  [mscorlib]System.DBNull
0x3df4b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3df50  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3df55  brfalse.s loc_3DF6D
0x3df57  ldarg.0
0x3df58  ldarg.1
0x3df59  ldstr    aReferencingent// "ReferencingEntityId"
0x3df5e  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3df63  unbox.any [mscorlib]System.Guid
0x3df68  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_ReferencingEntityId(valuetype [mscorlib]System.Guid value)
0x3df6d  ldarg.1
0x3df6e  ldstr    aReferencingatt// "ReferencingAttributeId"
0x3df73  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3df78  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3df7d  ldtoken  [mscorlib]System.DBNull
0x3df82  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3df87  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3df8c  brfalse.s loc_3DFA4
0x3df8e  ldarg.0
0x3df8f  ldarg.1
0x3df90  ldstr    aReferencingatt// "ReferencingAttributeId"
0x3df95  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3df9a  unbox.any [mscorlib]System.Guid
0x3df9f  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_ReferencingAttributeId(valuetype [mscorlib]System.Guid value)
0x3dfa4  ldarg.1
0x3dfa5  ldstr    aReferencedenti_0// "ReferencedEntityId"
0x3dfaa  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3dfaf  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3dfb4  ldtoken  [mscorlib]System.DBNull
0x3dfb9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3dfbe  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3dfc3  brfalse.s loc_3DFDB
0x3dfc5  ldarg.0
0x3dfc6  ldarg.1
0x3dfc7  ldstr    aReferencedenti_0// "ReferencedEntityId"
0x3dfcc  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3dfd1  unbox.any [mscorlib]System.Guid
0x3dfd6  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_ReferencedEntityId(valuetype [mscorlib]System.Guid value)
0x3dfdb  ldarg.1
0x3dfdc  ldstr    aReferencedattr// "ReferencedAttributeId"
0x3dfe1  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3dfe6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3dfeb  ldtoken  [mscorlib]System.DBNull
0x3dff0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3dff5  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3dffa  brfalse.s loc_3E012
0x3dffc  ldarg.0
0x3dffd  ldarg.1
0x3dffe  ldstr    aReferencedattr// "ReferencedAttributeId"
0x3e003  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e008  unbox.any [mscorlib]System.Guid
0x3e00d  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_ReferencedAttributeId(valuetype [mscorlib]System.Guid value)
0x3e012  ldarg.1
0x3e013  ldstr    aRelationshipty// "RelationshipType"
0x3e018  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e01d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e022  ldtoken  [mscorlib]System.DBNull
0x3e027  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e02c  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3e031  brfalse.s loc_3E049
0x3e033  ldarg.0
0x3e034  ldarg.1
0x3e035  ldstr    aRelationshipty// "RelationshipType"
0x3e03a  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e03f  unbox.any Microsoft.Crm.Metadata.RelationshipTypes
0x3e044  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_RelationshipType(valuetype Microsoft.Crm.Metadata.RelationshipTypes value)
0x3e049  ldarg.1
0x3e04a  ldstr    aIslogical// "IsLogical"
0x3e04f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e054  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e059  ldtoken  [mscorlib]System.DBNull
0x3e05e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e063  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3e068  brfalse.s loc_3E080
0x3e06a  ldarg.0
0x3e06b  ldarg.1
0x3e06c  ldstr    aIslogical// "IsLogical"
0x3e071  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e076  unbox.any [mscorlib]System.Boolean
0x3e07b  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_IsLogical(bool value)
0x3e080  ldarg.1
0x3e081  ldstr    aIsvalidforadva// "IsValidForAdvancedFind"
0x3e086  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e08b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e090  ldtoken  [mscorlib]System.DBNull
0x3e095  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e09a  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3e09f  brfalse.s loc_3E0B7
0x3e0a1  ldarg.0
0x3e0a2  ldarg.1
0x3e0a3  ldstr    aIsvalidforadva// "IsValidForAdvancedFind"
0x3e0a8  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e0ad  unbox.any [mscorlib]System.Boolean
0x3e0b2  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_IsValidForAdvancedFind(bool value)
0x3e0b7  ldarg.1
0x3e0b8  ldstr    aCascadedelete// "CascadeDelete"
0x3e0bd  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e0c2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e0c7  ldtoken  [mscorlib]System.DBNull
0x3e0cc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e0d1  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3e0d6  brfalse.s loc_3E0EE
0x3e0d8  ldarg.0
0x3e0d9  ldarg.1
0x3e0da  ldstr    aCascadedelete// "CascadeDelete"
0x3e0df  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e0e4  unbox.any [mscorlib]System.Byte
0x3e0e9  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeDelete(valuetype Microsoft.Crm.Metadata.CascadeLinkType value)
0x3e0ee  ldarg.1
0x3e0ef  ldstr    aCascadeassign// "CascadeAssign"
0x3e0f4  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e0f9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e0fe  ldtoken  [mscorlib]System.DBNull
0x3e103  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e108  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3e10d  brfalse.s loc_3E125
0x3e10f  ldarg.0
0x3e110  ldarg.1
0x3e111  ldstr    aCascadeassign// "CascadeAssign"
0x3e116  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e11b  unbox.any [mscorlib]System.Byte
0x3e120  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeAssign(valuetype Microsoft.Crm.Metadata.CascadeLinkType value)
0x3e125  ldarg.1
0x3e126  ldstr    aCascadeshare// "CascadeShare"
0x3e12b  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e130  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e135  ldtoken  [mscorlib]System.DBNull
0x3e13a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e13f  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3e144  brfalse.s loc_3E15C
0x3e146  ldarg.0
0x3e147  ldarg.1
0x3e148  ldstr    aCascadeshare// "CascadeShare"
0x3e14d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e152  unbox.any [mscorlib]System.Byte
0x3e157  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeShare(valuetype Microsoft.Crm.Metadata.CascadeLinkType value)
0x3e15c  ldarg.1
0x3e15d  ldstr    aCascadeunshare// "CascadeUnshare"
0x3e162  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e167  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e16c  ldtoken  [mscorlib]System.DBNull
0x3e171  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e176  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3e17b  brfalse.s loc_3E193
0x3e17d  ldarg.0
0x3e17e  ldarg.1
0x3e17f  ldstr    aCascadeunshare// "CascadeUnshare"
0x3e184  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e189  unbox.any [mscorlib]System.Byte
0x3e18e  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeUnshare(valuetype Microsoft.Crm.Metadata.CascadeLinkType value)
0x3e193  ldarg.1
0x3e194  ldstr    aCascademerge// "CascadeMerge"
0x3e199  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e19e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e1a3  ldtoken  [mscorlib]System.DBNull
0x3e1a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e1ad  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3e1b2  brfalse.s loc_3E1CA
0x3e1b4  ldarg.0
0x3e1b5  ldarg.1
0x3e1b6  ldstr    aCascademerge// "CascadeMerge"
0x3e1bb  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e1c0  unbox.any [mscorlib]System.Byte
0x3e1c5  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeMerge(valuetype Microsoft.Crm.Metadata.CascadeLinkType value)
0x3e1ca  ldarg.1
0x3e1cb  ldstr    aCascadereparen// "CascadeReparent"
0x3e1d0  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e1d5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e1da  ldtoken  [mscorlib]System.DBNull
0x3e1df  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e1e4  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3e1e9  brfalse.s loc_3E201
0x3e1eb  ldarg.0
0x3e1ec  ldarg.1
0x3e1ed  ldstr    aCascadereparen// "CascadeReparent"
0x3e1f2  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e1f7  unbox.any [mscorlib]System.Byte
0x3e1fc  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeReparent(valuetype Microsoft.Crm.Metadata.CascadeLinkType value)
0x3e201  ldarg.1
0x3e202  ldstr    aIscustomrelati// "IsCustomRelationship"
0x3e207  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e20c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e211  ldtoken  [mscorlib]System.DBNull
0x3e216  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e21b  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3e220  brfalse.s loc_3E238
0x3e222  ldarg.0
0x3e223  ldarg.1
0x3e224  ldstr    aIscustomrelati// "IsCustomRelationship"
0x3e229  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e22e  unbox.any [mscorlib]System.Boolean
0x3e233  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_IsCustomRelationship(bool value)
0x3e238  ldarg.1
0x3e239  ldstr    aIntroducedvers// "IntroducedVersion"
0x3e23e  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e243  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e248  ldtoken  [mscorlib]System.DBNull
0x3e24d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e252  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3e257  brfalse.s loc_3E274
0x3e259  ldarg.0
0x3e25a  ldarg.1
0x3e25b  ldstr    aIntroducedvers// "IntroducedVersion"
0x3e260  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e265  castclass [mscorlib]System.String
0x3e26a  call     class [mscorlib]System.Version Microsoft.Crm.Platform.ConvertHelper::ToVersionFromString(string value)
0x3e26f  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_IntroducedVersion(class [mscorlib]System.Version value)
0x3e274  ldarg.0
0x3e275  ldarg.1
0x3e276  ldstr    aCascadelinkmas// "CascadeLinkMask"
0x3e27b  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e280  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3e285  call     int64 [mscorlib]System.Convert::ToInt64(object, class [mscorlib]System.IFormatProvider)
0x3e28a  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeLinkMask(int64 value)
0x3e28f  ldarg.2
0x3e290  brtrue.s loc_3E29F
0x3e292  ldarg.0
0x3e293  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Metadata.RelationshipDescription::get_OrganizationContext()
0x3e298  call     class Microsoft.Crm.Metadata.MetadataForMetadata Microsoft.Crm.Metadata.MetadataForMetadata::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3e29d  starg.s  2
0x3e29f  ldarg.2
0x3e2a0  ldstr    aRelationship_0// "Relationship"
0x3e2a5  callvirt instance class Microsoft.Crm.Metadata.MetadataEntityMetadata Microsoft.Crm.Metadata.MetadataForMetadata::GetMetadataEntityByName(string metadataEntityName)
0x3e2aa  callvirt instance class Microsoft.Crm.Metadata.MetadataAttributeMetadataDictionary Microsoft.Crm.Metadata.MetadataEntityMetadata::get_Attributes()
0x3e2af  ldstr    aCascaderollupv_0// "cascaderollupview"
0x3e2b4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Metadata.MetadataAttributeMetadata>::ContainsKey(var<u1>)
0x3e2b9  brfalse.s loc_3E2F2
0x3e2bb  ldarg.1
0x3e2bc  ldstr    aCascaderollupv// "CascadeRollupView"
0x3e2c1  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e2c6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e2cb  ldtoken  [mscorlib]System.DBNull
0x3e2d0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e2d5  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3e2da  brfalse.s loc_3E2F2
0x3e2dc  ldarg.0
0x3e2dd  ldarg.1
0x3e2de  ldstr    aCascaderollupv// "CascadeRollupView"
0x3e2e3  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3e2e8  unbox.any [mscorlib]System.Byte
0x3e2ed  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeRollupView(valuetype Microsoft.Crm.Metadata.CascadeLinkType value)
0x3e2f2  ret
```
