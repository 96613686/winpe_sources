# Microsoft.Crm.Application.CellDescriptor::GenerateControlNode

- ea: `0x17b10`
- end: `0x17f12`
- name: `Microsoft.Crm.Application.CellDescriptor::GenerateControlNode`
- size: `1026`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x17590`
- `0x17960`
- `0x179a0`

## callees

- `0x174d0`
- `0x17b10`
- `0x17f20`
- `0x2fb90`
- `0x47970`
- `0x4b5a0`

## string_xrefs

- `0x17d5a`: `classid`
- `0x17e01`: `classid`
- `0x17ebb`: `classid`
- `0x17b89`: `formDescriptor`
- `0x17b9b`: `mainDescriptor`

## pseudocode

```c

```

## disassembly

```asm
0x17b10  ldarg.1
0x17b11  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x17b16  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x17b1b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17b20  ldstr    aControldescrip_1// "//controlDescription[@forControl='{0}']"
0x17b25  ldc.i4.1
0x17b26  newarr   [mscorlib]System.Object
0x17b2b  dup
0x17b2c  ldc.i4.0
0x17b2d  ldarg.3
0x17b2e  stelem.ref
0x17b2f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17b34  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17b39  stloc.0
0x17b3a  ldnull
0x17b3b  stloc.1
0x17b3c  ldarg.s  4
0x17b3e  brfalse.s loc_17B61
0x17b40  ldloc.0
0x17b41  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17b46  ldstr    aCustomcontrolP_0// "customControl/parameters/{0}"
0x17b4b  ldc.i4.1
0x17b4c  newarr   [mscorlib]System.Object
0x17b51  dup
0x17b52  ldc.i4.0
0x17b53  ldarg.s  4
0x17b55  stelem.ref
0x17b56  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17b5b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17b60  stloc.1
0x17b61  ldnull
0x17b62  stloc.2
0x17b63  ldloc.1
0x17b64  brfalse.s loc_17B72
0x17b66  ldloc.1
0x17b67  ldstr    aBindattribute// "BindAttribute"
0x17b6c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17b71  stloc.2
0x17b72  ldnull
0x17b73  stloc.3
0x17b74  ldloc.2
0x17b75  brfalse.s loc_17B80
0x17b77  ldloc.2
0x17b78  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x17b7d  stloc.3
0x17b7e  br.s     loc_17BB7
0x17b80  ldloc.1
0x17b81  brfalse.s loc_17BB7
0x17b83  ldloc.1
0x17b84  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x17b89  ldstr    aFormdescriptor// "formDescriptor"
0x17b8e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17b93  brtrue.s loc_17BA7
0x17b95  ldloc.1
0x17b96  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x17b9b  ldstr    aMaindescriptor// "mainDescriptor"
0x17ba0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17ba5  brfalse.s loc_17BB0
0x17ba7  ldloc.1
0x17ba8  call     string Microsoft.Crm.Application.Utility.FormDescriptorUtility::GetFormId(class [System.Xml]System.Xml.XmlNode childNode)
0x17bad  stloc.3
0x17bae  br.s     loc_17BB7
0x17bb0  ldloc.1
0x17bb1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x17bb6  stloc.3
0x17bb7  ldnull
0x17bb8  stloc.s  4
0x17bba  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x17bbf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x17bc4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlSolutionExport()
0x17bc9  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17bce  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17bd3  brfalse.s loc_17BFD
0x17bd5  ldloc.0
0x17bd6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17bdb  ldstr    aCustomcontrolF_1// "customControl[@formFactor='{0}']//param"...
0x17be0  ldc.i4.1
0x17be1  newarr   [mscorlib]System.Object
0x17be6  dup
0x17be7  ldc.i4.0
0x17be8  ldc.i4.2
0x17be9  box      [mscorlib]System.Int32
0x17bee  stelem.ref
0x17bef  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17bf4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17bf9  stloc.s  4
0x17bfb  br.s     loc_17C23
0x17bfd  ldloc.0
0x17bfe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17c03  ldstr    aCustomcontrolF_1// "customControl[@formFactor='{0}']//param"...
0x17c08  ldc.i4.1
0x17c09  newarr   [mscorlib]System.Object
0x17c0e  dup
0x17c0f  ldc.i4.0
0x17c10  ldc.i4.1
0x17c11  box      [mscorlib]System.Int32
0x17c16  stelem.ref
0x17c17  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17c1c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17c21  stloc.s  4
0x17c23  ldarg.1
0x17c24  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x17c29  ldstr    aControl// "control"
0x17c2e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x17c33  stloc.s  5
0x17c35  ldarg.1
0x17c36  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x17c3b  ldstr    aId// "id"
0x17c40  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x17c45  stloc.s  6
0x17c47  ldloc.s  6
0x17c49  ldarg.1
0x17c4a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17c4f  ldstr    aId// "id"
0x17c54  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17c59  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x17c5e  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x17c63  ldloc.s  5
0x17c65  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17c6a  ldloc.s  6
0x17c6c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x17c71  pop
0x17c72  ldarg.s  6
0x17c74  brtrue.s loc_17CB3
0x17c76  ldarg.1
0x17c77  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x17c7c  ldstr    aUniqueid// "uniqueid"
0x17c81  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x17c86  stloc.s  7
0x17c88  ldloc.s  7
0x17c8a  ldarg.1
0x17c8b  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17c90  ldstr    aUniqueid// "uniqueid"
0x17c95  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17c9a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x17c9f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x17ca4  ldloc.s  5
0x17ca6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17cab  ldloc.s  7
0x17cad  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x17cb2  pop
0x17cb3  ldarg.1
0x17cb4  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17cb9  ldstr    aDisabled// "disabled"
0x17cbe  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17cc3  brfalse.s loc_17D02
0x17cc5  ldarg.1
0x17cc6  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x17ccb  ldstr    aDisabled// "disabled"
0x17cd0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x17cd5  stloc.s  8
0x17cd7  ldloc.s  8
0x17cd9  ldarg.1
0x17cda  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17cdf  ldstr    aDisabled// "disabled"
0x17ce4  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17ce9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x17cee  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x17cf3  ldloc.s  5
0x17cf5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17cfa  ldloc.s  8
0x17cfc  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x17d01  pop
0x17d02  ldarg.s  6
0x17d04  brfalse.s loc_17D43
0x17d06  ldloc.s  4
0x17d08  stloc.s  9
0x17d0a  ldloc.s  9
0x17d0c  brfalse.s loc_17D43
0x17d0e  ldloc.s  9
0x17d10  ldc.i4.1
0x17d11  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::CloneNode(bool)
0x17d16  stloc.s  0xA
0x17d18  ldloc.s  0xA
0x17d1a  ldstr    aDatafieldname// "datafieldname"
0x17d1f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17d24  stloc.s  0xB
0x17d26  ldloc.s  0xB
0x17d28  brfalse.s loc_17D39
0x17d2a  ldloc.s  0xB
0x17d2c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x17d31  ldloc.s  0xB
0x17d33  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x17d38  pop
0x17d39  ldloc.s  5
0x17d3b  ldloc.s  0xA
0x17d3d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x17d42  pop
0x17d43  ldloc.3
0x17d44  brfalse  loc_17EB5
0x17d49  ldarg.0
0x17d4a  call     instance bool Microsoft.Crm.Application.CellDescriptor::IsMDDControl()
0x17d4f  brfalse  loc_17DF1
0x17d54  ldarg.1
0x17d55  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x17d5a  ldstr    aClassid// "classid"
0x17d5f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x17d64  stloc.s  0xC
0x17d66  ldloc.1
0x17d67  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17d6c  ldstr    aType// "type"
0x17d71  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17d76  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x17d7b  stloc.s  0xD
0x17d7d  ldarg.0
0x17d7e  ldloc.s  0xD
0x17d80  call     instance valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ControlType Microsoft.Crm.Application.CellDescriptor::GetControlTypeFromCustomControlManifestType(string propertyType)
0x17d85  stloc.s  0xE
0x17d87  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ControlType, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormControl> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormControlList::FormControlByType
0x17d8c  ldloc.s  0xE
0x17d8e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ControlType, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormControl>::get_Item(void)
0x17d93  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormControl::get_Id()
0x17d98  stloc.s  0xF
0x17d9a  ldloc.s  0xC
0x17d9c  ldloc.s  0xF
0x17d9e  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x17da3  ldloc.s  5
0x17da5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17daa  ldloc.s  0xC
0x17dac  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x17db1  pop
0x17db2  ldarg.1
0x17db3  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x17db8  ldstr    aIsunbound// "isunbound"
0x17dbd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x17dc2  stloc.s  0x10
0x17dc4  ldloc.s  0x10
0x17dc6  ldstr    aTrue// "true"
0x17dcb  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x17dd0  ldloc.s  5
0x17dd2  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17dd7  ldloc.s  0x10
0x17dd9  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x17dde  pop
0x17ddf  ldloc.s  5
0x17de1  ldarg.1
0x17de2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x17de7  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x17dec  br       loc_17F0F
0x17df1  ldarg.s  5
0x17df3  ldloc.3
0x17df4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x17df9  stloc.s  0x11
0x17dfb  ldarg.1
0x17dfc  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x17e01  ldstr    aClassid// "classid"
0x17e06  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x17e0b  stloc.s  0x12
0x17e0d  ldloc.0
0x17e0e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17e13  ldstr    aCustomcontrolF// "customControl[@formFactor='{0}']"
0x17e18  ldc.i4.1
0x17e19  newarr   [mscorlib]System.Object
0x17e1e  dup
0x17e1f  ldc.i4.0
0x17e20  ldc.i4.2
0x17e21  box      [mscorlib]System.Int32
0x17e26  stelem.ref
0x17e27  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17e2c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17e31  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17e36  ldstr    aId// "id"
0x17e3b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17e40  stloc.s  0x13
0x17e42  ldloc.s  0x13
0x17e44  brtrue.s loc_17E67
0x17e46  ldloc.s  0x12
0x17e48  ldloc.s  0x11
0x17e4a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x17e4f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x17e54  ldloc.s  0x11
0x17e56  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x17e5b  call     string Microsoft.Crm.Application.Utility.Util::GetControlClassId(string dataType, string format)
0x17e60  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x17e65  br.s     loc_17E75
0x17e67  ldloc.s  0x12
0x17e69  ldloc.s  0x13
0x17e6b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x17e70  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x17e75  ldloc.s  5
0x17e77  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17e7c  ldloc.s  0x12
0x17e7e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x17e83  pop
0x17e84  ldarg.1
0x17e85  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x17e8a  ldstr    aDatafieldname// "datafieldname"
0x17e8f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x17e94  stloc.s  0x14
0x17e96  ldloc.s  0x14
0x17e98  ldloc.s  0x11
0x17e9a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x17e9f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x17ea4  ldloc.s  5
0x17ea6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17eab  ldloc.s  0x14
0x17ead  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x17eb2  pop
0x17eb3  br.s     loc_17F0F
0x17eb5  ldarg.1
  ... truncated ...
```
