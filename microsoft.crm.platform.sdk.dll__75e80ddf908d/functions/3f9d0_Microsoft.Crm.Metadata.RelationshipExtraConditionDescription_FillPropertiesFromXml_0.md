# Microsoft.Crm.Metadata.RelationshipExtraConditionDescription::FillPropertiesFromXml_0

- ea: `0x3f9d0`
- end: `0x3fae2`
- name: `Microsoft.Crm.Metadata.RelationshipExtraConditionDescription::FillPropertiesFromXml_0`
- size: `274`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x183a0`
- `0x3f9d0`
- `0x3fb10`
- `0x3fb30`
- `0x3fb50`
- `0x3fb70`
- `0x3fb90`

## string_xrefs

- `0x3f9e9`: `RelationshipExtraCondition XML requires the ConditionId`
- `0x3fa9f`: `RelationshipExtraCondition XML requires the RelationshipId`
- `0x3fad6`: `RelationshipExtraCondition XML requires the AttributeId`

## pseudocode

```c

```

## disassembly

```asm
0x3f9d0  ldarg.1
0x3f9d1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3f9d6  stloc.0
0x3f9d7  ldloc.0
0x3f9d8  ldstr    aConditionid// "ConditionId"
0x3f9dd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3f9e2  ldnull
0x3f9e3  ceq
0x3f9e5  ldarg.2
0x3f9e6  and
0x3f9e7  brfalse.s loc_3F9F4
0x3f9e9  ldstr    aRelationshipex_2// "RelationshipExtraCondition XML requires"...
0x3f9ee  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3f9f3  throw
0x3f9f4  ldarg.0
0x3f9f5  ldloc.0
0x3f9f6  ldstr    aConditionid// "ConditionId"
0x3f9fb  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3fa00  brfalse.s loc_3FA19
0x3fa02  ldloc.0
0x3fa03  ldstr    aConditionid// "ConditionId"
0x3fa08  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3fa0d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x3fa12  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3fa17  br.s     loc_3FA1E
0x3fa19  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3fa1e  callvirt instance void Microsoft.Crm.Metadata.RelationshipExtraConditionDescription::set_ConditionId(valuetype [mscorlib]System.Guid value)
0x3fa23  ldarg.0
0x3fa24  ldloc.0
0x3fa25  ldstr    aOperator// "Operator"
0x3fa2a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3fa2f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x3fa34  call     unsigned int8 Microsoft.Crm.Metadata.RelationshipExtraCondition::ConditionOperatorFromXmlString(string strOperator)
0x3fa39  callvirt instance void Microsoft.Crm.Metadata.RelationshipExtraConditionDescription::set_ConditionOp(unsigned int8 value)
0x3fa3e  ldarg.0
0x3fa3f  ldloc.0
0x3fa40  ldstr    aValue_0// "Value"
0x3fa45  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3fa4a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x3fa4f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3fa54  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3fa59  callvirt instance void Microsoft.Crm.Metadata.RelationshipExtraConditionDescription::set_Value(int32 value)
0x3fa5e  ldarg.1
0x3fa5f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x3fa64  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x3fa69  ldstr    aRelationshipid_0// "RelationshipId"
0x3fa6e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3fa73  brfalse.s loc_3FA9C
0x3fa75  ldarg.0
0x3fa76  ldarg.1
0x3fa77  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x3fa7c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x3fa81  ldstr    aRelationshipid_0// "RelationshipId"
0x3fa86  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3fa8b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3fa90  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3fa95  callvirt instance void Microsoft.Crm.Metadata.RelationshipExtraConditionDescription::set_RelationshipId(valuetype [mscorlib]System.Guid value)
0x3fa9a  br.s     loc_3FAAA
0x3fa9c  ldarg.2
0x3fa9d  brfalse.s loc_3FAAA
0x3fa9f  ldstr    aRelationshipex_3// "RelationshipExtraCondition XML requires"...
0x3faa4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3faa9  throw
0x3faaa  ldloc.0
0x3faab  ldstr    aAttributeid// "AttributeId"
0x3fab0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3fab5  brfalse.s loc_3FAD3
0x3fab7  ldarg.0
0x3fab8  ldloc.0
0x3fab9  ldstr    aAttributeid// "AttributeId"
0x3fabe  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3fac3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x3fac8  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3facd  callvirt instance void Microsoft.Crm.Metadata.RelationshipExtraConditionDescription::set_AttributeId(valuetype [mscorlib]System.Guid value)
0x3fad2  ret
0x3fad3  ldarg.2
0x3fad4  brfalse.s loc_3FAE1
0x3fad6  ldstr    aRelationshipex_4// "RelationshipExtraCondition XML requires"...
0x3fadb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3fae0  throw
0x3fae1  ret
```
