# Microsoft.Crm.BusinessEntities.SoapContext::SerializeRawRequest

- ea: `0x78c30`
- end: `0x78ec3`
- name: `Microsoft.Crm.BusinessEntities.SoapContext::SerializeRawRequest`
- size: `659`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x78ed0`
- `0x79020`

## callees

- `0x67c10`
- `0x78640`
- `0x78c30`

## string_xrefs

- `0x78c85`: `http://schemas.xmlsoap.org/soap/envelope/`
- `0x78cc7`: `http://schemas.xmlsoap.org/soap/envelope/`
- `0x78d99`: `http://schemas.xmlsoap.org/soap/envelope/`
- `0x78c91`: `xmlns:xsi`
- `0x78e21`: `xmlns:xsi`
- `0x78c9d`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x78e84`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x78cde`: `CrmAuthenticationToken`
- `0x78ce3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x78dba`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x78de3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x78cfe`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x78d26`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x78d5e`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x78e15`: `xmlns:xsd`

## pseudocode

```c

```

## disassembly

```asm
0x78c30  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x78c35  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x78c3a  stloc.s  8
0x78c3c  ldarg.0
0x78c3d  call     instance object Microsoft.Crm.BusinessEntities.SoapContext::get_RawRequest()
0x78c42  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x78c47  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x78c4c  ldloc.s  8
0x78c4e  ldarg.0
0x78c4f  call     instance object Microsoft.Crm.BusinessEntities.SoapContext::get_RawRequest()
0x78c54  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [mscorlib]System.IO.TextWriter, object)
0x78c59  ldloc.s  8
0x78c5b  callvirt instance string [mscorlib]System.Object::ToString()
0x78c60  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x78c65  stloc.0
0x78c66  leave.s  loc_78C74
0x78c68  ldloc.s  8
0x78c6a  brfalse.s loc_78C73
0x78c6c  ldloc.s  8
0x78c6e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x78c73  endfinally
0x78c74  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x78c79  stloc.1
0x78c7a  ldloc.1
0x78c7b  ldstr    aSoap// "soap"
0x78c80  ldstr    aEnvelope// "Envelope"
0x78c85  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/envelop"...
0x78c8a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x78c8f  stloc.2
0x78c90  ldloc.1
0x78c91  ldstr    aXmlnsXsi// "xmlns:xsi"
0x78c96  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x78c9b  stloc.3
0x78c9c  ldloc.3
0x78c9d  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema-instan"...
0x78ca2  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x78ca7  ldloc.2
0x78ca8  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x78cad  ldloc.3
0x78cae  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x78cb3  pop
0x78cb4  ldloc.1
0x78cb5  ldloc.2
0x78cb6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x78cbb  pop
0x78cbc  ldloc.1
0x78cbd  ldstr    aSoap// "soap"
0x78cc2  ldstr    aHeader// "Header"
0x78cc7  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/envelop"...
0x78ccc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x78cd1  stloc.s  4
0x78cd3  ldloc.2
0x78cd4  ldloc.s  4
0x78cd6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x78cdb  pop
0x78cdc  ldloc.1
0x78cdd  ldnull
0x78cde  ldstr    aCrmauthenticat// "CrmAuthenticationToken"
0x78ce3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x78ce8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x78ced  stloc.2
0x78cee  ldloc.s  4
0x78cf0  ldloc.2
0x78cf1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x78cf6  pop
0x78cf7  ldloc.1
0x78cf8  ldnull
0x78cf9  ldstr    aAuthentication_2// "AuthenticationType"
0x78cfe  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x78d03  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x78d08  stloc.s  4
0x78d0a  ldloc.s  4
0x78d0c  ldstr    a0_3// "0"
0x78d11  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x78d16  ldloc.2
0x78d17  ldloc.s  4
0x78d19  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x78d1e  pop
0x78d1f  ldloc.1
0x78d20  ldnull
0x78d21  ldstr    aOrganizationna// "OrganizationName"
0x78d26  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x78d2b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x78d30  stloc.s  4
0x78d32  ldloc.s  4
0x78d34  ldarg.1
0x78d35  brtrue.s loc_78D3E
0x78d37  ldsfld   string [mscorlib]System.String::Empty
0x78d3c  br.s     loc_78D49
0x78d3e  ldarg.1
0x78d3f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_RootPluginContext()
0x78d44  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationName()
0x78d49  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x78d4e  ldloc.2
0x78d4f  ldloc.s  4
0x78d51  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x78d56  pop
0x78d57  ldloc.1
0x78d58  ldnull
0x78d59  ldstr    aCallerid_0// "CallerId"
0x78d5e  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x78d63  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x78d68  stloc.s  4
0x78d6a  ldloc.s  4
0x78d6c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x78d71  stloc.s  9
0x78d73  ldloca.s 9
0x78d75  constrained. [mscorlib]System.Guid
0x78d7b  callvirt instance string [mscorlib]System.Object::ToString()
0x78d80  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x78d85  ldloc.2
0x78d86  ldloc.s  4
0x78d88  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x78d8d  pop
0x78d8e  ldloc.1
0x78d8f  ldstr    aSoap// "soap"
0x78d94  ldstr    aBody// "Body"
0x78d99  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/envelop"...
0x78d9e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x78da3  stloc.s  4
0x78da5  ldloc.1
0x78da6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x78dab  ldloc.s  4
0x78dad  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x78db2  pop
0x78db3  ldloc.1
0x78db4  ldnull
0x78db5  ldstr    aExecute// "Execute"
0x78dba  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x78dbf  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x78dc4  stloc.2
0x78dc5  ldloc.s  4
0x78dc7  ldloc.2
0x78dc8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x78dcd  pop
0x78dce  ldloc.1
0x78dcf  ldloc.0
0x78dd0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x78dd5  ldc.i4.1
0x78dd6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x78ddb  stloc.s  5
0x78ddd  ldloc.1
0x78dde  ldstr    aRequest// "Request"
0x78de3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x78de8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0x78ded  stloc.s  4
0x78def  ldloc.s  4
0x78df1  ldloc.s  5
0x78df3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x78df8  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x78dfd  ldloc.2
0x78dfe  ldloc.s  4
0x78e00  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x78e05  pop
0x78e06  ldloc.s  5
0x78e08  isinst   [System.Xml]System.Xml.XmlElement
0x78e0d  stloc.s  6
0x78e0f  ldloc.s  6
0x78e11  brfalse.s loc_78E2B
0x78e13  ldloc.s  6
0x78e15  ldstr    aXmlnsXsd// "xmlns:xsd"
0x78e1a  callvirt instance void [System.Xml]System.Xml.XmlElement::RemoveAttribute(string)
0x78e1f  ldloc.s  6
0x78e21  ldstr    aXmlnsXsi// "xmlns:xsi"
0x78e26  callvirt instance void [System.Xml]System.Xml.XmlElement::RemoveAttribute(string)
0x78e2b  ldloc.s  5
0x78e2d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x78e32  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNamedNodeMap::GetEnumerator()
0x78e37  stloc.s  0xA
0x78e39  br.s     loc_78E5E
0x78e3b  ldloc.s  0xA
0x78e3d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x78e42  castclass [System.Xml]System.Xml.XmlAttribute
0x78e47  stloc.s  0xB
0x78e49  ldloc.s  4
0x78e4b  ldloc.s  0xB
0x78e4d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x78e52  ldloc.s  0xB
0x78e54  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x78e59  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x78e5e  ldloc.s  0xA
0x78e60  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x78e65  brtrue.s loc_78E3B
0x78e67  leave.s  loc_78E7E
0x78e69  ldloc.s  0xA
0x78e6b  isinst   [mscorlib]System.IDisposable
0x78e70  stloc.s  0xC
0x78e72  ldloc.s  0xC
0x78e74  brfalse.s loc_78E7D
0x78e76  ldloc.s  0xC
0x78e78  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x78e7d  endfinally
0x78e7e  ldloc.1
0x78e7f  ldstr    aXsiType// "xsi:type"
0x78e84  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema-instan"...
0x78e89  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0x78e8e  stloc.s  7
0x78e90  ldloc.s  7
0x78e92  ldarg.0
0x78e93  call     instance object Microsoft.Crm.BusinessEntities.SoapContext::get_RawRequest()
0x78e98  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x78e9d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x78ea2  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x78ea7  ldloc.s  4
0x78ea9  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x78eae  ldloc.s  7
0x78eb0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x78eb5  pop
0x78eb6  ldarg.0
0x78eb7  ldloc.1
0x78eb8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x78ebd  stfld    string Microsoft.Crm.BusinessEntities.SoapContext::_soapXml
0x78ec2  ret
```
