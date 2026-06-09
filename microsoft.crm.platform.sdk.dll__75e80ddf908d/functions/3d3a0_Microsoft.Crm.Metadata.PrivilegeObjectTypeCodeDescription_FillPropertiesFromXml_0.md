# Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::FillPropertiesFromXml_0

- ea: `0x3d3a0`
- end: `0x3d495`
- name: `Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::FillPropertiesFromXml_0`
- size: `245`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0xbc60`
- `0xbc80`
- `0x18a80`
- `0x3d3a0`
- `0x3d4f0`
- `0x3d510`
- `0x3d530`
- `0x3d590`

## string_xrefs

- `0x3d3d0`: `PrivilegeId`
- `0x3d3ee`: `PrivilegeId`
- `0x3d3fb`: `PrivilegeId`
- `0x3d3a2`: `PrivilegeObjectTypeCodeId`
- `0x3d3af`: `PrivilegeObjectTypeCodeId`
- `0x3d3e1`: `PrivilegeObjectTypeCode XML requires the privilege id`

## pseudocode

```c

```

## disassembly

```asm
0x3d3a0  ldarg.0
0x3d3a1  ldarg.1
0x3d3a2  ldstr    aPrivilegeobjec_1// "PrivilegeObjectTypeCodeId"
0x3d3a7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d3ac  brfalse.s loc_3D3C5
0x3d3ae  ldarg.1
0x3d3af  ldstr    aPrivilegeobjec_1// "PrivilegeObjectTypeCodeId"
0x3d3b4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d3b9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3d3be  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3d3c3  br.s     loc_3D3CA
0x3d3c5  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3d3ca  callvirt instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::set_PrivilegeObjectTypeCodeId(valuetype [mscorlib]System.Guid value)
0x3d3cf  ldarg.1
0x3d3d0  ldstr    aPrivilegeid_0// "PrivilegeId"
0x3d3d5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d3da  ldnull
0x3d3db  ceq
0x3d3dd  ldarg.2
0x3d3de  and
0x3d3df  brfalse.s loc_3D3EC
0x3d3e1  ldstr    aPrivilegeobjec_2// "PrivilegeObjectTypeCode XML requires th"...
0x3d3e6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3d3eb  throw
0x3d3ec  ldarg.0
0x3d3ed  ldarg.1
0x3d3ee  ldstr    aPrivilegeid_0// "PrivilegeId"
0x3d3f3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d3f8  brfalse.s loc_3D411
0x3d3fa  ldarg.1
0x3d3fb  ldstr    aPrivilegeid_0// "PrivilegeId"
0x3d400  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d405  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3d40a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3d40f  br.s     loc_3D416
0x3d411  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3d416  callvirt instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::set_PrivilegeId(valuetype [mscorlib]System.Guid value)
0x3d41b  ldarg.1
0x3d41c  ldstr    aObjecttypecode// "ObjectTypeCode"
0x3d421  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d426  brfalse.s loc_3D448
0x3d428  ldarg.0
0x3d429  ldarg.1
0x3d42a  ldstr    aObjecttypecode// "ObjectTypeCode"
0x3d42f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d434  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3d439  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3d43e  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3d443  callvirt instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::set_ObjectTypeCode(int32 value)
0x3d448  ldarg.1
0x3d449  ldstr    aIsmanaged// "IsManaged"
0x3d44e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d453  brfalse.s loc_3D46C
0x3d455  ldarg.0
0x3d456  ldarg.1
0x3d457  ldstr    aIsmanaged// "IsManaged"
0x3d45c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d461  ldc.i4.0
0x3d462  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node, bool defaultValue)
0x3d467  callvirt instance void Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::set_IsManaged(bool value)
0x3d46c  ldarg.1
0x3d46d  ldstr    aIntroducedvers// "IntroducedVersion"
0x3d472  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d477  brfalse.s loc_3D494
0x3d479  ldarg.0
0x3d47a  ldarg.1
0x3d47b  ldstr    aIntroducedvers// "IntroducedVersion"
0x3d480  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d485  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3d48a  call     class [mscorlib]System.Version Microsoft.Crm.Platform.ConvertHelper::ToVersionFromString(string value)
0x3d48f  callvirt instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::set_IntroducedVersion(class [mscorlib]System.Version value)
0x3d494  ret
```
