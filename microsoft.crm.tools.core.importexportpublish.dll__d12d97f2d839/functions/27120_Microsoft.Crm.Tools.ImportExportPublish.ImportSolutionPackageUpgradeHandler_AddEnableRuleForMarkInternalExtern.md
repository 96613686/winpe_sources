# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::AddEnableRuleForMarkInternalExternalRibbon

- ea: `0x27120`
- end: `0x2723c`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::AddEnableRuleForMarkInternalExternalRibbon`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x270e0`

## callees

- `0x27120`

## string_xrefs

- `0x27126`: `ImportExportXml//RibbonDiffXml/CommandDefinitions/CommandDefinition[@Id='{0}']`
- `0x2714a`: `ImportExportXml//RibbonDiffXml/CommandDefinitions/CommandDefinition/EnableRules/EnableRule`
- `0x27169`: `ImportExportXml//RibbonDiffXml/CommandDefinitions/CommandDefinition[@Id='{0}']/EnableRules`
- `0x271eb`: `ImportExportXml//RibbonDiffXml/CommandDefinitions/CommandDefinition[@Id='{0}']/EnableRules`
- `0x271c0`: `ImportExportXml//RibbonDiffXml/CommandDefinitions/CommandDefinition[@Id='{0}']/EnableRules/EnableRule[@Id='{1}']`

## pseudocode

```c

```

## disassembly

```asm
0x27120  ldarg.0
0x27121  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27126  ldstr    aImportexportxm_88// "ImportExportXml//RibbonDiffXml/CommandD"...
0x2712b  ldc.i4.1
0x2712c  newarr   [mscorlib]System.Object
0x27131  dup
0x27132  ldc.i4.0
0x27133  ldarg.1
0x27134  stelem.ref
0x27135  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2713a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2713f  brfalse  loc_2723B
0x27144  ldarg.0
0x27145  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2714a  ldstr    aImportexportxm_89// "ImportExportXml//RibbonDiffXml/CommandD"...
0x2714f  ldc.i4.0
0x27150  newarr   [mscorlib]System.Object
0x27155  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2715a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2715f  stloc.0
0x27160  ldloc.0
0x27161  brtrue.s loc_271BA
0x27163  ldarg.0
0x27164  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27169  ldstr    aImportexportxm_90// "ImportExportXml//RibbonDiffXml/CommandD"...
0x2716e  ldc.i4.1
0x2716f  newarr   [mscorlib]System.Object
0x27174  dup
0x27175  ldc.i4.0
0x27176  ldarg.1
0x27177  stelem.ref
0x27178  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2717d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x27182  ldarg.0
0x27183  ldstr    aEnablerule// "EnableRule"
0x27188  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2718d  stloc.0
0x2718e  ldloc.0
0x2718f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x27194  pop
0x27195  ldarg.0
0x27196  ldstr    aId_0// "Id"
0x2719b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x271a0  stloc.1
0x271a1  ldloc.0
0x271a2  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x271a7  ldloc.1
0x271a8  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x271ad  pop
0x271ae  ldloc.1
0x271af  ldstr    aMscrmFormstate// "Mscrm.FormStateNotNew"
0x271b4  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x271b9  ret
0x271ba  ldarg.0
0x271bb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x271c0  ldstr    aImportexportxm_91// "ImportExportXml//RibbonDiffXml/CommandD"...
0x271c5  ldc.i4.2
0x271c6  newarr   [mscorlib]System.Object
0x271cb  dup
0x271cc  ldc.i4.0
0x271cd  ldarg.1
0x271ce  stelem.ref
0x271cf  dup
0x271d0  ldc.i4.1
0x271d1  ldstr    aMscrmFormstate// "Mscrm.FormStateNotNew"
0x271d6  stelem.ref
0x271d7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x271dc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x271e1  stloc.2
0x271e2  ldloc.2
0x271e3  brtrue.s loc_2723B
0x271e5  ldarg.0
0x271e6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x271eb  ldstr    aImportexportxm_90// "ImportExportXml//RibbonDiffXml/CommandD"...
0x271f0  ldc.i4.1
0x271f1  newarr   [mscorlib]System.Object
0x271f6  dup
0x271f7  ldc.i4.0
0x271f8  ldarg.1
0x271f9  stelem.ref
0x271fa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x271ff  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x27204  ldarg.0
0x27205  ldstr    aEnablerule// "EnableRule"
0x2720a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2720f  stloc.2
0x27210  ldloc.2
0x27211  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x27216  pop
0x27217  ldarg.0
0x27218  ldstr    aId_0// "Id"
0x2721d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x27222  stloc.3
0x27223  ldloc.2
0x27224  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x27229  ldloc.3
0x2722a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x2722f  pop
0x27230  ldloc.3
0x27231  ldstr    aMscrmFormstate// "Mscrm.FormStateNotNew"
0x27236  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x2723b  ret
```
