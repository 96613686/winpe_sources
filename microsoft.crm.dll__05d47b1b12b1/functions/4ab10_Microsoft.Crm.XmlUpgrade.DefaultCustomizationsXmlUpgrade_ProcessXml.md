# Microsoft.Crm.XmlUpgrade.DefaultCustomizationsXmlUpgrade::ProcessXml

- ea: `0x4ab10`
- end: `0x4ab43`
- name: `Microsoft.Crm.XmlUpgrade.DefaultCustomizationsXmlUpgrade::ProcessXml`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4ab50`
- `0x4ab90`
- `0x4abd0`

## string_xrefs

- `0x4ab19`: `ImportExportXml/Dashboards/Dashboard`
- `0x4ab25`: `ImportExportXml/InteractionCentricDashboards/InteractionCentricDashboard`
- `0x4ab31`: `ImportExportXml/Dialogs/Dialog`

## pseudocode

```c

```

## disassembly

```asm
0x4ab10  ldarg.0
0x4ab11  ldarg.1
0x4ab12  call     instance void Microsoft.Crm.XmlUpgrade.DefaultCustomizationsXmlUpgrade::ProcessEntityNode(class [System.Xml]System.Xml.XmlDocument xmlDoc)
0x4ab17  ldarg.0
0x4ab18  ldarg.1
0x4ab19  ldstr    aImportexportxm// "ImportExportXml/Dashboards/Dashboard"
0x4ab1e  call     instance void Microsoft.Crm.XmlUpgrade.DefaultCustomizationsXmlUpgrade::ProcessNode(class [System.Xml]System.Xml.XmlDocument xmlDoc, string select)
0x4ab23  ldarg.0
0x4ab24  ldarg.1
0x4ab25  ldstr    aImportexportxm_0// "ImportExportXml/InteractionCentricDashb"...
0x4ab2a  call     instance void Microsoft.Crm.XmlUpgrade.DefaultCustomizationsXmlUpgrade::ProcessNode(class [System.Xml]System.Xml.XmlDocument xmlDoc, string select)
0x4ab2f  ldarg.0
0x4ab30  ldarg.1
0x4ab31  ldstr    aImportexportxm_1// "ImportExportXml/Dialogs/Dialog"
0x4ab36  call     instance void Microsoft.Crm.XmlUpgrade.DefaultCustomizationsXmlUpgrade::ProcessNode(class [System.Xml]System.Xml.XmlDocument xmlDoc, string select)
0x4ab3b  ldarg.0
0x4ab3c  ldarg.1
0x4ab3d  call     instance void Microsoft.Crm.XmlUpgrade.DefaultCustomizationsXmlUpgrade::ProcessRibbon(class [System.Xml]System.Xml.XmlDocument xmlDoc)
0x4ab42  ret
```
