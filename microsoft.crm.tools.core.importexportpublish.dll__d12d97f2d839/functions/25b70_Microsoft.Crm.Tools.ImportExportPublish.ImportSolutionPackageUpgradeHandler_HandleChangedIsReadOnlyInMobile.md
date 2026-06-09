# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::HandleChangedIsReadOnlyInMobile

- ea: `0x25b70`
- end: `0x25c67`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::HandleChangedIsReadOnlyInMobile`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x25b70`

## string_xrefs

- `0x25bb9`: `IsReadOnlyInMobileClient`
- `0x25bf5`: `IsReadOnlyInMobileClient`
- `0x25c19`: `IsReadOnlyInMobileClient`
- `0x25c30`: `IsReadOnlyInMobileClient`
- `0x25b98`: `ImportExportXml/Entities/Entity/EntityInfo/entity[@Name="{0}"]`

## pseudocode

```c

```

## disassembly

```asm
0x25b70  ldc.i4.2
0x25b71  newarr   [mscorlib]System.String
0x25b76  dup
0x25b77  ldc.i4.0
0x25b78  ldstr    aQueue// "Queue"
0x25b7d  stelem.ref
0x25b7e  dup
0x25b7f  ldc.i4.1
0x25b80  ldstr    aIncident_0// "Incident"
0x25b85  stelem.ref
0x25b86  stloc.0
0x25b87  ldc.i4.0
0x25b88  stloc.1
0x25b89  br       loc_25C5D
0x25b8e  ldloc.0
0x25b8f  ldloc.1
0x25b90  ldelem.ref
0x25b91  stloc.2
0x25b92  ldarg.1
0x25b93  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25b98  ldstr    aImportexportxm_67// "ImportExportXml/Entities/Entity/EntityI"...
0x25b9d  ldc.i4.1
0x25b9e  newarr   [mscorlib]System.Object
0x25ba3  dup
0x25ba4  ldc.i4.0
0x25ba5  ldloc.2
0x25ba6  stelem.ref
0x25ba7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25bac  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x25bb1  stloc.3
0x25bb2  ldloc.3
0x25bb3  brfalse  loc_25C59
0x25bb8  ldloc.3
0x25bb9  ldstr    aIsreadonlyinmo// "IsReadOnlyInMobileClient"
0x25bbe  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x25bc3  brfalse  loc_25C59
0x25bc8  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x25bcd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x25bd2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_LeoServiceFeatures()
0x25bd7  ldarg.s  5
0x25bd9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x25bde  ldarg.s  0xA
0x25be0  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x25be5  brfalse.s loc_25C0B
0x25be7  ldloc.2
0x25be8  ldstr    aIncident_0// "Incident"
0x25bed  callvirt instance bool [mscorlib]System.String::Equals(string)
0x25bf2  brtrue.s loc_25C59
0x25bf4  ldloc.3
0x25bf5  ldstr    aIsreadonlyinmo// "IsReadOnlyInMobileClient"
0x25bfa  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x25bff  ldstr    a1// "1"
0x25c04  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x25c09  br.s     loc_25C59
0x25c0b  ldloc.2
0x25c0c  ldstr    aIncident_0// "Incident"
0x25c11  callvirt instance bool [mscorlib]System.String::Equals(string)
0x25c16  brfalse.s loc_25C2F
0x25c18  ldloc.3
0x25c19  ldstr    aIsreadonlyinmo// "IsReadOnlyInMobileClient"
0x25c1e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x25c23  ldstr    a1// "1"
0x25c28  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x25c2d  br.s     loc_25C59
0x25c2f  ldloc.3
0x25c30  ldstr    aIsreadonlyinmo// "IsReadOnlyInMobileClient"
0x25c35  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x25c3a  ldstr    a0_1// "0"
0x25c3f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x25c44  ldloc.3
0x25c45  ldstr    aIsvisibleinmob_1// "IsVisibleInMobileClient"
0x25c4a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x25c4f  ldstr    a0_1// "0"
0x25c54  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x25c59  ldloc.1
0x25c5a  ldc.i4.1
0x25c5b  add
0x25c5c  stloc.1
0x25c5d  ldloc.1
0x25c5e  ldloc.0
0x25c5f  ldlen
0x25c60  conv.i4
0x25c61  blt      loc_25B8E
0x25c66  ret
```
