# Microsoft.Crm.Application.CellDescriptor::GenerateSubGridControlNode

- ea: `0x182f0`
- end: `0x18563`
- name: `Microsoft.Crm.Application.CellDescriptor::GenerateSubGridControlNode`
- size: `627`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x17590`
- `0x17960`
- `0x179a0`

## callees

- `0x182f0`
- `0x18570`
- `0x1f7e0`
- `0x2fb90`
- `0x336b0`

## string_xrefs

- `0x18340`: `classid`
- `0x18534`: `CustomControlXmlParam`

## pseudocode

```c

```

## disassembly

```asm
0x182f0  ldarg.1
0x182f1  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x182f6  ldstr    aControl// "control"
0x182fb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x18300  stloc.0
0x18301  ldarg.1
0x18302  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x18307  ldstr    aId// "id"
0x1830c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x18311  stloc.1
0x18312  ldloc.1
0x18313  ldarg.1
0x18314  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x18319  ldstr    aId// "id"
0x1831e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x18323  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x18328  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x1832d  ldloc.0
0x1832e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x18333  ldloc.1
0x18334  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x18339  pop
0x1833a  ldarg.1
0x1833b  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x18340  ldstr    aClassid// "classid"
0x18345  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x1834a  stloc.2
0x1834b  ldloc.2
0x1834c  ldstr    aE7a8127886354d// "{E7A81278-8635-4D9E-8D4D-59480B391C5B}"
0x18351  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x18356  ldloc.0
0x18357  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1835c  ldloc.2
0x1835d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x18362  pop
0x18363  ldarg.s  4
0x18365  brtrue.s loc_183A3
0x18367  ldarg.1
0x18368  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x1836d  ldstr    aUniqueid// "uniqueid"
0x18372  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x18377  stloc.s  6
0x18379  ldloc.s  6
0x1837b  ldarg.1
0x1837c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x18381  ldstr    aUniqueid// "uniqueid"
0x18386  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1838b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x18390  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x18395  ldloc.0
0x18396  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1839b  ldloc.s  6
0x1839d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x183a2  pop
0x183a3  ldnull
0x183a4  stloc.3
0x183a5  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x183aa  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x183af  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlSolutionExport()
0x183b4  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x183b9  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x183be  brfalse.s loc_183F5
0x183c0  ldarg.1
0x183c1  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x183c6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x183cb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x183d0  ldstr    aControldescrip_2// "//controlDescription[@forControl='{0}']"...
0x183d5  ldc.i4.2
0x183d6  newarr   [mscorlib]System.Object
0x183db  dup
0x183dc  ldc.i4.0
0x183dd  ldarg.3
0x183de  stelem.ref
0x183df  dup
0x183e0  ldc.i4.1
0x183e1  ldc.i4.2
0x183e2  box      [mscorlib]System.Int32
0x183e7  stelem.ref
0x183e8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x183ed  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x183f2  stloc.3
0x183f3  br.s     loc_18428
0x183f5  ldarg.1
0x183f6  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x183fb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x18400  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18405  ldstr    aControldescrip_2// "//controlDescription[@forControl='{0}']"...
0x1840a  ldc.i4.2
0x1840b  newarr   [mscorlib]System.Object
0x18410  dup
0x18411  ldc.i4.0
0x18412  ldarg.3
0x18413  stelem.ref
0x18414  dup
0x18415  ldc.i4.1
0x18416  ldc.i4.1
0x18417  box      [mscorlib]System.Int32
0x1841c  stelem.ref
0x1841d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18422  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x18427  stloc.3
0x18428  ldnull
0x18429  stloc.s  4
0x1842b  ldarg.0
0x1842c  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_Context()
0x18431  call     bool Microsoft.Crm.Application.Utility.DataSetControlUtility::IsDataSetControlFCBEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x18436  brfalse.s loc_18462
0x18438  ldloc.3
0x18439  brfalse.s loc_18462
0x1843b  ldloc.3
0x1843c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x18441  brfalse.s loc_18462
0x18443  ldloc.3
0x18444  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x18449  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x1844e  ldstr    aCustomcontrol_0// "customControl"
0x18453  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18458  brfalse.s loc_18462
0x1845a  ldloc.3
0x1845b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x18460  stloc.s  4
0x18462  ldarg.s  4
0x18464  brfalse.s loc_18474
0x18466  ldloc.3
0x18467  ldc.i4.1
0x18468  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::CloneNode(bool)
0x1846d  stloc.s  5
0x1846f  br       loc_18558
0x18474  ldloc.3
0x18475  ldstr    aDataSet// "./data-set"
0x1847a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1847f  stloc.3
0x18480  ldarg.1
0x18481  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x18486  ldstr    aParameters// "parameters"
0x1848b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x18490  stloc.s  5
0x18492  ldarg.0
0x18493  ldloc.3
0x18494  ldloc.s  5
0x18496  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1849b  dup
0x1849c  ldstr    aViewid_0// "ViewId"
0x184a1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x184a6  dup
0x184a7  ldstr    aIsuserview// "IsUserView"
0x184ac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x184b1  dup
0x184b2  ldstr    aTargetentityty// "TargetEntityType"
0x184b7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x184bc  dup
0x184bd  ldstr    aRelationshipna// "RelationshipName"
0x184c2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x184c7  dup
0x184c8  ldstr    aRelationshipro// "RelationshipRoleOrdinal"
0x184cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x184d2  call     instance void Microsoft.Crm.Application.CellDescriptor::CloneParameters(class [System.Xml]System.Xml.XmlNode fromNode, class [System.Xml]System.Xml.XmlNode toNode, class [mscorlib]System.Collections.Generic.ICollection`1<string> filterParameterNodes)
0x184d7  ldarg.1
0x184d8  ldstr    aParameters// "parameters"
0x184dd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x184e2  stloc.s  7
0x184e4  ldarg.0
0x184e5  ldloc.s  7
0x184e7  ldloc.s  5
0x184e9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x184ee  dup
0x184ef  ldstr    aEnablequickfin// "EnableQuickFind"
0x184f4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x184f9  dup
0x184fa  ldstr    aEnableviewpick// "EnableViewPicker"
0x184ff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x18504  dup
0x18505  ldstr    aEnablejumpbar// "EnableJumpBar"
0x1850a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1850f  dup
0x18510  ldstr    aEnablechartpic// "EnableChartPicker"
0x18515  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1851a  dup
0x1851b  ldstr    aRecordsperpage// "RecordsPerPage"
0x18520  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x18525  call     instance void Microsoft.Crm.Application.CellDescriptor::CloneParameters(class [System.Xml]System.Xml.XmlNode fromNode, class [System.Xml]System.Xml.XmlNode toNode, class [mscorlib]System.Collections.Generic.ICollection`1<string> filterParameterNodes)
0x1852a  ldloc.s  4
0x1852c  brfalse.s loc_18558
0x1852e  ldarg.1
0x1852f  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x18534  ldstr    aCustomcontrolx// "CustomControlXmlParam"
0x18539  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x1853e  stloc.s  8
0x18540  ldloc.s  8
0x18542  ldloc.s  4
0x18544  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x18549  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x1854e  ldloc.s  5
0x18550  ldloc.s  8
0x18552  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x18557  pop
0x18558  ldloc.0
0x18559  ldloc.s  5
0x1855b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x18560  pop
0x18561  ldloc.0
0x18562  ret
```
