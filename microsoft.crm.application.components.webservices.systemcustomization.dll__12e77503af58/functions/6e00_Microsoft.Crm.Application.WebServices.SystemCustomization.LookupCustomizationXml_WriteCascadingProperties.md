# Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::WriteCascadingProperties

- ea: `0x6e00`
- end: `0x6e67`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::WriteCascadingProperties`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x6cd0`

## string_xrefs

- `0x6e50`: `delete`

## pseudocode

```c

```

## disassembly

```asm
0x6e00  ldarg.1
0x6e01  ldstr    aCascading// "cascading"
0x6e06  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x6e0b  ldarg.1
0x6e0c  ldstr    aAssign// "assign"
0x6e11  ldarg.0
0x6e12  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_assignCascade
0x6e17  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6e1c  ldarg.1
0x6e1d  ldstr    aShare// "share"
0x6e22  ldarg.0
0x6e23  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_shareCascade
0x6e28  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6e2d  ldarg.1
0x6e2e  ldstr    aUnshare// "unshare"
0x6e33  ldarg.0
0x6e34  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_unshareCascade
0x6e39  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6e3e  ldarg.1
0x6e3f  ldstr    aReparent// "reparent"
0x6e44  ldarg.0
0x6e45  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_reparentCascade
0x6e4a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6e4f  ldarg.1
0x6e50  ldstr    aDelete// "delete"
0x6e55  ldarg.0
0x6e56  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_deleteCascade
0x6e5b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6e60  ldarg.1
0x6e61  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x6e66  ret
```
