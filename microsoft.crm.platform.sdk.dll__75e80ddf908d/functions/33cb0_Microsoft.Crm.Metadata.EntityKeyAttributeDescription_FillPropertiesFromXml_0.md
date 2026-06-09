# Microsoft.Crm.Metadata.EntityKeyAttributeDescription::FillPropertiesFromXml_0

- ea: `0x33cb0`
- end: `0x33dd8`
- name: `Microsoft.Crm.Metadata.EntityKeyAttributeDescription::FillPropertiesFromXml_0`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0xbc60`
- `0x18a80`
- `0x33cb0`
- `0x33e20`
- `0x33e40`
- `0x33e60`
- `0x33e80`

## string_xrefs

- `0x33cc2`: `EntityKeyAttribute XML must contain the EntityKeyAttributeId`
- `0x33cdf`: `EntityKeyAttribute XML must contain the EntityKeyid`
- `0x33cfc`: `EntityKeyAttribute XML must contain the AttributeId`

## pseudocode

```c

```

## disassembly

```asm
0x33cb0  ldarg.1
0x33cb1  ldstr    aEntitykeyattri_0// "EntityKeyAttributeId"
0x33cb6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x33cbb  ldnull
0x33cbc  ceq
0x33cbe  ldarg.2
0x33cbf  and
0x33cc0  brfalse.s loc_33CCD
0x33cc2  ldstr    aEntitykeyattri_2// "EntityKeyAttribute XML must contain the"...
0x33cc7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x33ccc  throw
0x33ccd  ldarg.1
0x33cce  ldstr    aEntitykeyid// "EntityKeyId"
0x33cd3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x33cd8  ldnull
0x33cd9  ceq
0x33cdb  ldarg.2
0x33cdc  and
0x33cdd  brfalse.s loc_33CEA
0x33cdf  ldstr    aEntitykeyattri_3// "EntityKeyAttribute XML must contain the"...
0x33ce4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x33ce9  throw
0x33cea  ldarg.1
0x33ceb  ldstr    aAttributeid// "AttributeId"
0x33cf0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x33cf5  ldnull
0x33cf6  ceq
0x33cf8  ldarg.2
0x33cf9  and
0x33cfa  brfalse.s loc_33D07
0x33cfc  ldstr    aEntitykeyattri_4// "EntityKeyAttribute XML must contain the"...
0x33d01  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x33d06  throw
0x33d07  ldarg.0
0x33d08  ldarg.1
0x33d09  ldstr    aEntitykeyattri_0// "EntityKeyAttributeId"
0x33d0e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x33d13  brfalse.s loc_33D2C
0x33d15  ldarg.1
0x33d16  ldstr    aEntitykeyattri_0// "EntityKeyAttributeId"
0x33d1b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x33d20  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x33d25  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x33d2a  br.s     loc_33D31
0x33d2c  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x33d31  callvirt instance void Microsoft.Crm.Metadata.EntityKeyAttributeDescription::set_EntityKeyAttributeId(valuetype [mscorlib]System.Guid value)
0x33d36  ldarg.1
0x33d37  ldstr    aEntitykeyid// "EntityKeyId"
0x33d3c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x33d41  brfalse.s loc_33D5E
0x33d43  ldarg.0
0x33d44  ldarg.1
0x33d45  ldstr    aEntitykeyid// "EntityKeyId"
0x33d4a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x33d4f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x33d54  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x33d59  callvirt instance void Microsoft.Crm.Metadata.EntityKeyAttributeDescription::set_EntityKeyId(valuetype [mscorlib]System.Guid value)
0x33d5e  ldarg.1
0x33d5f  ldstr    aAttributeid// "AttributeId"
0x33d64  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x33d69  brfalse.s loc_33D86
0x33d6b  ldarg.0
0x33d6c  ldarg.1
0x33d6d  ldstr    aAttributeid// "AttributeId"
0x33d72  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x33d77  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x33d7c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x33d81  callvirt instance void Microsoft.Crm.Metadata.EntityKeyAttributeDescription::set_AttributeId(valuetype [mscorlib]System.Guid value)
0x33d86  ldarg.1
0x33d87  ldstr    aIndexorder// "IndexOrder"
0x33d8c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x33d91  brfalse.s loc_33DB3
0x33d93  ldarg.0
0x33d94  ldarg.1
0x33d95  ldstr    aIndexorder// "IndexOrder"
0x33d9a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x33d9f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x33da4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x33da9  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x33dae  callvirt instance void Microsoft.Crm.Metadata.EntityKeyAttributeDescription::set_IndexOrder(int32 value)
0x33db3  ldarg.1
0x33db4  ldstr    aIsmanaged// "IsManaged"
0x33db9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x33dbe  brfalse.s loc_33DD7
0x33dc0  ldarg.0
0x33dc1  ldarg.1
0x33dc2  ldstr    aIsmanaged// "IsManaged"
0x33dc7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x33dcc  ldc.i4.0
0x33dcd  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node, bool defaultValue)
0x33dd2  callvirt instance void Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::set_IsManaged(bool value)
0x33dd7  ret
```
