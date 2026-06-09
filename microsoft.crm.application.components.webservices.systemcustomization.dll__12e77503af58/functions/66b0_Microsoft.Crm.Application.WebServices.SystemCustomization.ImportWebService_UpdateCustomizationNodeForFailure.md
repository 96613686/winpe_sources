# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateCustomizationNodeForFailure

- ea: `0x66b0`
- end: `0x6733`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateCustomizationNodeForFailure`
- size: `131`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x5ea0`
- `0x5ed0`
- `0x6240`

## pseudocode

```c

```

## disassembly

```asm
0x66b0  ldarg.2
0x66b1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x66b6  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::.ctor(class [mscorlib]System.Exception, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x66bb  stloc.0
0x66bc  ldarg.1
0x66bd  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x66c2  ldstr    aCustomizatione// "CustomizationError"
0x66c7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x66cc  stloc.1
0x66cd  ldarg.1
0x66ce  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x66d3  ldstr    aErrorcode// "ErrorCode"
0x66d8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x66dd  stloc.2
0x66de  ldloc.2
0x66df  ldloc.0
0x66e0  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_ErrorCode()
0x66e5  stloc.s  4
0x66e7  ldloca.s 4
0x66e9  ldstr    aX// "X"
0x66ee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x66f3  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x66f8  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x66fd  ldloc.1
0x66fe  ldloc.2
0x66ff  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6704  pop
0x6705  ldarg.1
0x6706  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x670b  ldstr    aErrormessage// "ErrorMessage"
0x6710  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6715  stloc.3
0x6716  ldloc.3
0x6717  ldloc.0
0x6718  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_DisplayText()
0x671d  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x6722  ldloc.1
0x6723  ldloc.3
0x6724  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6729  pop
0x672a  ldarg.1
0x672b  ldloc.1
0x672c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6731  pop
0x6732  ret
```
