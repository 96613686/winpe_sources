# Microsoft.Crm.Metadata.SavedQueryHelper::GenerateFetchXml

- ea: `0x5d1a0`
- end: `0x5d42a`
- name: `Microsoft.Crm.Metadata.SavedQueryHelper::GenerateFetchXml`
- size: `650`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x5c6e0`

## callees

- `0x18490`
- `0x29450`
- `0x29460`
- `0x2cb70`
- `0x2cd30`
- `0x2cd70`
- `0x2d1b0`
- `0x2d530`
- `0x5d170`
- `0x5d1a0`
- `0x5d430`

## string_xrefs

- `0x5d2b7`: `createdon`
- `0x5d3c2`: `processid`

## pseudocode

```c

```

## disassembly

```asm
0x5d1a0  ldarg.0
0x5d1a1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x5d1a6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_LogicalName()
0x5d1ab  stloc.0
0x5d1ac  ldarg.0
0x5d1ad  callvirt instance class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryField()
0x5d1b2  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x5d1b7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5d1bc  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x5d1c1  stloc.1
0x5d1c2  ldloc.0
0x5d1c3  ldarg.0
0x5d1c4  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsActivity()
0x5d1c9  ldarg.0
0x5d1ca  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsBPFEntity()
0x5d1cf  call     string Microsoft.Crm.Metadata.SavedQueryHelper::GetPrimaryKeyName(string entityName, bool isActivity, [opt] bool isBpfEntity)
0x5d1d4  stloc.2
0x5d1d5  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument()
0x5d1da  stloc.3
0x5d1db  ldloc.3
0x5d1dc  ldstr    aFetch// "fetch"
0x5d1e1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d1e6  stloc.s  4
0x5d1e8  ldloc.s  4
0x5d1ea  ldstr    aVersion// "version"
0x5d1ef  ldstr    a10// "1.0"
0x5d1f4  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d1f9  ldloc.s  4
0x5d1fb  ldstr    aMapping// "mapping"
0x5d200  ldstr    aLogical// "logical"
0x5d205  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d20a  ldarg.2
0x5d20b  brfalse.s loc_5D21E
0x5d20d  ldloc.s  4
0x5d20f  ldstr    aDistinct// "distinct"
0x5d214  ldstr    aTrue// "true"
0x5d219  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d21e  ldloc.3
0x5d21f  ldstr    aEntity// "entity"
0x5d224  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d229  stloc.s  5
0x5d22b  ldloc.s  5
0x5d22d  ldstr    aName// "name"
0x5d232  ldloc.0
0x5d233  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d238  ldloc.s  4
0x5d23a  ldloc.s  5
0x5d23c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d241  pop
0x5d242  ldloc.3
0x5d243  ldstr    aAttribute_0// "attribute"
0x5d248  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d24d  stloc.s  6
0x5d24f  ldloc.s  6
0x5d251  ldstr    aName// "name"
0x5d256  ldloc.2
0x5d257  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d25c  ldloc.s  5
0x5d25e  ldloc.s  6
0x5d260  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d265  pop
0x5d266  ldloc.3
0x5d267  ldstr    aAttribute_0// "attribute"
0x5d26c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d271  stloc.s  7
0x5d273  ldloc.s  7
0x5d275  ldstr    aName// "name"
0x5d27a  ldloc.1
0x5d27b  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d280  ldloc.s  5
0x5d282  ldloc.s  7
0x5d284  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d289  pop
0x5d28a  ldarg.0
0x5d28b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.EntityCreateInfo::get_DataProviderId()
0x5d290  stloc.s  9
0x5d292  ldloca.s 9
0x5d294  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x5d299  brfalse.s loc_5D2A3
0x5d29b  ldloc.s  4
0x5d29d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x5d2a2  ret
0x5d2a3  ldloc.3
0x5d2a4  ldstr    aAttribute_0// "attribute"
0x5d2a9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d2ae  stloc.s  8
0x5d2b0  ldloc.s  8
0x5d2b2  ldstr    aName// "name"
0x5d2b7  ldstr    aCreatedon// "createdon"
0x5d2bc  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d2c1  ldloc.s  5
0x5d2c3  ldloc.s  8
0x5d2c5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d2ca  pop
0x5d2cb  ldarg.0
0x5d2cc  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsBPFEntity()
0x5d2d1  brfalse  loc_5D3D6
0x5d2d6  ldarg.3
0x5d2d7  brfalse  loc_5D3D6
0x5d2dc  ldloc.3
0x5d2dd  ldstr    aAttribute_0// "attribute"
0x5d2e2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d2e7  stloc.s  0xA
0x5d2e9  ldloc.s  0xA
0x5d2eb  ldstr    aName// "name"
0x5d2f0  ldarg.3
0x5d2f1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x5d2f6  call     string Microsoft.Crm.Metadata.BusinessProcessFlowEntityBuilder::GetCustomBPFEntityColumnName(string entityLogicalName)
0x5d2fb  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d300  ldloc.s  5
0x5d302  ldloc.s  0xA
0x5d304  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d309  pop
0x5d30a  ldloc.3
0x5d30b  ldstr    aAttribute_0// "attribute"
0x5d310  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d315  stloc.s  0xB
0x5d317  ldloc.s  0xB
0x5d319  ldstr    aName// "name"
0x5d31e  ldstr    aActivestageid_0// "activestageid"
0x5d323  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d328  ldloc.s  5
0x5d32a  ldloc.s  0xB
0x5d32c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d331  pop
0x5d332  ldloc.3
0x5d333  ldstr    aAttribute_0// "attribute"
0x5d338  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d33d  stloc.s  0xC
0x5d33f  ldloc.s  0xC
0x5d341  ldstr    aName// "name"
0x5d346  ldstr    aStatecode_1// "statecode"
0x5d34b  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d350  ldloc.s  5
0x5d352  ldloc.s  0xC
0x5d354  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d359  pop
0x5d35a  ldloc.3
0x5d35b  ldstr    aAttribute_0// "attribute"
0x5d360  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d365  stloc.s  0xD
0x5d367  ldloc.s  0xD
0x5d369  ldstr    aName// "name"
0x5d36e  ldstr    aStatuscode// "statuscode"
0x5d373  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d378  ldloc.s  5
0x5d37a  ldloc.s  0xD
0x5d37c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d381  pop
0x5d382  ldarg.1
0x5d383  ldc.i4.2
0x5d384  bne.un.s loc_5D3AE
0x5d386  ldloc.3
0x5d387  ldstr    aAttribute_0// "attribute"
0x5d38c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d391  stloc.s  0xF
0x5d393  ldloc.s  0xF
0x5d395  ldstr    aName// "name"
0x5d39a  call     string Microsoft.Crm.Metadata.BusinessProcessFlowEntityBuilder::GetCustomBPFEntityDurationColumnName()
0x5d39f  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d3a4  ldloc.s  5
0x5d3a6  ldloc.s  0xF
0x5d3a8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d3ad  pop
0x5d3ae  ldloc.3
0x5d3af  ldstr    aAttribute_0// "attribute"
0x5d3b4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d3b9  stloc.s  0xE
0x5d3bb  ldloc.s  0xE
0x5d3bd  ldstr    aName// "name"
0x5d3c2  ldstr    aProcessid_0// "processid"
0x5d3c7  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d3cc  ldloc.s  5
0x5d3ce  ldloc.s  0xE
0x5d3d0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d3d5  pop
0x5d3d6  ldarg.1
0x5d3d7  ldc.i4.7
0x5d3d8  beq.s    loc_5D40F
0x5d3da  ldloc.3
0x5d3db  ldstr    aOrder// "order"
0x5d3e0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d3e5  stloc.s  0x10
0x5d3e7  ldloc.s  0x10
0x5d3e9  ldstr    aAttribute_0// "attribute"
0x5d3ee  ldloc.1
0x5d3ef  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d3f4  ldloc.s  0x10
0x5d3f6  ldstr    aDescending// "descending"
0x5d3fb  ldstr    aFalse// "false"
0x5d400  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d405  ldloc.s  5
0x5d407  ldloc.s  0x10
0x5d409  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d40e  pop
0x5d40f  ldloc.3
0x5d410  ldarg.1
0x5d411  ldloc.1
0x5d412  ldloc.s  5
0x5d414  ldarg.0
0x5d415  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsActivity()
0x5d41a  ldarg.3
0x5d41b  ldarg.s  4
0x5d41d  call     void Microsoft.Crm.Metadata.SavedQueryHelper::GenerateFilter(class [System.Xml]System.Xml.XmlDocument xmlDom, valuetype SystemViewType view, string primaryAttributeName, class [System.Xml]System.Xml.XmlElement entityElement, bool isActivity, [opt] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata bpfPrimaryEntity, [opt] bool isBPFSpecificView)
0x5d422  ldloc.s  4
0x5d424  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x5d429  ret
```
