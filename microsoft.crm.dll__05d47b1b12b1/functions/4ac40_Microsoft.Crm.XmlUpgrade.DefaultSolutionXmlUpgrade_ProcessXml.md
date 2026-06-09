# Microsoft.Crm.XmlUpgrade.DefaultSolutionXmlUpgrade::ProcessXml

- ea: `0x4ac40`
- end: `0x4ac6e`
- name: `Microsoft.Crm.XmlUpgrade.DefaultSolutionXmlUpgrade::ProcessXml`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4a1b0`
- `0x4ace0`
- `0x50ae0`

## string_xrefs

- `0x4ac52`: `ImportExportXml/SolutionManifest/MissingDependencies/MissingDependency/Required`

## pseudocode

```c

```

## disassembly

```asm
0x4ac40  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x4ac45  stloc.0
0x4ac46  ldloc.0
0x4ac47  call     class Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::get_Instance()
0x4ac4c  stfld    class Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation <>c__DisplayClass1_0::upgradeInfo
0x4ac51  ldarg.1
0x4ac52  ldstr    aImportexportxm_5// "ImportExportXml/SolutionManifest/Missin"...
0x4ac57  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x4ac5c  ldloc.0
0x4ac5d  ldftn    instance void <>c__DisplayClass1_0::<ProcessXml>b__0(class [System.Xml]System.Xml.XmlNode requiredNode)
0x4ac63  newobj   instance void class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode>::.ctor(object, native int)
0x4ac68  call     void Microsoft.Crm.XmlUpgrade.ParserExtensions::ForEach(class [System.Xml]System.Xml.XmlNodeList xmlNodeList, class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode> action)
0x4ac6d  ret
```
