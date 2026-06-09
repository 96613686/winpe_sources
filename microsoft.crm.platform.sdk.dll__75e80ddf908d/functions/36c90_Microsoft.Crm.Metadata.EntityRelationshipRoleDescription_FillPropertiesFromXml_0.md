# Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::FillPropertiesFromXml_0

- ea: `0x36c90`
- end: `0x36f61`
- name: `Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::FillPropertiesFromXml_0`
- size: `721`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callees

- `0xbc40`
- `0xbc50`
- `0x36c90`
- `0x36f90`
- `0x36fb0`
- `0x36fd0`
- `0x36ff0`
- `0x37010`
- `0x37030`
- `0x37050`
- `0x37070`
- `0x37090`
- `0x370b0`
- `0x370d0`
- `0x370f0`
- `0x37110`
- `0x37130`
- `0x37150`
- `0x371b0`

## string_xrefs

- `0x36ca9`: `Entity Relationship Role XML must contain the EntityRelationshipRoleId`
- `0x36d10`: `Entity Relationship Role XML must contain the EntityRelationshipId property`
- `0x36d48`: `Entity Relationship Role XML must contain the EntityId property`

## pseudocode

```c

```

## disassembly

```asm
0x36c90  ldarg.1
0x36c91  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x36c96  pop
0x36c97  ldarg.1
0x36c98  ldstr    aEntityrelation_5// "EntityRelationshipRoleId"
0x36c9d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36ca2  ldnull
0x36ca3  ceq
0x36ca5  ldarg.2
0x36ca6  and
0x36ca7  brfalse.s loc_36CB4
0x36ca9  ldstr    aEntityRelation_3// "Entity Relationship Role XML must conta"...
0x36cae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x36cb3  throw
0x36cb4  ldarg.0
0x36cb5  ldarg.1
0x36cb6  ldstr    aEntityrelation_5// "EntityRelationshipRoleId"
0x36cbb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36cc0  brfalse.s loc_36CD9
0x36cc2  ldarg.1
0x36cc3  ldstr    aEntityrelation_5// "EntityRelationshipRoleId"
0x36cc8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36ccd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36cd2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x36cd7  br.s     loc_36CDE
0x36cd9  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x36cde  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_EntityRelationshipRoleId(valuetype [mscorlib]System.Guid value)
0x36ce3  ldarg.1
0x36ce4  ldstr    aEntityrelation_1// "EntityRelationshipId"
0x36ce9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36cee  brfalse.s loc_36D0D
0x36cf0  ldarg.0
0x36cf1  ldarg.1
0x36cf2  ldstr    aEntityrelation_1// "EntityRelationshipId"
0x36cf7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36cfc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36d01  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x36d06  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_EntityRelationshipId(valuetype [mscorlib]System.Guid value)
0x36d0b  br.s     loc_36D1B
0x36d0d  ldarg.2
0x36d0e  brfalse.s loc_36D1B
0x36d10  ldstr    aEntityRelation_4// "Entity Relationship Role XML must conta"...
0x36d15  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x36d1a  throw
0x36d1b  ldarg.1
0x36d1c  ldstr    aEntityid// "EntityId"
0x36d21  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36d26  brfalse.s loc_36D45
0x36d28  ldarg.0
0x36d29  ldarg.1
0x36d2a  ldstr    aEntityid// "EntityId"
0x36d2f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36d34  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36d39  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x36d3e  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_EntityId(valuetype [mscorlib]System.Guid value)
0x36d43  br.s     loc_36D53
0x36d45  ldarg.2
0x36d46  brfalse.s loc_36D53
0x36d48  ldstr    aEntityRelation_5// "Entity Relationship Role XML must conta"...
0x36d4d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x36d52  throw
0x36d53  ldarg.1
0x36d54  ldstr    aRelationshipro// "RelationshipRoleType"
0x36d59  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36d5e  brfalse.s loc_36D85
0x36d60  ldarg.0
0x36d61  ldtoken  Microsoft.Crm.Metadata.EntityRelationshipRoleType
0x36d66  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x36d6b  ldarg.1
0x36d6c  ldstr    aRelationshipro// "RelationshipRoleType"
0x36d71  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36d76  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36d7b  call     int32 Microsoft.Crm.Platform.ConvertHelper::NonFlagEnumFromXmlString(class [mscorlib]System.Type enumType, string value)
0x36d80  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_RelationshipRoleType(int32 value)
0x36d85  ldarg.1
0x36d86  ldstr    aNavpanedisplay// "NavPaneDisplayOption"
0x36d8b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36d90  brfalse.s loc_36DB7
0x36d92  ldarg.0
0x36d93  ldtoken  Microsoft.Crm.Metadata.NavPaneDisplayOption
0x36d98  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x36d9d  ldarg.1
0x36d9e  ldstr    aNavpanedisplay// "NavPaneDisplayOption"
0x36da3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36da8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36dad  call     int32 Microsoft.Crm.Platform.ConvertHelper::NonFlagEnumFromXmlString(class [mscorlib]System.Type enumType, string value)
0x36db2  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneDisplayOption(int32 value)
0x36db7  ldarg.1
0x36db8  ldstr    aNavpanearea// "NavPaneArea"
0x36dbd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36dc2  brfalse.s loc_36DE9
0x36dc4  ldarg.0
0x36dc5  ldtoken  Microsoft.Crm.Metadata.NavPaneArea
0x36dca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x36dcf  ldarg.1
0x36dd0  ldstr    aNavpanearea// "NavPaneArea"
0x36dd5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36dda  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36ddf  call     int32 Microsoft.Crm.Platform.ConvertHelper::NonFlagEnumFromXmlString(class [mscorlib]System.Type enumType, string value)
0x36de4  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneArea(int32 value)
0x36de9  ldarg.1
0x36dea  ldstr    aNavpaneid// "NavPaneId"
0x36def  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36df4  brfalse.s loc_36E0C
0x36df6  ldarg.0
0x36df7  ldarg.1
0x36df8  ldstr    aNavpaneid// "NavPaneId"
0x36dfd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36e02  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36e07  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneId(string value)
0x36e0c  ldarg.1
0x36e0d  ldstr    aNavpaneorder// "NavPaneOrder"
0x36e12  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36e17  brfalse.s loc_36E39
0x36e19  ldarg.0
0x36e1a  ldarg.1
0x36e1b  ldstr    aNavpaneorder// "NavPaneOrder"
0x36e20  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36e25  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36e2a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x36e2f  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x36e34  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneOrder(int32 value)
0x36e39  ldarg.1
0x36e3a  ldstr    aNavpaneicon// "NavPaneIcon"
0x36e3f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36e44  brfalse.s loc_36E5C
0x36e46  ldarg.0
0x36e47  ldarg.1
0x36e48  ldstr    aNavpaneicon// "NavPaneIcon"
0x36e4d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36e52  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36e57  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneIcon(string value)
0x36e5c  ldarg.1
0x36e5d  ldstr    aNavpaneoffline// "NavPaneOffline"
0x36e62  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36e67  brfalse.s loc_36E7F
0x36e69  ldarg.0
0x36e6a  ldarg.1
0x36e6b  ldstr    aNavpaneoffline// "NavPaneOffline"
0x36e70  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36e75  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x36e7a  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneOffline(bool value)
0x36e7f  ldarg.1
0x36e80  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x36e85  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36e8a  brfalse.s loc_36EA2
0x36e8c  ldarg.0
0x36e8d  ldarg.1
0x36e8e  ldstr    aNavpanequeryap// "NavPaneQueryApi"
0x36e93  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36e98  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36e9d  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneQueryApi(string value)
0x36ea2  ldarg.1
0x36ea3  ldstr    aNavpaneviewid// "NavPaneViewId"
0x36ea8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36ead  brfalse.s loc_36EC5
0x36eaf  ldarg.0
0x36eb0  ldarg.1
0x36eb1  ldstr    aNavpaneviewid// "NavPaneViewId"
0x36eb6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36ebb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36ec0  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneViewId(string value)
0x36ec5  ldarg.1
0x36ec6  ldstr    aNavpaneiscusto// "NavPaneIsCustomizable"
0x36ecb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36ed0  brfalse.s loc_36EE8
0x36ed2  ldarg.0
0x36ed3  ldarg.1
0x36ed4  ldstr    aNavpaneiscusto// "NavPaneIsCustomizable"
0x36ed9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36ede  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x36ee3  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneIsCustomizable(bool value)
0x36ee8  ldarg.1
0x36ee9  ldstr    aIntersectentit// "IntersectEntityAttributeId"
0x36eee  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36ef3  brfalse.s loc_36F10
0x36ef5  ldarg.0
0x36ef6  ldarg.1
0x36ef7  ldstr    aIntersectentit// "IntersectEntityAttributeId"
0x36efc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36f01  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36f06  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x36f0b  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_IntersectEntityAttributeId(valuetype [mscorlib]System.Guid value)
0x36f10  ldarg.1
0x36f11  ldstr    aAssociationrol// "AssociationRoleOrdinal"
0x36f16  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36f1b  brfalse.s loc_36F3D
0x36f1d  ldarg.0
0x36f1e  ldarg.1
0x36f1f  ldstr    aAssociationrol// "AssociationRoleOrdinal"
0x36f24  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36f29  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36f2e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x36f33  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x36f38  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_AssociationRoleOrdinal(int32 value)
0x36f3d  ldarg.1
0x36f3e  ldstr    aNavigationprop// "NavigationPropertyName"
0x36f43  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36f48  brfalse.s loc_36F60
0x36f4a  ldarg.0
0x36f4b  ldarg.1
0x36f4c  ldstr    aNavigationprop// "NavigationPropertyName"
0x36f51  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36f56  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36f5b  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavigationPropertyName(string value)
0x36f60  ret
```
