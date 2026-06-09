# Microsoft.Crm.Metadata.SavedQueryHelper::GenerateLayoutXml_0

- ea: `0x5ceb0`
- end: `0x5d161`
- name: `Microsoft.Crm.Metadata.SavedQueryHelper::GenerateLayoutXml_0`
- size: `689`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x5ce40`

## callees

- `0x29450`
- `0x29460`
- `0x5ceb0`

## string_xrefs

- `0x5d044`: `createdon`
- `0x5d135`: `createdon`
- `0x5d0ba`: `processid`

## pseudocode

```c

```

## disassembly

```asm
0x5ceb0  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument()
0x5ceb5  stloc.0
0x5ceb6  ldc.i4.5
0x5ceb7  ldarg.0
0x5ceb8  beq.s    loc_5CEBE
0x5ceba  ldc.i4.7
0x5cebb  ldarg.0
0x5cebc  bne.un.s loc_5CEC4
0x5cebe  ldarg.2
0x5cebf  stloc.1
0x5cec0  ldarg.1
0x5cec1  stloc.2
0x5cec2  br.s     loc_5CED0
0x5cec4  ldstr    aResultset// "resultset"
0x5cec9  stloc.1
0x5ceca  ldstr    aResult// "result"
0x5cecf  stloc.2
0x5ced0  ldloc.0
0x5ced1  ldstr    aGrid// "grid"
0x5ced6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5cedb  stloc.3
0x5cedc  ldloc.3
0x5cedd  ldstr    aName// "name"
0x5cee2  ldloc.1
0x5cee3  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5cee8  ldloc.3
0x5cee9  ldstr    aObject// "object"
0x5ceee  ldarga.s 4
0x5cef0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5cef5  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5cefa  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5ceff  ldloc.3
0x5cf00  ldstr    aJump// "jump"
0x5cf05  ldarg.3
0x5cf06  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5cf0b  ldloc.3
0x5cf0c  ldstr    aSelect// "select"
0x5cf11  ldstr    a1// "1"
0x5cf16  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5cf1b  ldloc.3
0x5cf1c  ldstr    aIcon// "icon"
0x5cf21  ldstr    a1// "1"
0x5cf26  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5cf2b  ldloc.3
0x5cf2c  ldstr    aPreview// "preview"
0x5cf31  ldarg.0
0x5cf32  ldc.i4.7
0x5cf33  beq.s    loc_5CF3C
0x5cf35  ldstr    a1// "1"
0x5cf3a  br.s     loc_5CF41
0x5cf3c  ldstr    a0_1// "0"
0x5cf41  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5cf46  ldloc.0
0x5cf47  ldstr    aRow// "row"
0x5cf4c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5cf51  stloc.s  4
0x5cf53  ldloc.s  4
0x5cf55  ldstr    aName// "name"
0x5cf5a  ldloc.2
0x5cf5b  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5cf60  ldloc.s  4
0x5cf62  ldstr    aId// "id"
0x5cf67  ldarg.s  5
0x5cf69  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5cf6e  ldloc.3
0x5cf6f  ldloc.s  4
0x5cf71  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5cf76  pop
0x5cf77  ldarg.s  7
0x5cf79  brfalse  loc_5D0E1
0x5cf7e  ldloc.0
0x5cf7f  ldstr    aCell// "cell"
0x5cf84  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5cf89  stloc.s  5
0x5cf8b  ldloc.s  5
0x5cf8d  ldstr    aName// "name"
0x5cf92  ldarg.s  7
0x5cf94  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x5cf99  call     string Microsoft.Crm.Metadata.BusinessProcessFlowEntityBuilder::GetCustomBPFEntityColumnName(string entityLogicalName)
0x5cf9e  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5cfa3  ldloc.s  5
0x5cfa5  ldstr    aWidth// "width"
0x5cfaa  ldstr    a300// "300"
0x5cfaf  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5cfb4  ldloc.s  4
0x5cfb6  ldloc.s  5
0x5cfb8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5cfbd  pop
0x5cfbe  ldloc.0
0x5cfbf  ldstr    aCell// "cell"
0x5cfc4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5cfc9  stloc.s  6
0x5cfcb  ldloc.s  6
0x5cfcd  ldstr    aName// "name"
0x5cfd2  ldstr    aActivestageid_0// "activestageid"
0x5cfd7  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5cfdc  ldloc.s  6
0x5cfde  ldstr    aWidth// "width"
0x5cfe3  ldstr    a150// "150"
0x5cfe8  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5cfed  ldloc.s  4
0x5cfef  ldloc.s  6
0x5cff1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5cff6  pop
0x5cff7  ldloc.0
0x5cff8  ldstr    aCell// "cell"
0x5cffd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d002  stloc.s  7
0x5d004  ldloc.s  7
0x5d006  ldstr    aName// "name"
0x5d00b  ldstr    aStatuscode// "statuscode"
0x5d010  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d015  ldloc.s  7
0x5d017  ldstr    aWidth// "width"
0x5d01c  ldstr    a150// "150"
0x5d021  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d026  ldloc.s  4
0x5d028  ldloc.s  7
0x5d02a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d02f  pop
0x5d030  ldloc.0
0x5d031  ldstr    aCell// "cell"
0x5d036  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d03b  stloc.s  8
0x5d03d  ldloc.s  8
0x5d03f  ldstr    aName// "name"
0x5d044  ldstr    aCreatedon// "createdon"
0x5d049  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d04e  ldloc.s  8
0x5d050  ldstr    aWidth// "width"
0x5d055  ldstr    a150// "150"
0x5d05a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d05f  ldloc.s  4
0x5d061  ldloc.s  8
0x5d063  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d068  pop
0x5d069  ldarg.0
0x5d06a  ldc.i4.2
0x5d06b  bne.un.s loc_5D0A6
0x5d06d  ldloc.0
0x5d06e  ldstr    aCell// "cell"
0x5d073  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d078  stloc.s  0xA
0x5d07a  ldloc.s  0xA
0x5d07c  ldstr    aName// "name"
0x5d081  call     string Microsoft.Crm.Metadata.BusinessProcessFlowEntityBuilder::GetCustomBPFEntityDurationColumnName()
0x5d086  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d08b  ldloc.s  0xA
0x5d08d  ldstr    aWidth// "width"
0x5d092  ldstr    a150// "150"
0x5d097  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d09c  ldloc.s  4
0x5d09e  ldloc.s  0xA
0x5d0a0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d0a5  pop
0x5d0a6  ldloc.0
0x5d0a7  ldstr    aCell// "cell"
0x5d0ac  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d0b1  stloc.s  9
0x5d0b3  ldloc.s  9
0x5d0b5  ldstr    aName// "name"
0x5d0ba  ldstr    aProcessid_0// "processid"
0x5d0bf  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d0c4  ldloc.s  9
0x5d0c6  ldstr    aWidth// "width"
0x5d0cb  ldstr    a300// "300"
0x5d0d0  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d0d5  ldloc.s  4
0x5d0d7  ldloc.s  9
0x5d0d9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d0de  pop
0x5d0df  br.s     loc_5D15A
0x5d0e1  ldloc.0
0x5d0e2  ldstr    aCell// "cell"
0x5d0e7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d0ec  stloc.s  0xB
0x5d0ee  ldloc.s  0xB
0x5d0f0  ldstr    aName// "name"
0x5d0f5  ldarg.3
0x5d0f6  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d0fb  ldloc.s  0xB
0x5d0fd  ldstr    aWidth// "width"
0x5d102  ldstr    a300// "300"
0x5d107  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d10c  ldloc.s  4
0x5d10e  ldloc.s  0xB
0x5d110  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d115  pop
0x5d116  ldarg.s  6
0x5d118  brfalse.s loc_5D121
0x5d11a  ldloc.3
0x5d11b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x5d120  ret
0x5d121  ldloc.0
0x5d122  ldstr    aCell// "cell"
0x5d127  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d12c  stloc.s  0xC
0x5d12e  ldloc.s  0xC
0x5d130  ldstr    aName// "name"
0x5d135  ldstr    aCreatedon// "createdon"
0x5d13a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d13f  ldloc.s  0xC
0x5d141  ldstr    aWidth// "width"
0x5d146  ldstr    a125// "125"
0x5d14b  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d150  ldloc.s  4
0x5d152  ldloc.s  0xC
0x5d154  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d159  pop
0x5d15a  ldloc.3
0x5d15b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x5d160  ret
```
