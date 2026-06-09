# Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::Create

- ea: `0x4a1f0`
- end: `0x4a214`
- name: `Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::Create`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4a1b0`

## callees

- `0x190a0`
- `0x4a220`

## string_xrefs

- `0x4a1f0`: `FormXmlUpgradeTable.xml`

## pseudocode

```c

```

## disassembly

```asm
0x4a1f0  ldstr    aFormxmlupgrade// "FormXmlUpgradeTable.xml"
0x4a1f5  call     string Microsoft.Crm.ApplicationFileManager::GetApplicationFilePath(string fileId)
0x4a1fa  stloc.0
0x4a1fb  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x4a200  dup
0x4a201  ldnull
0x4a202  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x4a207  dup
0x4a208  ldloc.0
0x4a209  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(string)
0x4a20e  call     class Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::CreateFromXml(class [System.Xml]System.Xml.XmlDocument xmlDoc)
0x4a213  ret
```
