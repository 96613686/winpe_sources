# Microsoft.Crm.XmlUpgrade.DefaultCustomizationsXmlUpgrade::ProcessRibbon

- ea: `0x4abd0`
- end: `0x4abf9`
- name: `Microsoft.Crm.XmlUpgrade.DefaultCustomizationsXmlUpgrade::ProcessRibbon`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4ab10`

## callees

- `0x49de0`
- `0x49e90`

## string_xrefs

- `0x4abd8`: `ImportExportXml//RibbonDiffXml/CommandDefinitions/CommandDefinition/Actions/JavaScriptFunction`
- `0x4abe9`: `ImportExportXml//RibbonDiffXml/RuleDefinitions//CustomRule`

## pseudocode

```c

```

## disassembly

```asm
0x4abd0  newobj   instance void Microsoft.Crm.XmlUpgrade.RibbonXmlProcessor::.ctor()
0x4abd5  dup
0x4abd6  ldarg.1
0x4abd7  ldarg.1
0x4abd8  ldstr    aImportexportxm_3// "ImportExportXml//RibbonDiffXml/CommandD"...
0x4abdd  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x4abe2  callvirt instance void Microsoft.Crm.XmlUpgrade.RibbonXmlProcessor::ProcessRibbonXml(class [System.Xml]System.Xml.XmlDocument xmlDoc, class [System.Xml]System.Xml.XmlNodeList ribbonNodes)
0x4abe7  ldarg.1
0x4abe8  ldarg.1
0x4abe9  ldstr    aImportexportxm_4// "ImportExportXml//RibbonDiffXml/RuleDefi"...
0x4abee  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x4abf3  callvirt instance void Microsoft.Crm.XmlUpgrade.RibbonXmlProcessor::ProcessRibbonXml(class [System.Xml]System.Xml.XmlDocument xmlDoc, class [System.Xml]System.Xml.XmlNodeList ribbonNodes)
0x4abf8  ret
```
