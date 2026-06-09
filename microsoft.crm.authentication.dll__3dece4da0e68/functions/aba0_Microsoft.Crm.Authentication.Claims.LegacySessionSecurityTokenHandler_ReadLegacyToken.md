# Microsoft.Crm.Authentication.Claims.LegacySessionSecurityTokenHandler::ReadLegacyToken

- ea: `0xaba0`
- end: `0xad92`
- name: `Microsoft.Crm.Authentication.Claims.LegacySessionSecurityTokenHandler::ReadLegacyToken`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0xab90`

## callees

- `0xaba0`
- `0xada0`

## string_xrefs

- `0xaba1`: `reader`
- `0xabc0`: `SecurityContextToken`
- `0xabe1`: `SecurityContextToken`
- `0xac12`: `SecurityContextToken`
- `0xabc5`: `http://schemas.xmlsoap.org/ws/2005/02/sc`
- `0xabd1`: `http://schemas.xmlsoap.org/ws/2005/02/sc`
- `0xabe6`: `http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512`
- `0xabf2`: `http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512`
- `0xac2a`: `http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd`
- `0xad72`: `Token couldn't be read from cookie`

## pseudocode

```c

```

## disassembly

```asm
0xaba0  ldarg.1
0xaba1  ldstr    aReader// "reader"
0xaba6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xabab  ldnull
0xabac  stloc.0
0xabad  ldnull
0xabae  stloc.1
0xabaf  ldnull
0xabb0  stloc.2
0xabb1  ldnull
0xabb2  stloc.3
0xabb3  ldnull
0xabb4  stloc.s  4
0xabb6  ldarg.1
0xabb7  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReader [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::CreateDictionaryReader(class [System.Xml]System.Xml.XmlReader)
0xabbc  stloc.s  5
0xabbe  ldloc.s  5
0xabc0  ldstr    aSecuritycontex// "SecurityContextToken"
0xabc5  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/ws/2005/02/s"...
0xabca  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement(string, string)
0xabcf  brfalse.s loc_ABDF
0xabd1  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/ws/2005/02/s"...
0xabd6  stloc.2
0xabd7  ldstr    aIdentifier// "Identifier"
0xabdc  stloc.3
0xabdd  br.s     loc_AC23
0xabdf  ldloc.s  5
0xabe1  ldstr    aSecuritycontex// "SecurityContextToken"
0xabe6  ldstr    aHttpDocsOasisO// "http://docs.oasis-open.org/ws-sx/ws-sec"...
0xabeb  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement(string, string)
0xabf0  brfalse.s loc_AC00
0xabf2  ldstr    aHttpDocsOasisO// "http://docs.oasis-open.org/ws-sx/ws-sec"...
0xabf7  stloc.2
0xabf8  ldstr    aIdentifier// "Identifier"
0xabfd  stloc.3
0xabfe  br.s     loc_AC23
0xac00  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xac05  ldstr    aExpected0Eleme// "Expected {0} element."
0xac0a  ldc.i4.1
0xac0b  newarr   [mscorlib]System.Object
0xac10  dup
0xac11  ldc.i4.0
0xac12  ldstr    aSecuritycontex// "SecurityContextToken"
0xac17  stelem.ref
0xac18  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xac1d  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0xac22  throw
0xac23  ldloc.s  5
0xac25  ldstr    aId// "Id"
0xac2a  ldstr    aHttpDocsOasisO_0// "http://docs.oasis-open.org/wss/2004/01/"...
0xac2f  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string, string)
0xac34  stloc.s  6
0xac36  ldloc.s  5
0xac38  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::ReadFullStartElement()
0xac3d  ldloc.s  5
0xac3f  ldloc.3
0xac40  ldloc.2
0xac41  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement(string, string)
0xac46  brtrue.s loc_AC67
0xac48  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xac4d  ldstr    aExpected0Eleme// "Expected {0} element."
0xac52  ldc.i4.1
0xac53  newarr   [mscorlib]System.Object
0xac58  dup
0xac59  ldc.i4.0
0xac5a  ldloc.3
0xac5b  stelem.ref
0xac5c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xac61  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0xac66  throw
0xac67  ldloc.s  5
0xac69  callvirt instance class [System.Runtime.Serialization]System.Xml.UniqueId [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::ReadElementContentAsUniqueId()
0xac6e  stloc.1
0xac6f  ldloc.1
0xac70  ldnull
0xac71  call     bool [System.Runtime.Serialization]System.Xml.UniqueId::op_Equality(class [System.Runtime.Serialization]System.Xml.UniqueId, class [System.Runtime.Serialization]System.Xml.UniqueId)
0xac76  brtrue.s loc_AC85
0xac78  ldloc.1
0xac79  callvirt instance string [mscorlib]System.Object::ToString()
0xac7e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xac83  brfalse.s loc_AC90
0xac85  ldstr    aExpectedContex// "Expected ContextId to be present"
0xac8a  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0xac8f  throw
0xac90  ldloc.s  5
0xac92  ldstr    aInstance// "Instance"
0xac97  ldloc.2
0xac98  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement(string, string)
0xac9d  brfalse.s loc_ACA7
0xac9f  ldloc.s  5
0xaca1  callvirt instance class [System.Runtime.Serialization]System.Xml.UniqueId [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::ReadElementContentAsUniqueId()
0xaca6  pop
0xaca7  ldloc.s  5
0xaca9  ldarg.0
0xacaa  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler::get_CookieElementName()
0xacaf  ldarg.0
0xacb0  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler::get_CookieNamespace()
0xacb5  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement(string, string)
0xacba  brfalse  loc_AD67
0xacbf  ldloc.s  5
0xacc1  callvirt instance unsigned int8[] [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::ReadElementContentAsBase64()
0xacc6  stloc.0
0xacc7  ldloc.0
0xacc8  brtrue.s loc_ACD5
0xacca  ldstr    aExpectedCookie// "Expected cookie body"
0xaccf  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0xacd4  throw
0xacd5  ldarg.0
0xacd6  ldloc.0
0xacd7  ldc.i4.0
0xacd8  callvirt instance unsigned int8[] [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler::ApplyTransforms(unsigned int8[], bool)
0xacdd  call     class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.Crm.Authentication.Claims.LegacySessionSecurityTokenHandler::DeserializeLegacyToken(unsigned int8[] cookie)
0xace2  stloc.s  4
0xace4  ldloc.s  4
0xace6  isinst   [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken
0xaceb  stloc.s  7
0xaced  ldloc.s  7
0xacef  brfalse.s loc_AD29
0xacf1  ldloc.s  7
0xacf3  callvirt instance class [System.Runtime.Serialization]System.Xml.UniqueId [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_ContextId()
0xacf8  ldloc.1
0xacf9  call     bool [System.Runtime.Serialization]System.Xml.UniqueId::op_Inequality(class [System.Runtime.Serialization]System.Xml.UniqueId, class [System.Runtime.Serialization]System.Xml.UniqueId)
0xacfe  brfalse.s loc_AD29
0xad00  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xad05  ldstr    aTheSessionId0F// "The session Id '{0}' found in the cooki"...
0xad0a  ldc.i4.2
0xad0b  newarr   [mscorlib]System.Object
0xad10  dup
0xad11  ldc.i4.0
0xad12  ldloc.s  7
0xad14  callvirt instance class [System.Runtime.Serialization]System.Xml.UniqueId [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_ContextId()
0xad19  stelem.ref
0xad1a  dup
0xad1b  ldc.i4.1
0xad1c  ldloc.1
0xad1d  stelem.ref
0xad1e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xad23  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0xad28  throw
0xad29  ldloc.s  7
0xad2b  brfalse.s loc_AD67
0xad2d  ldloc.s  7
0xad2f  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xad34  ldloc.s  6
0xad36  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xad3b  brfalse.s loc_AD67
0xad3d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xad42  ldstr    aTheSessionId0F// "The session Id '{0}' found in the cooki"...
0xad47  ldc.i4.2
0xad48  newarr   [mscorlib]System.Object
0xad4d  dup
0xad4e  ldc.i4.0
0xad4f  ldloc.s  7
0xad51  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xad56  stelem.ref
0xad57  dup
0xad58  ldc.i4.1
0xad59  ldloc.s  6
0xad5b  stelem.ref
0xad5c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xad61  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0xad66  throw
0xad67  ldloc.s  5
0xad69  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0xad6e  ldloc.s  4
0xad70  brtrue.s loc_AD7D
0xad72  ldstr    aTokenCouldnTBe// "Token couldn't be read from cookie"
0xad77  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0xad7c  throw
0xad7d  ldloc.s  4
0xad7f  stloc.s  8
0xad81  leave.s  loc_AD8F
0xad83  ldloc.s  5
0xad85  brfalse.s loc_AD8E
0xad87  ldloc.s  5
0xad89  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xad8e  endfinally
0xad8f  ldloc.s  8
0xad91  ret
```
