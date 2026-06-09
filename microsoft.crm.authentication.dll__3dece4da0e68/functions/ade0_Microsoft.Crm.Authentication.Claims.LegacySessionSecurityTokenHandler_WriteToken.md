# Microsoft.Crm.Authentication.Claims.LegacySessionSecurityTokenHandler::WriteToken

- ea: `0xade0`
- end: `0xaf81`
- name: `Microsoft.Crm.Authentication.Claims.LegacySessionSecurityTokenHandler::WriteToken`
- size: `417`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xade0`
- `0xaf90`
- `0x11620`

## string_xrefs

- `0xadec`: `token`
- `0xae4f`: `SecurityContextToken`
- `0xae96`: `SecurityContextToken`
- `0xae49`: `http://schemas.xmlsoap.org/ws/2005/02/sc`
- `0xae90`: `http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512`
- `0xaed3`: `http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd`
- `0xade1`: `writer`
- `0xae05`: `The SecurityTokenHandler cannot write the token '{0}'. The SecurityTokenHandler can only write tokens of type '{1}'.`
- `0xae85`: `The SecurityContextSecurityTokenHandler requires a valid WS-SecureConversation version when writing a token.`

## pseudocode

```c

```

## disassembly

```asm
0xade0  ldarg.1
0xade1  ldstr    aWriter// "writer"
0xade6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xadeb  ldarg.2
0xadec  ldstr    aToken// "token"
0xadf1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xadf6  ldarg.2
0xadf7  isinst   [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken
0xadfc  stloc.0
0xadfd  ldloc.0
0xadfe  brtrue.s loc_AE28
0xae00  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xae05  ldstr    aTheSecuritytok// "The SecurityTokenHandler cannot write t"...
0xae0a  ldc.i4.2
0xae0b  newarr   [mscorlib]System.Object
0xae10  dup
0xae11  ldc.i4.0
0xae12  ldarg.2
0xae13  stelem.ref
0xae14  dup
0xae15  ldc.i4.1
0xae16  ldarg.0
0xae17  callvirt instance class [mscorlib]System.Type [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler::get_TokenType()
0xae1c  stelem.ref
0xae1d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xae22  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xae27  throw
0xae28  ldloc.0
0xae29  callvirt instance class [System]System.Uri [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_SecureConversationVersion()
0xae2e  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xae33  call     class [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion::get_WSSecureConversationFeb2005()
0xae38  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion::get_Namespace()
0xae3d  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryString::get_Value()
0xae42  call     bool [mscorlib]System.String::op_Equality(string, string)
0xae47  brfalse.s loc_AE64
0xae49  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/ws/2005/02/s"...
0xae4e  stloc.1
0xae4f  ldstr    aSecuritycontex// "SecurityContextToken"
0xae54  stloc.2
0xae55  ldstr    aIdentifier// "Identifier"
0xae5a  stloc.3
0xae5b  ldstr    aInstance// "Instance"
0xae60  stloc.s  4
0xae62  br.s     loc_AEA9
0xae64  ldloc.0
0xae65  callvirt instance class [System]System.Uri [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_SecureConversationVersion()
0xae6a  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xae6f  call     class [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion::get_WSSecureConversation13()
0xae74  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion::get_Namespace()
0xae79  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryString::get_Value()
0xae7e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xae83  brfalse.s loc_AE90
0xae85  ldstr    aTheSecuritycon// "The SecurityContextSecurityTokenHandler"...
0xae8a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xae8f  throw
0xae90  ldstr    aHttpDocsOasisO// "http://docs.oasis-open.org/ws-sx/ws-sec"...
0xae95  stloc.1
0xae96  ldstr    aSecuritycontex// "SecurityContextToken"
0xae9b  stloc.2
0xae9c  ldstr    aIdentifier// "Identifier"
0xaea1  stloc.3
0xaea2  ldstr    aInstance// "Instance"
0xaea7  stloc.s  4
0xaea9  ldarg.1
0xaeaa  isinst   [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter
0xaeaf  dup
0xaeb0  brtrue.s loc_AEB9
0xaeb2  pop
0xaeb3  ldarg.1
0xaeb4  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::CreateDictionaryWriter(class [System.Xml]System.Xml.XmlWriter)
0xaeb9  stloc.s  5
0xaebb  ldloc.s  5
0xaebd  ldloc.2
0xaebe  ldloc.1
0xaebf  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xaec4  ldloc.0
0xaec5  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xaeca  brfalse.s loc_AEE3
0xaecc  ldloc.s  5
0xaece  ldstr    aId// "Id"
0xaed3  ldstr    aHttpDocsOasisO_0// "http://docs.oasis-open.org/wss/2004/01/"...
0xaed8  ldloc.0
0xaed9  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xaede  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string)
0xaee3  ldloc.s  5
0xaee5  ldloc.3
0xaee6  ldloc.1
0xaee7  ldloc.0
0xaee8  callvirt instance class [System.Runtime.Serialization]System.Xml.UniqueId [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_ContextId()
0xaeed  callvirt instance string [mscorlib]System.Object::ToString()
0xaef2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string, string)
0xaef7  ldloc.0
0xaef8  callvirt instance class [System.Runtime.Serialization]System.Xml.UniqueId [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_KeyGeneration()
0xaefd  ldnull
0xaefe  call     bool [System.Runtime.Serialization]System.Xml.UniqueId::op_Inequality(class [System.Runtime.Serialization]System.Xml.UniqueId, class [System.Runtime.Serialization]System.Xml.UniqueId)
0xaf03  brfalse.s loc_AF23
0xaf05  ldloc.s  5
0xaf07  ldloc.s  4
0xaf09  ldloc.1
0xaf0a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xaf0f  ldloc.s  5
0xaf11  ldloc.0
0xaf12  callvirt instance class [System.Runtime.Serialization]System.Xml.UniqueId [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_KeyGeneration()
0xaf17  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteValue(class [System.Runtime.Serialization]System.Xml.UniqueId)
0xaf1c  ldloc.s  5
0xaf1e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xaf23  ldloc.s  5
0xaf25  ldarg.0
0xaf26  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler::get_CookieElementName()
0xaf2b  ldarg.0
0xaf2c  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler::get_CookieNamespace()
0xaf31  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xaf36  ldarg.0
0xaf37  call     instance class Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer Microsoft.Crm.Authentication.Claims.LegacySessionSecurityTokenHandler::CreateCookieSerializer()
0xaf3c  ldloc.0
0xaf3d  callvirt instance unsigned int8[] Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::Serialize(class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken sessionToken)
0xaf42  stloc.s  6
0xaf44  ldarg.0
0xaf45  ldloc.s  6
0xaf47  ldc.i4.1
0xaf48  callvirt instance unsigned int8[] [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler::ApplyTransforms(unsigned int8[], bool)
0xaf4d  stloc.s  6
0xaf4f  ldloc.s  5
0xaf51  ldloc.s  6
0xaf53  ldc.i4.0
0xaf54  ldloc.s  6
0xaf56  ldlen
0xaf57  conv.i4
0xaf58  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteBase64(unsigned int8[], int32, int32)
0xaf5d  ldloc.s  5
0xaf5f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xaf64  ldloc.s  5
0xaf66  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xaf6b  ldloc.s  5
0xaf6d  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0xaf72  leave.s  loc_AF80
0xaf74  ldloc.s  5
0xaf76  brfalse.s loc_AF7F
0xaf78  ldloc.s  5
0xaf7a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaf7f  endfinally
0xaf80  ret
```
