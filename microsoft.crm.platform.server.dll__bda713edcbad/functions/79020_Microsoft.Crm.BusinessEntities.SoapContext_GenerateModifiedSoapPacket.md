# Microsoft.Crm.BusinessEntities.SoapContext::GenerateModifiedSoapPacket

- ea: `0x79020`
- end: `0x7928b`
- name: `Microsoft.Crm.BusinessEntities.SoapContext::GenerateModifiedSoapPacket`
- size: `619`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x785f0`
- `0x78640`
- `0x78c30`
- `0x79000`
- `0x79020`
- `0x79320`

## string_xrefs

- `0x790a3`: `http://schemas.xmlsoap.org/soap/envelope/`
- `0x790d6`: `http://schemas.xmlsoap.org/soap/envelope/`
- `0x790ec`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x790b3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x79142`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x79152`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x790e1`: `xmlns`
- `0x790f7`: `xmlns`
- `0x79102`: `http://www.w3.org/2001/XMLSchema`
- `0x791cc`: `http://schemas.microsoft.com/crm/2006/WebServices`
- `0x791e0`: `http://schemas.microsoft.com/crm/2006/WebServices`
- `0x79280`: `2007/CrmService.asmx`

## pseudocode

```c

```

## disassembly

```asm
0x79020  ldarg.1
0x79021  ldstr    aEntity_0// "entity"
0x79026  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7902b  ldarg.2
0x7902c  ldstr    aRequestname// "requestName"
0x79031  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x79036  ldarg.3
0x79037  ldstr    aTargetname// "targetName"
0x7903c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x79041  ldarg.0
0x79042  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest Microsoft.Crm.BusinessEntities.SoapContext::_request
0x79047  brfalse.s loc_7905B
0x79049  ldarg.0
0x7904a  call     instance bool Microsoft.Crm.BusinessEntities.SoapContext::get_IsEmpty()
0x7904f  brfalse.s loc_7905A
0x79051  ldarg.0
0x79052  ldarg.1
0x79053  ldarg.s  4
0x79055  call     instance void Microsoft.Crm.BusinessEntities.SoapContext::SerializeRequestWithEntity(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity dynamicEntity, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext context)
0x7905a  ret
0x7905b  ldarg.0
0x7905c  call     instance bool Microsoft.Crm.BusinessEntities.SoapContext::get_IsEmpty()
0x79061  brfalse.s loc_79072
0x79063  ldarg.0
0x79064  call     instance object Microsoft.Crm.BusinessEntities.SoapContext::get_RawRequest()
0x79069  brfalse.s loc_79072
0x7906b  ldarg.0
0x7906c  ldnull
0x7906d  call     instance void Microsoft.Crm.BusinessEntities.SoapContext::SerializeRawRequest(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x79072  ldarg.0
0x79073  call     instance bool Microsoft.Crm.BusinessEntities.SoapContext::get_IsEmpty()
0x79078  ldc.i4.0
0x79079  ceq
0x7907b  ldstr    aSoapPacketIsNo// "Soap Packet is not stored on Execution "...
0x79080  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x79085  ldarg.0
0x79086  ldfld    string Microsoft.Crm.BusinessEntities.SoapContext::_soapXml
0x7908b  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x79090  stloc.0
0x79091  ldloc.0
0x79092  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x79097  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x7909c  stloc.1
0x7909d  ldloc.1
0x7909e  ldstr    aSoap// "soap"
0x790a3  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/envelop"...
0x790a8  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x790ad  ldloc.1
0x790ae  ldstr    aCrmns// "crmns"
0x790b3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x790b8  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x790bd  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x790c2  stloc.2
0x790c3  ldarg.0
0x790c4  ldloc.2
0x790c5  call     instance class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.BusinessEntities.SoapContext::GetXmlWriter(class [mscorlib]System.IO.Stream stream)
0x790ca  stloc.3
0x790cb  ldloc.3
0x790cc  ldstr    aSoap// "soap"
0x790d1  ldstr    aEnvelope// "Envelope"
0x790d6  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/envelop"...
0x790db  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x790e0  ldloc.3
0x790e1  ldstr    aXmlns// "xmlns"
0x790e6  ldstr    aXsi// "xsi"
0x790eb  ldnull
0x790ec  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema-instan"...
0x790f1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x790f6  ldloc.3
0x790f7  ldstr    aXmlns// "xmlns"
0x790fc  ldstr    aXsd// "xsd"
0x79101  ldnull
0x79102  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x79107  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x7910c  ldloc.0
0x7910d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x79112  ldstr    aSoapEnvelopeSo// "/soap:Envelope/soap:Header"
0x79117  ldloc.1
0x79118  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x7911d  stloc.s  4
0x7911f  ldloc.s  4
0x79121  brfalse.s loc_7912B
0x79123  ldloc.s  4
0x79125  ldloc.3
0x79126  callvirt instance void [System.Xml]System.Xml.XmlNode::WriteTo(class [System.Xml]System.Xml.XmlWriter)
0x7912b  ldloc.3
0x7912c  ldstr    aSoap// "soap"
0x79131  ldstr    aBody// "Body"
0x79136  ldnull
0x79137  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x7913c  ldloc.3
0x7913d  ldstr    aExecute// "Execute"
0x79142  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x79147  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x7914c  ldloc.3
0x7914d  ldstr    aRequest// "Request"
0x79152  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x79157  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x7915c  ldloc.3
0x7915d  ldstr    aXsi// "xsi"
0x79162  ldstr    aType// "type"
0x79167  ldnull
0x79168  ldarg.2
0x79169  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x7916e  ldloc.0
0x7916f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x79174  ldstr    aSoapEnvelopeSo_0// "/soap:Envelope/soap:Body/crmns:Execute/"...
0x79179  ldloc.1
0x7917a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x7917f  stloc.s  5
0x79181  ldloc.s  5
0x79183  brfalse.s loc_7918D
0x79185  ldloc.s  5
0x79187  ldloc.3
0x79188  callvirt instance void [System.Xml]System.Xml.XmlNode::WriteTo(class [System.Xml]System.Xml.XmlWriter)
0x7918d  ldloc.3
0x7918e  ldstr    aTarget_0// "Target"
0x79193  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x79198  ldloc.3
0x79199  ldstr    aXsi// "xsi"
0x7919e  ldstr    aType// "type"
0x791a3  ldnull
0x791a4  ldarg.3
0x791a5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x791aa  ldloc.3
0x791ab  ldstr    aEntity// "Entity"
0x791b0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x791b5  ldloc.3
0x791b6  ldstr    aName_2// "Name"
0x791bb  ldarg.1
0x791bc  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity::get_Name()
0x791c1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x791c6  ldloc.3
0x791c7  ldstr    aProperties// "Properties"
0x791cc  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/crm/2006/W"...
0x791d1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x791d6  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Property
0x791db  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x791e0  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/crm/2006/W"...
0x791e5  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type, string)
0x791ea  stloc.s  6
0x791ec  ldarg.1
0x791ed  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyCollection [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity::get_Properties()
0x791f2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Property>::GetEnumerator()
0x791f7  stloc.s  7
0x791f9  br.s     loc_7920E
0x791fb  ldloc.s  7
0x791fd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Property>::get_Current()
0x79202  stloc.s  8
0x79204  ldloc.s  6
0x79206  ldloc.3
0x79207  ldloc.s  8
0x79209  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [System.Xml]System.Xml.XmlWriter, object)
0x7920e  ldloc.s  7
0x79210  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x79215  brtrue.s loc_791FB
0x79217  leave.s  loc_79225
0x79219  ldloc.s  7
0x7921b  brfalse.s loc_79224
0x7921d  ldloc.s  7
0x7921f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x79224  endfinally
0x79225  ldloc.3
0x79226  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndDocument()
0x7922b  ldloc.3
0x7922c  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x79231  leave.s  loc_7923D
0x79233  ldloc.3
0x79234  brfalse.s loc_7923C
0x79236  ldloc.3
0x79237  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7923c  endfinally
0x7923d  ldloc.2
0x7923e  ldc.i4.0
0x7923f  conv.i8
0x79240  ldc.i4.0
0x79241  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x79246  pop
0x79247  ldloc.2
0x79248  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x7924d  stloc.s  9
0x7924f  ldarg.0
0x79250  ldloc.s  9
0x79252  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x79257  stfld    string Microsoft.Crm.BusinessEntities.SoapContext::_soapXml
0x7925c  leave.s  loc_79274
0x7925e  ldloc.s  9
0x79260  brfalse.s loc_79269
0x79262  ldloc.s  9
0x79264  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x79269  endfinally
0x7926a  ldloc.2
0x7926b  brfalse.s loc_79273
0x7926d  ldloc.2
0x7926e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x79273  endfinally
0x79274  ldarg.0
0x79275  ldsfld   string Microsoft.Crm.BusinessEntities.SoapContext::executeSOAPAction
0x7927a  stfld    string Microsoft.Crm.BusinessEntities.SoapContext::_httpHeader
0x7927f  ldarg.0
0x79280  ldstr    a2007Crmservice// "2007/CrmService.asmx"
0x79285  stfld    string Microsoft.Crm.BusinessEntities.SoapContext::_endpoint
0x7928a  ret
```
