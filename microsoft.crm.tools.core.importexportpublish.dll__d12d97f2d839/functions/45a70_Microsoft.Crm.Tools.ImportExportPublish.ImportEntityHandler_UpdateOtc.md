# Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::UpdateOtc

- ea: `0x45a70`
- end: `0x45b2d`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::UpdateOtc`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x44870`

## callees

- `0x45a70`
- `0x45b30`
- `0x45b80`

## string_xrefs

- `0x45ab6`: `CustomControlDefaultConfigs/CustomControlDefaultConfig/PrimaryEntityTypeCode`
- `0x45ad6`: `SavedQueries/savedqueries/savedquery/layoutxml/grid/@object`
- `0x45b08`: `ImportExportXml/Slas/Sla/@PrimaryEntityOTC`

## pseudocode

```c

```

## disassembly

```asm
0x45a70  ldarg.2
0x45a71  ldstr    aObjecttypecode// "ObjectTypeCode"
0x45a76  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x45a7b  stloc.0
0x45a7c  ldsfld   string [mscorlib]System.String::Empty
0x45a81  stloc.1
0x45a82  ldloc.0
0x45a83  brtrue.s loc_45AA7
0x45a85  ldarg.0
0x45a86  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x45a8b  ldstr    aObjecttypecode// "ObjectTypeCode"
0x45a90  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x45a95  stloc.2
0x45a96  ldloc.2
0x45a97  ldarg.1
0x45a98  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x45a9d  ldarg.2
0x45a9e  ldloc.2
0x45a9f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x45aa4  pop
0x45aa5  br.s     loc_45AB5
0x45aa7  ldloc.0
0x45aa8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x45aad  stloc.1
0x45aae  ldloc.0
0x45aaf  ldarg.1
0x45ab0  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x45ab5  ldarg.2
0x45ab6  ldstr    aCustomcontrold_7// "CustomControlDefaultConfigs/CustomContr"...
0x45abb  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x45ac0  stloc.3
0x45ac1  ldarg.0
0x45ac2  ldloc.3
0x45ac3  ldarg.1
0x45ac4  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::UpdateOtcInStringElement(class [System.Xml]System.Xml.XmlNodeList nodes, string newOtc)
0x45ac9  leave.s  loc_45AD5
0x45acb  ldloc.3
0x45acc  brfalse.s loc_45AD4
0x45ace  ldloc.3
0x45acf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45ad4  endfinally
0x45ad5  ldarg.2
0x45ad6  ldstr    aSavedqueriesSa_1// "SavedQueries/savedqueries/savedquery/la"...
0x45adb  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x45ae0  stloc.s  4
0x45ae2  ldarg.0
0x45ae3  ldloc.s  4
0x45ae5  ldarg.1
0x45ae6  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::UpdateOtcInStringElement(class [System.Xml]System.Xml.XmlNodeList nodes, string newOtc)
0x45aeb  leave.s  loc_45AF9
0x45aed  ldloc.s  4
0x45aef  brfalse.s loc_45AF8
0x45af1  ldloc.s  4
0x45af3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45af8  endfinally
0x45af9  ldloc.1
0x45afa  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x45aff  brfalse.s loc_45B02
0x45b01  ret
0x45b02  ldarg.2
0x45b03  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x45b08  ldstr    aImportexportxm_116// "ImportExportXml/Slas/Sla/@PrimaryEntity"...
0x45b0d  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x45b12  stloc.s  5
0x45b14  ldarg.0
0x45b15  ldloc.s  5
0x45b17  ldloc.1
0x45b18  ldarg.1
0x45b19  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::UpdateOtcInStringElement(class [System.Xml]System.Xml.XmlNodeList nodes, string oldOtc, string newOtc)
0x45b1e  leave.s  loc_45B2C
0x45b20  ldloc.s  5
0x45b22  brfalse.s loc_45B2B
0x45b24  ldloc.s  5
0x45b26  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45b2b  endfinally
0x45b2c  ret
```
