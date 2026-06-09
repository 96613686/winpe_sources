# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateMapXmlForPublishFailure

- ea: `0x6880`
- end: `0x68fe`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateMapXmlForPublishFailure`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x6900`
- `0x6960`

## pseudocode

```c

```

## disassembly

```asm
0x6880  ldarg.2
0x6881  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6886  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::.ctor(class [mscorlib]System.Exception, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x688b  stloc.0
0x688c  ldarg.1
0x688d  ldstr    aPublisherror// "PublishError"
0x6892  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6897  stloc.1
0x6898  ldarg.1
0x6899  ldstr    aErrorcode// "ErrorCode"
0x689e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x68a3  stloc.2
0x68a4  ldloc.2
0x68a5  ldloc.0
0x68a6  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_ErrorCode()
0x68ab  stloc.s  4
0x68ad  ldloca.s 4
0x68af  ldstr    aX// "X"
0x68b4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x68b9  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x68be  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x68c3  ldloc.1
0x68c4  ldloc.2
0x68c5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x68ca  pop
0x68cb  ldarg.1
0x68cc  ldstr    aErrormessage// "ErrorMessage"
0x68d1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x68d6  stloc.3
0x68d7  ldloc.3
0x68d8  ldloc.0
0x68d9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_DisplayText()
0x68de  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x68e3  ldloc.1
0x68e4  ldloc.3
0x68e5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x68ea  pop
0x68eb  ldarg.1
0x68ec  ldstr    aMapCustomizati_0// "/Map/Customizations"
0x68f1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x68f6  ldloc.1
0x68f7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x68fc  pop
0x68fd  ret
```
