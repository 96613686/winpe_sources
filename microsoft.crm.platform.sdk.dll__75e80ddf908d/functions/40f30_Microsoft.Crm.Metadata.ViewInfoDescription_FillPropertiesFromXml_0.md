# Microsoft.Crm.Metadata.ViewInfoDescription::FillPropertiesFromXml_0

- ea: `0x40f30`
- end: `0x41076`
- name: `Microsoft.Crm.Metadata.ViewInfoDescription::FillPropertiesFromXml_0`
- size: `326`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0xbc60`
- `0x40f30`
- `0x410a0`
- `0x410c0`
- `0x410e0`
- `0x41100`
- `0x41120`

## string_xrefs

- `0x40f42`: `ViewAttribute XML requires the ViewAttributeId`
- `0x40fe9`: `ViewAttribute XML requires the AttributeId`
- `0x4106a`: `ViewAttribute XML requires the RelationshipId and RemoteAttributeId`

## pseudocode

```c

```

## disassembly

```asm
0x40f30  ldarg.1
0x40f31  ldstr    aViewattributei// "ViewAttributeId"
0x40f36  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40f3b  ldnull
0x40f3c  ceq
0x40f3e  ldarg.2
0x40f3f  and
0x40f40  brfalse.s loc_40F4D
0x40f42  ldstr    aViewattributeX// "ViewAttribute XML requires the ViewAttr"...
0x40f47  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x40f4c  throw
0x40f4d  ldarg.0
0x40f4e  ldarg.1
0x40f4f  ldstr    aViewattributei// "ViewAttributeId"
0x40f54  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40f59  brfalse.s loc_40F72
0x40f5b  ldarg.1
0x40f5c  ldstr    aViewattributei// "ViewAttributeId"
0x40f61  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40f66  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x40f6b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x40f70  br.s     loc_40F77
0x40f72  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x40f77  callvirt instance void Microsoft.Crm.Metadata.ViewInfoDescription::set_ViewAttributeId(valuetype [mscorlib]System.Guid value)
0x40f7c  ldarg.0
0x40f7d  ldarg.1
0x40f7e  ldstr    aIsdenormalized// "IsDenormalized"
0x40f83  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40f88  ldc.i4.0
0x40f89  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node, bool defaultValue)
0x40f8e  callvirt instance void Microsoft.Crm.Metadata.ViewInfoDescription::set_IsDenormalized(bool value)
0x40f93  ldarg.1
0x40f94  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x40f99  brfalse.s loc_40FE6
0x40f9b  ldarg.1
0x40f9c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x40fa1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x40fa6  brfalse.s loc_40FE6
0x40fa8  ldarg.1
0x40fa9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x40fae  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x40fb3  ldstr    aAttributeid// "AttributeId"
0x40fb8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40fbd  brfalse.s loc_40FE6
0x40fbf  ldarg.0
0x40fc0  ldarg.1
0x40fc1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x40fc6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x40fcb  ldstr    aAttributeid// "AttributeId"
0x40fd0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40fd5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x40fda  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x40fdf  callvirt instance void Microsoft.Crm.Metadata.ViewInfoDescription::set_AttributeId(valuetype [mscorlib]System.Guid value)
0x40fe4  br.s     loc_40FF4
0x40fe6  ldarg.2
0x40fe7  brfalse.s loc_40FF4
0x40fe9  ldstr    aViewattributeX_0// "ViewAttribute XML requires the Attribut"...
0x40fee  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x40ff3  throw
0x40ff4  ldarg.1
0x40ff5  ldstr    aRelationshipna_0// "RelationshipName"
0x40ffa  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40fff  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x41004  pop
0x41005  ldarg.1
0x41006  ldstr    aRemoteattribut_0// "RemoteAttributeName"
0x4100b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x41010  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x41015  pop
0x41016  ldarg.1
0x41017  ldstr    aRelationshipid_0// "RelationshipId"
0x4101c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x41021  brfalse.s loc_41067
0x41023  ldarg.1
0x41024  ldstr    aRemoteattribut// "RemoteAttributeId"
0x41029  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4102e  brfalse.s loc_41067
0x41030  ldarg.0
0x41031  ldarg.1
0x41032  ldstr    aRelationshipid_0// "RelationshipId"
0x41037  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4103c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x41041  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x41046  callvirt instance void Microsoft.Crm.Metadata.ViewInfoDescription::set_RelationshipId(valuetype [mscorlib]System.Guid value)
0x4104b  ldarg.0
0x4104c  ldarg.1
0x4104d  ldstr    aRemoteattribut// "RemoteAttributeId"
0x41052  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x41057  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x4105c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x41061  callvirt instance void Microsoft.Crm.Metadata.ViewInfoDescription::set_RemoteAttributeId(valuetype [mscorlib]System.Guid value)
0x41066  ret
0x41067  ldarg.2
0x41068  brfalse.s loc_41075
0x4106a  ldstr    aViewattributeX_1// "ViewAttribute XML requires the Relation"...
0x4106f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x41074  throw
0x41075  ret
```
