# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::WriteDisplayProperties

- ea: `0x7290`
- end: `0x73ec`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::WriteDisplayProperties`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7050`

## pseudocode

```c

```

## disassembly

```asm
0x7290  ldarg.1
0x7291  ldstr    aDisplayareas// "displayareas"
0x7296  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x729b  ldarg.1
0x729c  ldstr    aDisplayarea// "displayarea"
0x72a1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x72a6  ldarg.1
0x72a7  ldstr    aId// "id"
0x72ac  ldstr    aWorplace// "Worplace"
0x72b1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x72b6  ldarg.1
0x72b7  ldstr    aDisplayed// "displayed"
0x72bc  ldarg.0
0x72bd  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_displayInWorkplace
0x72c2  call     instance string [mscorlib]System.Boolean::ToString()
0x72c7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x72cc  ldarg.1
0x72cd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x72d2  ldarg.1
0x72d3  ldstr    aDisplayarea// "displayarea"
0x72d8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x72dd  ldarg.1
0x72de  ldstr    aId// "id"
0x72e3  ldstr    aSfa// "SFA"
0x72e8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x72ed  ldarg.1
0x72ee  ldstr    aDisplayed// "displayed"
0x72f3  ldarg.0
0x72f4  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_displayInSFA
0x72f9  call     instance string [mscorlib]System.Boolean::ToString()
0x72fe  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x7303  ldarg.1
0x7304  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x7309  ldarg.1
0x730a  ldstr    aDisplayarea// "displayarea"
0x730f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x7314  ldarg.1
0x7315  ldstr    aId// "id"
0x731a  ldstr    aMa// "MA"
0x731f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x7324  ldarg.1
0x7325  ldstr    aDisplayed// "displayed"
0x732a  ldarg.0
0x732b  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_displayInMA
0x7330  call     instance string [mscorlib]System.Boolean::ToString()
0x7335  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x733a  ldarg.1
0x733b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x7340  ldarg.1
0x7341  ldstr    aDisplayarea// "displayarea"
0x7346  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x734b  ldarg.1
0x734c  ldstr    aId// "id"
0x7351  ldstr    aCs// "CS"
0x7356  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x735b  ldarg.1
0x735c  ldstr    aDisplayed// "displayed"
0x7361  ldarg.0
0x7362  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_displayInCS
0x7367  call     instance string [mscorlib]System.Boolean::ToString()
0x736c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x7371  ldarg.1
0x7372  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x7377  ldarg.1
0x7378  ldstr    aDisplayarea// "displayarea"
0x737d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x7382  ldarg.1
0x7383  ldstr    aId// "id"
0x7388  ldstr    aSettings// "Settings"
0x738d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x7392  ldarg.1
0x7393  ldstr    aDisplayed// "displayed"
0x7398  ldarg.0
0x7399  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_displayInSettings
0x739e  call     instance string [mscorlib]System.Boolean::ToString()
0x73a3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x73a8  ldarg.1
0x73a9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x73ae  ldarg.1
0x73af  ldstr    aDisplayarea// "displayarea"
0x73b4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x73b9  ldarg.1
0x73ba  ldstr    aId// "id"
0x73bf  ldstr    aResourcecenter// "ResourceCenter"
0x73c4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x73c9  ldarg.1
0x73ca  ldstr    aDisplayed// "displayed"
0x73cf  ldarg.0
0x73d0  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_displayInResourceCenter
0x73d5  call     instance string [mscorlib]System.Boolean::ToString()
0x73da  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x73df  ldarg.1
0x73e0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x73e5  ldarg.1
0x73e6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x73eb  ret
```
