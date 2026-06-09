# Microsoft.Crm.Ribbon.RibbonPlatformXml::GenerateLayoutXml

- ea: `0x9cb0`
- end: `0x9e5b`
- name: `Microsoft.Crm.Ribbon.RibbonPlatformXml::GenerateLayoutXml`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x9830`

## callees

- `0x9cb0`

## string_xrefs

- `0x9ce4`: `TabSwitchCommand`
- `0x9cf4`: `RootEventCommand`
- `0x9d04`: `ToolTipDisabledCommandTitle`
- `0x9d14`: `ToolTipDisabledCommandDescription`
- `0x9d5a`: `ImageSideArrow`
- `0x9d7c`: `ImageSideArrow`
- `0x9e11`: `Templates`
- `0x9e1c`: `RibbonTemplates`
- `0x9e2c`: `Mscrm.RibbonTemplates`

## pseudocode

```c

```

## disassembly

```asm
0x9cb0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x9cb5  stloc.0
0x9cb6  ldloc.0
0x9cb7  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder)
0x9cbc  stloc.1
0x9cbd  ldloc.1
0x9cbe  ldstr    aUi// "UI"
0x9cc3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x9cc8  ldloc.1
0x9cc9  ldstr    aRibbon// "Ribbon"
0x9cce  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x9cd3  ldloc.1
0x9cd4  ldstr    aId_0// "Id"
0x9cd9  ldstr    aMscrmRibbon// "Mscrm.Ribbon"
0x9cde  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x9ce3  ldloc.1
0x9ce4  ldstr    aTabswitchcomma// "TabSwitchCommand"
0x9ce9  ldstr    aMscrmRibbonTab// "Mscrm.Ribbon.TabSwitch"
0x9cee  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x9cf3  ldloc.1
0x9cf4  ldstr    aRooteventcomma// "RootEventCommand"
0x9cf9  ldstr    aMscrmRibbonRoo// "Mscrm.Ribbon.RootEvent"
0x9cfe  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x9d03  ldloc.1
0x9d04  ldstr    aTooltipdisable// "ToolTipDisabledCommandTitle"
0x9d09  ldstr    aResourcesRibbo_1// "$Resources:Ribbon.Tooltip.Disabled.Titl"...
0x9d0e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x9d13  ldloc.1
0x9d14  ldstr    aTooltipdisable_0// "ToolTipDisabledCommandDescription"
0x9d19  ldstr    aResourcesRibbo_2// "$Resources:Ribbon.Tooltip.Disabled.Text"
0x9d1e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x9d23  ldloc.1
0x9d24  ldstr    aImage32by32gro// "Image32by32GroupPopupDefault"
0x9d29  ldstr    aImgsPlaceholde// "/_imgs/placeholders/ribbon_placeholder_"...
0x9d2e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x9d33  ldloc.1
0x9d34  ldstr    aImagedownarrow// "ImageDownArrow"
0x9d39  ldstr    aImgsRibbonArro// "/_imgs/ribbon/arrow_down.png"
0x9d3e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x9d43  ldarg.2
0x9d44  brtrue.s loc_9D8B
0x9d46  ldarg.0
0x9d47  brfalse.s loc_9D6B
0x9d49  ldloc.1
0x9d4a  ldstr    aTextdirection// "TextDirection"
0x9d4f  ldstr    aRtl// "rtl"
0x9d54  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x9d59  ldloc.1
0x9d5a  ldstr    aImagesidearrow// "ImageSideArrow"
0x9d5f  ldstr    aImgsRibbonArro_0// "/_imgs/ribbon/arrow_left.png"
0x9d64  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x9d69  br.s     loc_9D8B
0x9d6b  ldloc.1
0x9d6c  ldstr    aTextdirection// "TextDirection"
0x9d71  ldstr    aLtr// "ltr"
0x9d76  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x9d7b  ldloc.1
0x9d7c  ldstr    aImagesidearrow// "ImageSideArrow"
0x9d81  ldstr    aImgsRibbonArro_1// "/_imgs/ribbon/arrow_right.png"
0x9d86  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x9d8b  ldloc.1
0x9d8c  ldstr    aTabs// "Tabs"
0x9d91  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x9d96  ldloc.1
0x9d97  ldstr    aId_0// "Id"
0x9d9c  ldstr    aMscrmTabs// "Mscrm.Tabs"
0x9da1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x9da6  ldloc.1
0x9da7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x9dac  ldloc.1
0x9dad  ldstr    aContextualtabs// "ContextualTabs"
0x9db2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x9db7  ldloc.1
0x9db8  ldstr    aId_0// "Id"
0x9dbd  ldstr    aMscrmContextua// "Mscrm.ContextualTabs"
0x9dc2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x9dc7  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0x9dcc  stloc.2
0x9dcd  ldloc.2
0x9dce  ldc.i4.1
0x9dcf  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_ConformanceLevel(valuetype [System.Xml]System.Xml.ConformanceLevel)
0x9dd4  ldarg.1
0x9dd5  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x9dda  ldloc.2
0x9ddb  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader, class [System.Xml]System.Xml.XmlReaderSettings)
0x9de0  stloc.3
0x9de1  ldloc.3
0x9de2  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x9de7  pop
0x9de8  ldloc.1
0x9de9  ldloc.3
0x9dea  ldc.i4.1
0x9deb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteNode(class [System.Xml]System.Xml.XmlReader, bool)
0x9df0  ldloc.3
0x9df1  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_EOF()
0x9df6  brfalse.s loc_9DE8
0x9df8  leave.s  loc_9E04
0x9dfa  ldloc.3
0x9dfb  brfalse.s loc_9E03
0x9dfd  ldloc.3
0x9dfe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9e03  endfinally
0x9e04  ldloc.1
0x9e05  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x9e0a  ldloc.1
0x9e0b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x9e10  ldloc.1
0x9e11  ldstr    aTemplates// "Templates"
0x9e16  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x9e1b  ldloc.1
0x9e1c  ldstr    aRibbontemplate// "RibbonTemplates"
0x9e21  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x9e26  ldloc.1
0x9e27  ldstr    aId_0// "Id"
0x9e2c  ldstr    aMscrmRibbontem// "Mscrm.RibbonTemplates"
0x9e31  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x9e36  ldloc.1
0x9e37  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x9e3c  ldloc.1
0x9e3d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x9e42  ldloc.1
0x9e43  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x9e48  leave.s  loc_9E54
0x9e4a  ldloc.1
0x9e4b  brfalse.s loc_9E53
0x9e4d  ldloc.1
0x9e4e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9e53  endfinally
0x9e54  ldloc.0
0x9e55  callvirt instance string [mscorlib]System.Object::ToString()
0x9e5a  ret
```
