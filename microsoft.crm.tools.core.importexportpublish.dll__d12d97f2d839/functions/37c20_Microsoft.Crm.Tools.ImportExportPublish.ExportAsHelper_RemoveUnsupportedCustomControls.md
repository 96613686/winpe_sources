# Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::RemoveUnsupportedCustomControls

- ea: `0x37c20`
- end: `0x37fc7`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::RemoveUnsupportedCustomControls`
- size: `935`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x2cba0`
- `0x32880`
- `0x3c090`

## callees

- `0x37be0`
- `0x37c20`
- `0x38280`
- `0x38380`
- `0x3a780`

## string_xrefs

- `0x37f1d`: `classid`
- `0x37e2b`: `//control[translate(@classid, 'abcdefghijklmnopqrstuvwxyz', 'ABCDEFGHIJKLMNOPQRSTUVWXYZ')='{`
- `0x37df7`: `FormXML`

## pseudocode

```c

```

## disassembly

```asm
0x37c20  ldarg.0
0x37c21  brfalse  loc_37FC6
0x37c26  ldnull
0x37c27  stloc.0
0x37c28  ldarg.3
0x37c29  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_TargetVersion()
0x37c2e  ldsfld   class [mscorlib]System.Version [Microsoft.Crm]Microsoft.Crm.CrmVersions::AraVersion
0x37c33  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x37c38  brfalse.s loc_37C42
0x37c3a  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::GetAraCustomControlsList()
0x37c3f  stloc.0
0x37c40  br.s     loc_37C5A
0x37c42  ldarg.3
0x37c43  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_TargetVersion()
0x37c48  ldsfld   class [mscorlib]System.Version [Microsoft.Crm]Microsoft.Crm.CrmVersions::NaosVersion
0x37c4d  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x37c52  brfalse.s loc_37C5A
0x37c54  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::GetNaosSupportedCustomControlsList()
0x37c59  stloc.0
0x37c5a  ldarg.0
0x37c5b  ldstr    aControldescrip_2// "//controlDescription"
0x37c60  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x37c65  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x37c6a  stloc.1
0x37c6b  br       loc_37FA5
0x37c70  ldloc.1
0x37c71  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x37c76  castclass [System.Xml]System.Xml.XmlNode
0x37c7b  stloc.2
0x37c7c  ldloc.2
0x37c7d  ldstr    aCustomcontrol_0// "customControl"
0x37c82  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x37c87  stloc.3
0x37c88  ldnull
0x37c89  stloc.s  4
0x37c8b  ldc.i4.0
0x37c8c  stloc.s  5
0x37c8e  ldc.i4.0
0x37c8f  stloc.s  6
0x37c91  ldnull
0x37c92  stloc.s  7
0x37c94  ldloc.2
0x37c95  ldstr    aCustomcontrolN// "customControl[not(@version or @name)]"
0x37c9a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x37c9f  stloc.s  4
0x37ca1  ldloc.s  4
0x37ca3  brfalse.s loc_37CC7
0x37ca5  ldloc.s  4
0x37ca7  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37cac  brfalse.s loc_37CC7
0x37cae  ldloc.s  4
0x37cb0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37cb5  ldstr    aId// "id"
0x37cba  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x37cbf  stloc.s  7
0x37cc1  ldloc.s  6
0x37cc3  ldc.i4.1
0x37cc4  add
0x37cc5  stloc.s  6
0x37cc7  ldloc.3
0x37cc8  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x37ccd  stloc.s  8
0x37ccf  br       loc_37F82
0x37cd4  ldloc.s  8
0x37cd6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x37cdb  castclass [System.Xml]System.Xml.XmlNode
0x37ce0  stloc.s  9
0x37ce2  ldloc.s  9
0x37ce4  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37ce9  ldstr    aName// "name"
0x37cee  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x37cf3  brfalse  loc_37F82
0x37cf8  ldloc.0
0x37cf9  ldloc.s  9
0x37cfb  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37d00  ldstr    aName// "name"
0x37d05  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x37d0a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x37d0f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x37d14  brfalse.s loc_37D22
0x37d16  ldloc.s  9
0x37d18  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::IsControlForWeb(class [System.Xml]System.Xml.XmlNode control)
0x37d1d  brfalse  loc_37F82
0x37d22  ldloc.s  9
0x37d24  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x37d29  stloc.s  0xA
0x37d2b  ldloc.s  4
0x37d2d  brfalse  loc_37DE7
0x37d32  ldloc.s  9
0x37d34  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37d39  ldstr    aFormfactor// "formFactor"
0x37d3e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x37d43  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x37d48  call     int32 [mscorlib]System.Int32::Parse(string)
0x37d4d  ldc.i4.0
0x37d4e  blt      loc_37DE7
0x37d53  ldloc.s  9
0x37d55  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::IsControlForWeb(class [System.Xml]System.Xml.XmlNode control)
0x37d5a  brtrue.s loc_37D66
0x37d5c  ldloc.s  4
0x37d5e  ldc.i4.1
0x37d5f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::CloneNode(bool)
0x37d64  br.s     loc_37D68
0x37d66  ldloc.s  4
0x37d68  stloc.s  0xB
0x37d6a  ldloc.s  0xB
0x37d6c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37d71  ldstr    aFormfactor// "formFactor"
0x37d76  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x37d7b  brfalse.s loc_37DAB
0x37d7d  ldloc.s  0xB
0x37d7f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37d84  ldstr    aFormfactor// "formFactor"
0x37d89  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x37d8e  ldloc.s  9
0x37d90  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37d95  ldstr    aFormfactor// "formFactor"
0x37d9a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x37d9f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x37da4  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x37da9  br.s     loc_37DD4
0x37dab  ldloc.s  0xB
0x37dad  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37db2  ldloc.s  9
0x37db4  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37db9  ldstr    aFormfactor// "formFactor"
0x37dbe  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x37dc3  ldc.i4.1
0x37dc4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::CloneNode(bool)
0x37dc9  castclass [System.Xml]System.Xml.XmlAttribute
0x37dce  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x37dd3  pop
0x37dd4  ldloc.s  9
0x37dd6  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::IsControlForWeb(class [System.Xml]System.Xml.XmlNode control)
0x37ddb  brtrue.s loc_37DE7
0x37ddd  ldloc.s  0xA
0x37ddf  ldloc.s  0xB
0x37de1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x37de6  pop
0x37de7  ldloc.s  0xA
0x37de9  ldloc.s  9
0x37deb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x37df0  pop
0x37df1  ldloc.s  5
0x37df3  ldc.i4.1
0x37df4  add
0x37df5  stloc.s  5
0x37df7  ldstr    aFormxml_2// "FormXML"
0x37dfc  ldarg.2
0x37dfd  call     instance bool [mscorlib]System.String::Equals(string)
0x37e02  brtrue.s loc_37E14
0x37e04  ldstr    aDashboards// "Dashboards"
0x37e09  ldarg.2
0x37e0a  call     instance bool [mscorlib]System.String::Equals(string)
0x37e0f  brfalse  loc_37F64
0x37e14  ldloc.2
0x37e15  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37e1a  ldstr    aForcontrol// "forControl"
0x37e1f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x37e24  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x37e29  stloc.s  0xC
0x37e2b  ldstr    aControlTransla// "//control[translate(@classid, 'abcdefgh"...
0x37e30  ldsflda  valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormConstants::CustomControlClassId
0x37e35  constrained. [mscorlib]System.Guid
0x37e3b  callvirt instance string [mscorlib]System.Object::ToString()
0x37e40  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x37e45  ldstr    asc_EA17A// "}']"
0x37e4a  call     string [mscorlib]System.String::Concat(string, string, string)
0x37e4f  stloc.s  0xD
0x37e51  ldarg.0
0x37e52  ldloc.s  0xD
0x37e54  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x37e59  stloc.s  0xE
0x37e5b  ldloc.s  0xE
0x37e5d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x37e62  stloc.s  0xF
0x37e64  br       loc_37F35
0x37e69  ldloc.s  0xF
0x37e6b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x37e70  castclass [System.Xml]System.Xml.XmlNode
0x37e75  stloc.s  0x10
0x37e77  ldloc.s  0x10
0x37e79  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37e7e  ldstr    aUniqueid// "uniqueid"
0x37e83  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x37e88  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x37e8d  ldloc.s  0xC
0x37e8f  callvirt instance bool [mscorlib]System.String::Equals(string)
0x37e94  brfalse  loc_37F35
0x37e99  ldc.i4.0
0x37e9a  stloc.s  0x11
0x37e9c  ldloc.2
0x37e9d  ldstr    aCustomcontrol_0// "customControl"
0x37ea2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x37ea7  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x37eac  stloc.s  0x12
0x37eae  br.s     loc_37EEC
0x37eb0  ldloc.s  0x12
0x37eb2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x37eb7  castclass [System.Xml]System.Xml.XmlNode
0x37ebc  stloc.s  0x13
0x37ebe  ldloc.s  0x13
0x37ec0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37ec5  ldstr    aName// "name"
0x37eca  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x37ecf  brfalse.s loc_37EE9
0x37ed1  ldloc.s  0x13
0x37ed3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37ed8  ldstr    aVersion// "version"
0x37edd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x37ee2  brfalse.s loc_37EE9
0x37ee4  ldc.i4.0
0x37ee5  stloc.s  0x11
0x37ee7  leave.s  loc_37F0C
0x37ee9  ldc.i4.1
0x37eea  stloc.s  0x11
0x37eec  ldloc.s  0x12
0x37eee  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x37ef3  brtrue.s loc_37EB0
0x37ef5  leave.s  loc_37F0C
0x37ef7  ldloc.s  0x12
0x37ef9  isinst   [mscorlib]System.IDisposable
0x37efe  stloc.s  0x14
0x37f00  ldloc.s  0x14
0x37f02  brfalse.s loc_37F0B
0x37f04  ldloc.s  0x14
0x37f06  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37f0b  endfinally
0x37f0c  ldloc.s  7
0x37f0e  ldnull
0x37f0f  cgt.un
0x37f11  ldloc.s  0x11
0x37f13  and
0x37f14  brfalse.s loc_37F41
0x37f16  ldloc.s  0x10
0x37f18  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x37f1d  ldstr    aClassid// "classid"
0x37f22  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x37f27  ldloc.s  7
0x37f29  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x37f2e  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x37f33  leave.s  loc_37F64
0x37f35  ldloc.s  0xF
0x37f37  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x37f3c  brtrue   loc_37E69
0x37f41  leave.s  loc_37F64
0x37f43  ldloc.s  0xF
0x37f45  isinst   [mscorlib]System.IDisposable
0x37f4a  stloc.s  0x14
0x37f4c  ldloc.s  0x14
0x37f4e  brfalse.s loc_37F57
0x37f50  ldloc.s  0x14
0x37f52  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37f57  endfinally
0x37f58  ldloc.s  0xE
0x37f5a  brfalse.s loc_37F63
0x37f5c  ldloc.s  0xE
0x37f5e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37f63  endfinally
0x37f64  ldloc.3
0x37f65  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x37f6a  ldloc.s  5
0x37f6c  ldloc.s  6
0x37f6e  add
0x37f6f  bne.un.s loc_37F82
0x37f71  ldloc.s  0xA
0x37f73  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x37f78  ldloc.s  0xA
0x37f7a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x37f7f  pop
0x37f80  leave.s  loc_37FA5
0x37f82  ldloc.s  8
0x37f84  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x37f89  brtrue   loc_37CD4
0x37f8e  leave.s  loc_37FA5
0x37f90  ldloc.s  8
0x37f92  isinst   [mscorlib]System.IDisposable
0x37f97  stloc.s  0x14
0x37f99  ldloc.s  0x14
0x37f9b  brfalse.s loc_37FA4
0x37f9d  ldloc.s  0x14
0x37f9f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37fa4  endfinally
0x37fa5  ldloc.1
0x37fa6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x37fab  brtrue   loc_37C70
0x37fb0  leave.s  loc_37FC6
0x37fb2  ldloc.1
0x37fb3  isinst   [mscorlib]System.IDisposable
0x37fb8  stloc.s  0x14
0x37fba  ldloc.s  0x14
0x37fbc  brfalse.s loc_37FC5
0x37fbe  ldloc.s  0x14
0x37fc0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37fc5  endfinally
0x37fc6  ret
```
