# Microsoft.Crm.Metadata.RelationshipDescription::FillPropertiesFromXml_0

- ea: `0x3e310`
- end: `0x3e647`
- name: `Microsoft.Crm.Metadata.RelationshipDescription::FillPropertiesFromXml_0`
- size: `823`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callees

- `0xbbf0`
- `0xbc50`
- `0xbc80`
- `0x3e310`
- `0x3e6b0`
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
- `0x3ea20`
- `0x6f350`

## string_xrefs

- `0x3e3ff`: `CascadeDelete`
- `0x3e40d`: `CascadeDelete`
- `0x3e329`: `Relationship XML requires the RelationshipId`
- `0x3e594`: `Relationship XML requires the ReferencingEntityId`
- `0x3e5cc`: `Relationship XML requires the ReferencedEntityId`
- `0x3e604`: `Relationship XML requires the ReferencingAttributeId`
- `0x3e63b`: `Relationship XML requires the ReferencedAttributeId`

## pseudocode

```c

```

## disassembly

```asm
0x3e310  ldarg.1
0x3e311  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3e316  stloc.0
0x3e317  ldarg.1
0x3e318  ldstr    aRelationshipid_0// "RelationshipId"
0x3e31d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e322  ldnull
0x3e323  ceq
0x3e325  ldarg.2
0x3e326  and
0x3e327  brfalse.s loc_3E334
0x3e329  ldstr    aRelationshipXm// "Relationship XML requires the Relations"...
0x3e32e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3e333  throw
0x3e334  ldarg.0
0x3e335  ldarg.1
0x3e336  ldstr    aRelationshipid_0// "RelationshipId"
0x3e33b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e340  brfalse.s loc_3E359
0x3e342  ldarg.1
0x3e343  ldstr    aRelationshipid_0// "RelationshipId"
0x3e348  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e34d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3e352  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3e357  br.s     loc_3E35E
0x3e359  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3e35e  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_RelationshipId(valuetype [mscorlib]System.Guid value)
0x3e363  ldloc.0
0x3e364  ldstr    aName// "Name"
0x3e369  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3e36e  brfalse.s loc_3E386
0x3e370  ldarg.0
0x3e371  ldloc.0
0x3e372  ldstr    aName// "Name"
0x3e377  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3e37c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x3e381  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_Name(string value)
0x3e386  ldarg.1
0x3e387  ldstr    aRelationtype// "RelationType"
0x3e38c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e391  brfalse.s loc_3E3B8
0x3e393  ldarg.0
0x3e394  ldtoken  Microsoft.Crm.Metadata.RelationshipTypes
0x3e399  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e39e  ldarg.1
0x3e39f  ldstr    aRelationtype// "RelationType"
0x3e3a4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e3a9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3e3ae  call     int32 Microsoft.Crm.Platform.ConvertHelper::EnumFromXmlString(class [mscorlib]System.Type enumType, string mask)
0x3e3b3  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_RelationshipType(valuetype Microsoft.Crm.Metadata.RelationshipTypes value)
0x3e3b8  ldarg.1
0x3e3b9  ldstr    aIslogical// "IsLogical"
0x3e3be  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e3c3  brfalse.s loc_3E3DB
0x3e3c5  ldarg.0
0x3e3c6  ldarg.1
0x3e3c7  ldstr    aIslogical// "IsLogical"
0x3e3cc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e3d1  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x3e3d6  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_IsLogical(bool value)
0x3e3db  ldarg.1
0x3e3dc  ldstr    aIsvalidforadva// "IsValidForAdvancedFind"
0x3e3e1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e3e6  brfalse.s loc_3E3FE
0x3e3e8  ldarg.0
0x3e3e9  ldarg.1
0x3e3ea  ldstr    aIsvalidforadva// "IsValidForAdvancedFind"
0x3e3ef  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e3f4  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x3e3f9  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_IsValidForAdvancedFind(bool value)
0x3e3fe  ldarg.1
0x3e3ff  ldstr    aCascadedelete// "CascadeDelete"
0x3e404  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e409  brfalse.s loc_3E426
0x3e40b  ldarg.0
0x3e40c  ldarg.1
0x3e40d  ldstr    aCascadedelete// "CascadeDelete"
0x3e412  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e417  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3e41c  call     valuetype Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Metadata.RelationshipSerializationHelper::CascadeLinkTypeFromXmlString(string strCascadeLinkType)
0x3e421  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeDelete(valuetype Microsoft.Crm.Metadata.CascadeLinkType value)
0x3e426  ldarg.1
0x3e427  ldstr    aCascadeassign// "CascadeAssign"
0x3e42c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e431  brfalse.s loc_3E44E
0x3e433  ldarg.0
0x3e434  ldarg.1
0x3e435  ldstr    aCascadeassign// "CascadeAssign"
0x3e43a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e43f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3e444  call     valuetype Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Metadata.RelationshipSerializationHelper::CascadeLinkTypeFromXmlString(string strCascadeLinkType)
0x3e449  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeAssign(valuetype Microsoft.Crm.Metadata.CascadeLinkType value)
0x3e44e  ldarg.1
0x3e44f  ldstr    aCascadeshare// "CascadeShare"
0x3e454  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e459  brfalse.s loc_3E476
0x3e45b  ldarg.0
0x3e45c  ldarg.1
0x3e45d  ldstr    aCascadeshare// "CascadeShare"
0x3e462  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e467  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3e46c  call     valuetype Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Metadata.RelationshipSerializationHelper::CascadeLinkTypeFromXmlString(string strCascadeLinkType)
0x3e471  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeShare(valuetype Microsoft.Crm.Metadata.CascadeLinkType value)
0x3e476  ldarg.1
0x3e477  ldstr    aCascadeunshare// "CascadeUnshare"
0x3e47c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e481  brfalse.s loc_3E49E
0x3e483  ldarg.0
0x3e484  ldarg.1
0x3e485  ldstr    aCascadeunshare// "CascadeUnshare"
0x3e48a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e48f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3e494  call     valuetype Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Metadata.RelationshipSerializationHelper::CascadeLinkTypeFromXmlString(string strCascadeLinkType)
0x3e499  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeUnshare(valuetype Microsoft.Crm.Metadata.CascadeLinkType value)
0x3e49e  ldarg.1
0x3e49f  ldstr    aCascademerge// "CascadeMerge"
0x3e4a4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e4a9  brfalse.s loc_3E4C6
0x3e4ab  ldarg.0
0x3e4ac  ldarg.1
0x3e4ad  ldstr    aCascademerge// "CascadeMerge"
0x3e4b2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e4b7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3e4bc  call     valuetype Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Metadata.RelationshipSerializationHelper::CascadeLinkTypeFromXmlString(string strCascadeLinkType)
0x3e4c1  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeMerge(valuetype Microsoft.Crm.Metadata.CascadeLinkType value)
0x3e4c6  ldarg.1
0x3e4c7  ldstr    aCascaderollupv// "CascadeRollupView"
0x3e4cc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e4d1  brfalse.s loc_3E4EE
0x3e4d3  ldarg.0
0x3e4d4  ldarg.1
0x3e4d5  ldstr    aCascaderollupv// "CascadeRollupView"
0x3e4da  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e4df  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3e4e4  call     valuetype Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Metadata.RelationshipSerializationHelper::CascadeLinkTypeFromXmlString(string strCascadeLinkType)
0x3e4e9  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeRollupView(valuetype Microsoft.Crm.Metadata.CascadeLinkType value)
0x3e4ee  ldarg.1
0x3e4ef  ldstr    aCascadereparen// "CascadeReparent"
0x3e4f4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e4f9  brfalse.s loc_3E516
0x3e4fb  ldarg.0
0x3e4fc  ldarg.1
0x3e4fd  ldstr    aCascadereparen// "CascadeReparent"
0x3e502  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e507  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3e50c  call     valuetype Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Metadata.RelationshipSerializationHelper::CascadeLinkTypeFromXmlString(string strCascadeLinkType)
0x3e511  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_CascadeReparent(valuetype Microsoft.Crm.Metadata.CascadeLinkType value)
0x3e516  ldarg.1
0x3e517  ldstr    aIscustomrelati// "IsCustomRelationship"
0x3e51c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e521  brfalse.s loc_3E539
0x3e523  ldarg.0
0x3e524  ldarg.1
0x3e525  ldstr    aIscustomrelati// "IsCustomRelationship"
0x3e52a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e52f  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x3e534  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_IsCustomRelationship(bool value)
0x3e539  ldarg.1
0x3e53a  ldstr    aIntroducedvers// "IntroducedVersion"
0x3e53f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e544  brfalse.s loc_3E561
0x3e546  ldarg.0
0x3e547  ldarg.1
0x3e548  ldstr    aIntroducedvers// "IntroducedVersion"
0x3e54d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e552  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3e557  call     class [mscorlib]System.Version Microsoft.Crm.Platform.ConvertHelper::ToVersionFromString(string value)
0x3e55c  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_IntroducedVersion(class [mscorlib]System.Version value)
0x3e561  ldarg.0
0x3e562  call     instance void Microsoft.Crm.Metadata.RelationshipDescription::DefaultCascadeLinkMask()
0x3e567  ldarg.1
0x3e568  ldstr    aReferencingent// "ReferencingEntityId"
0x3e56d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e572  brfalse.s loc_3E591
0x3e574  ldarg.0
0x3e575  ldarg.1
0x3e576  ldstr    aReferencingent// "ReferencingEntityId"
0x3e57b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e580  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3e585  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3e58a  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_ReferencingEntityId(valuetype [mscorlib]System.Guid value)
0x3e58f  br.s     loc_3E59F
0x3e591  ldarg.2
0x3e592  brfalse.s loc_3E59F
0x3e594  ldstr    aRelationshipXm_0// "Relationship XML requires the Referenci"...
0x3e599  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3e59e  throw
0x3e59f  ldarg.1
0x3e5a0  ldstr    aReferencedenti_0// "ReferencedEntityId"
0x3e5a5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e5aa  brfalse.s loc_3E5C9
0x3e5ac  ldarg.0
0x3e5ad  ldarg.1
0x3e5ae  ldstr    aReferencedenti_0// "ReferencedEntityId"
0x3e5b3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e5b8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3e5bd  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3e5c2  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_ReferencedEntityId(valuetype [mscorlib]System.Guid value)
0x3e5c7  br.s     loc_3E5D7
0x3e5c9  ldarg.2
0x3e5ca  brfalse.s loc_3E5D7
0x3e5cc  ldstr    aRelationshipXm_1// "Relationship XML requires the Reference"...
0x3e5d1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3e5d6  throw
0x3e5d7  ldarg.1
0x3e5d8  ldstr    aReferencingatt// "ReferencingAttributeId"
0x3e5dd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e5e2  brfalse.s loc_3E601
0x3e5e4  ldarg.0
0x3e5e5  ldarg.1
0x3e5e6  ldstr    aReferencingatt// "ReferencingAttributeId"
0x3e5eb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e5f0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3e5f5  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3e5fa  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_ReferencingAttributeId(valuetype [mscorlib]System.Guid value)
0x3e5ff  br.s     loc_3E60F
0x3e601  ldarg.2
0x3e602  brfalse.s loc_3E60F
0x3e604  ldstr    aRelationshipXm_2// "Relationship XML requires the Referenci"...
0x3e609  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3e60e  throw
0x3e60f  ldarg.1
0x3e610  ldstr    aReferencedattr// "ReferencedAttributeId"
0x3e615  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e61a  brfalse.s loc_3E638
0x3e61c  ldarg.0
0x3e61d  ldarg.1
0x3e61e  ldstr    aReferencedattr// "ReferencedAttributeId"
0x3e623  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3e628  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3e62d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3e632  callvirt instance void Microsoft.Crm.Metadata.RelationshipDescription::set_ReferencedAttributeId(valuetype [mscorlib]System.Guid value)
0x3e637  ret
0x3e638  ldarg.2
0x3e639  brfalse.s loc_3E646
0x3e63b  ldstr    aRelationshipXm_3// "Relationship XML requires the Reference"...
0x3e640  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3e645  throw
0x3e646  ret
```
