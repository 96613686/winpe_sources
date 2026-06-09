# Microsoft.Crm.Metadata.AttributeDescription::FillPropertiesFromXml_0

- ea: `0x220e0`
- end: `0x2310b`
- name: `Microsoft.Crm.Metadata.AttributeDescription::FillPropertiesFromXml_0`
- size: `4139`
- prototype: ``
- caller_count: `0`
- callee_count: `107`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0xbbf0`
- `0xbc50`
- `0xbc60`
- `0xbc80`
- `0x18a80`
- `0x220e0`
- `0x23150`
- `0x23160`
- `0x23170`
- `0x23180`
- `0x23190`
- `0x231a0`
- `0x231b0`
- `0x231d0`
- `0x231f0`
- `0x23210`
- `0x23230`
- `0x23250`
- `0x23270`
- `0x23290`
- `0x232b0`
- `0x232d0`
- `0x232f0`
- `0x23310`
- `0x23330`
- `0x23350`
- `0x23370`
- `0x23390`
- `0x233b0`
- `0x233d0`
- `0x233e0`
- `0x233f0`
- `0x23410`
- `0x23430`
- `0x23450`
- `0x23470`
- `0x23490`
- `0x234b0`
- `0x234d0`
- `0x234f0`
- `0x23510`
- `0x23530`
- `0x23550`
- `0x23570`
- `0x23590`
- `0x235b0`
- `0x235d0`
- `0x235f0`
- `0x23610`
- `0x23630`

## string_xrefs

- `0x223ac`: `ValidForCreateApi`
- `0x223ba`: `ValidForCreateApi`
- `0x2230d`: `ValidForUpdateApi`
- `0x2231b`: `ValidForUpdateApi`
- `0x22389`: `ValidForReadApi`
- `0x22397`: `ValidForReadApi`
- `0x22277`: `XmlAbbreviation`
- `0x22285`: `XmlAbbreviation`
- `0x22a78`: `LinkedAttributeId`
- `0x22a85`: `LinkedAttributeId`
- `0x22a9d`: `LinkedAttributeId`
- `0x22582`: `IsIdentity`
- `0x22590`: `IsIdentity`
- `0x22c73`: `CanBeSecuredForCreate`
- `0x22c81`: `CanBeSecuredForCreate`
- `0x22c96`: `CanBeSecuredForRead`
- `0x22ca4`: `CanBeSecuredForRead`
- `0x22cb9`: `CanBeSecuredForUpdate`
- `0x22cc7`: `CanBeSecuredForUpdate`
- `0x22bb3`: `ManagedPropertyParentComponentType`
- `0x22bc1`: `ManagedPropertyParentComponentType`
- `0x22d46`: `IsRenameable`
- `0x22d54`: `IsRenameable`
- `0x2210d`: `Attribute XML must contain the attribute id`
- `0x221a2`: `Attribute XML must contain Physical Name`
- `0x22853`: `Attribute XML must contain the entity id`
- `0x2289a`: `Attribute XML must contain the AggregateOfId if AggregateOf is present`
- `0x228e1`: `Attribute XML must contain the YomiOfId if YomiOf is present`
- `0x22928`: `Attribute XML must contain the AttributeOfId if AttributeOf is present`
- `0x22992`: `Attribute XML must contain the CalculationOfId if CalculationOf is present`
- `0x229d9`: `Attribute XML must contain the ValuesFromRelationshipAttributeId if ValuesFromRelationshipAttribute is present`
- `0x22a6c`: `Attribute XML must contain the OptionSetId if OptionSetName is present`
- `0x22af7`: `Attribute XML must contain the InheritsFromId if InheritsFrom is present`
- `0x22b3e`: `Attribute XML must contain the ParentEnumAttributeId if ParentEnumAttributeName is present`

## pseudocode

```c

```

## disassembly

```asm
0x220e0  ldarg.1
0x220e1  ldstr    aNode// "node"
0x220e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x220eb  ldarg.1
0x220ec  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x220f1  ldstr    aAttributeNodeW// "Attribute node with null attributes"
0x220f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x220fb  ldarg.1
0x220fc  ldstr    aAttributeid// "AttributeId"
0x22101  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22106  ldnull
0x22107  ceq
0x22109  ldarg.2
0x2210a  and
0x2210b  brfalse.s loc_22118
0x2210d  ldstr    aAttributeXmlMu// "Attribute XML must contain the attribut"...
0x22112  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x22117  throw
0x22118  ldarg.0
0x22119  ldarg.1
0x2211a  ldstr    aAttributeid// "AttributeId"
0x2211f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22124  brfalse.s loc_2213D
0x22126  ldarg.1
0x22127  ldstr    aAttributeid// "AttributeId"
0x2212c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22131  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x22136  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2213b  br.s     loc_22142
0x2213d  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x22142  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_AttributeId(valuetype [mscorlib]System.Guid value)
0x22147  ldarg.0
0x22148  ldarg.1
0x22149  ldstr    aAttributetypei_0// "AttributeTypeId"
0x2214e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22153  brtrue.s loc_22176
0x22155  call     class Microsoft.Crm.Metadata.AttributeTypeDictionary Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x2215a  ldarg.1
0x2215b  ldstr    aType_0// "Type"
0x22160  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22165  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2216a  callvirt instance class Microsoft.Crm.Metadata.AttributeTypeInfo Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object key)
0x2216f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x22174  br.s     loc_2218B
0x22176  ldarg.1
0x22177  ldstr    aAttributetypei_0// "AttributeTypeId"
0x2217c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22181  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x22186  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2218b  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_AttributeTypeId(valuetype [mscorlib]System.Guid value)
0x22190  ldarg.1
0x22191  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x22196  ldstr    aPhysicalname// "PhysicalName"
0x2219b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x221a0  brtrue.s loc_221AD
0x221a2  ldstr    aAttributeXmlMu_0// "Attribute XML must contain Physical Nam"...
0x221a7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x221ac  throw
0x221ad  ldarg.1
0x221ae  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x221b3  ldstr    aPhysicalname// "PhysicalName"
0x221b8  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x221bd  brfalse.s loc_221DA
0x221bf  ldarg.0
0x221c0  ldarg.1
0x221c1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x221c6  ldstr    aPhysicalname// "PhysicalName"
0x221cb  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x221d0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x221d5  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_PhysicalName(string value)
0x221da  ldarg.0
0x221db  ldarg.1
0x221dc  ldstr    aName// "Name"
0x221e1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x221e6  dup
0x221e7  brtrue.s loc_221ED
0x221e9  pop
0x221ea  ldnull
0x221eb  br.s     loc_221F2
0x221ed  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x221f2  dup
0x221f3  brtrue.s loc_22201
0x221f5  pop
0x221f6  ldarg.0
0x221f7  callvirt instance string Microsoft.Crm.Metadata.AttributeDescription::get_PhysicalName()
0x221fc  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x22201  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_Name(string value)
0x22206  ldarg.1
0x22207  ldstr    aLength// "Length"
0x2220c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22211  brfalse.s loc_22253
0x22213  ldarg.0
0x22214  ldarg.1
0x22215  ldstr    aLength// "Length"
0x2221a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2221f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x22224  ldstr    aMax// "max"
0x22229  ldc.i4.5
0x2222a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2222f  brfalse.s loc_2224D
0x22231  ldarg.1
0x22232  ldstr    aLength// "Length"
0x22237  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2223c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x22241  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22246  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x2224b  br.s     loc_2224E
0x2224d  ldc.i4.m1
0x2224e  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_Length(int32 value)
0x22253  ldarg.1
0x22254  ldstr    aIsnullable// "IsNullable"
0x22259  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2225e  brfalse.s loc_22276
0x22260  ldarg.0
0x22261  ldarg.1
0x22262  ldstr    aIsnullable// "IsNullable"
0x22267  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2226c  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x22271  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_IsNullable(bool value)
0x22276  ldarg.1
0x22277  ldstr    aXmlabbreviatio_0// "XmlAbbreviation"
0x2227c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22281  brfalse.s loc_22299
0x22283  ldarg.0
0x22284  ldarg.1
0x22285  ldstr    aXmlabbreviatio_0// "XmlAbbreviation"
0x2228a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2228f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x22294  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_XmlAbbreviation(string value)
0x22299  ldarg.1
0x2229a  ldstr    aDefaultvalue// "DefaultValue"
0x2229f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x222a4  brfalse.s loc_222BC
0x222a6  ldarg.0
0x222a7  ldarg.1
0x222a8  ldstr    aDefaultvalue// "DefaultValue"
0x222ad  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x222b2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x222b7  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_DefaultValue(string value)
0x222bc  ldarg.1
0x222bd  ldstr    aUpgradedefault// "UpgradeDefaultValue"
0x222c2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x222c7  brfalse.s loc_222DF
0x222c9  ldarg.0
0x222ca  ldarg.1
0x222cb  ldstr    aUpgradedefault// "UpgradeDefaultValue"
0x222d0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x222d5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x222da  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_UpgradeDefaultValue(string value)
0x222df  ldarg.1
0x222e0  ldstr    aColumnnumber// "ColumnNumber"
0x222e5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x222ea  brfalse.s loc_2230C
0x222ec  ldarg.0
0x222ed  ldarg.1
0x222ee  ldstr    aColumnnumber// "ColumnNumber"
0x222f3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x222f8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x222fd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22302  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x22307  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_ColumnNumber(int32 value)
0x2230c  ldarg.1
0x2230d  ldstr    aValidforupdate// "ValidForUpdateApi"
0x22312  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22317  brfalse.s loc_2232F
0x22319  ldarg.0
0x2231a  ldarg.1
0x2231b  ldstr    aValidforupdate// "ValidForUpdateApi"
0x22320  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22325  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x2232a  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_ValidForUpdateApi(bool value)
0x2232f  ldarg.1
0x22330  ldstr    aLogicalname// "LogicalName"
0x22335  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2233a  brfalse.s loc_22354
0x2233c  ldarg.0
0x2233d  ldarg.1
0x2233e  ldstr    aLogicalname// "LogicalName"
0x22343  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22348  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2234d  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_LogicalName(string value)
0x22352  br.s     loc_22365
0x22354  ldarg.0
0x22355  ldarg.0
0x22356  callvirt instance string Microsoft.Crm.Metadata.AttributeDescription::get_Name()
0x2235b  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x22360  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_LogicalName(string value)
0x22365  ldarg.1
0x22366  ldstr    aExternalname// "ExternalName"
0x2236b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22370  brfalse.s loc_22388
0x22372  ldarg.0
0x22373  ldarg.1
0x22374  ldstr    aExternalname// "ExternalName"
0x22379  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2237e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x22383  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_ExternalName(string value)
0x22388  ldarg.1
0x22389  ldstr    aValidforreadap// "ValidForReadApi"
0x2238e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22393  brfalse.s loc_223AB
0x22395  ldarg.0
0x22396  ldarg.1
0x22397  ldstr    aValidforreadap// "ValidForReadApi"
0x2239c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x223a1  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x223a6  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_ValidForReadApi(bool value)
0x223ab  ldarg.1
0x223ac  ldstr    aValidforcreate// "ValidForCreateApi"
0x223b1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x223b6  brfalse.s loc_223CE
0x223b8  ldarg.0
0x223b9  ldarg.1
0x223ba  ldstr    aValidforcreate// "ValidForCreateApi"
0x223bf  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x223c4  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x223c9  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_ValidForCreateApi(bool value)
0x223ce  ldarg.1
0x223cf  ldstr    aVisibletoplatf// "VisibleToPlatform"
0x223d4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x223d9  brfalse.s loc_223F1
0x223db  ldarg.0
0x223dc  ldarg.1
0x223dd  ldstr    aVisibletoplatf// "VisibleToPlatform"
0x223e2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x223e7  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x223ec  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_VisibleToPlatform(bool value)
0x223f1  ldarg.1
0x223f2  ldstr    aIspkattribute// "IsPKAttribute"
0x223f7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x223fc  brfalse.s loc_22414
0x223fe  ldarg.0
0x223ff  ldarg.1
0x22400  ldstr    aIspkattribute// "IsPKAttribute"
0x22405  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2240a  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x2240f  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_IsPKAttribute(bool value)
0x22414  ldarg.1
0x22415  ldstr    aAutonumberform// "AutoNumberFormat"
0x2241a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2241f  brfalse.s loc_22437
0x22421  ldarg.0
0x22422  ldarg.1
0x22423  ldstr    aAutonumberform// "AutoNumberFormat"
0x22428  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2242d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x22432  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_AutoNumberFormat(string value)
0x22437  ldarg.1
0x22438  ldstr    aIscustomfield// "IsCustomField"
0x2243d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22442  brfalse.s loc_2245A
0x22444  ldarg.0
0x22445  ldarg.1
0x22446  ldstr    aIscustomfield// "IsCustomField"
0x2244b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22450  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x22455  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_IsCustomField(bool value)
0x2245a  ldarg.1
0x2245b  ldstr    aIslogical// "IsLogical"
0x22460  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22465  brfalse.s loc_2247D
0x22467  ldarg.0
0x22468  ldarg.1
0x22469  ldstr    aIslogical// "IsLogical"
0x2246e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22473  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x22478  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_IsLogical(bool value)
0x2247d  ldarg.1
0x2247e  ldstr    aDisplaymask// "DisplayMask"
0x22483  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x22488  brfalse.s loc_224AF
0x2248a  ldarg.0
0x2248b  ldtoken  Microsoft.Crm.Metadata.DisplayMasks
0x22490  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22495  ldarg.1
0x22496  ldstr    aDisplaymask// "DisplayMask"
0x2249b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x224a0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x224a5  call     int32 Microsoft.Crm.Platform.ConvertHelper::EnumFromXmlString(class [mscorlib]System.Type enumType, string mask)
0x224aa  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32 value)
0x224af  ldarg.1
0x224b0  ldstr    aEntityid// "EntityId"
0x224b5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x224ba  brfalse.s loc_224D7
0x224bc  ldarg.0
0x224bd  ldarg.1
0x224be  ldstr    aEntityid// "EntityId"
0x224c3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x224c8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x224cd  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x224d2  callvirt instance void Microsoft.Crm.Metadata.AttributeDescription::set_EntityId(valuetype [mscorlib]System.Guid value)
0x224d7  ldarg.1
0x224d8  ldstr    aReferencedenti// "ReferencedEntityObjectTypeCode"
0x224dd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x224e2  brfalse.s loc_22504
0x224e4  ldarg.0
0x224e5  ldarg.1
0x224e6  ldstr    aReferencedenti// "ReferencedEntityObjectTypeCode"
0x224eb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x224f0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
  ... truncated ...
```
