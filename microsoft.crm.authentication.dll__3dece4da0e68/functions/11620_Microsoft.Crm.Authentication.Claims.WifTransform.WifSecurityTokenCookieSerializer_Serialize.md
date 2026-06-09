# Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::Serialize

- ea: `0x11620`
- end: `0x11869`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::Serialize`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0xade0`

## callees

- `0x11620`
- `0x11870`
- `0x11cd0`
- `0x11ce0`
- `0x11da0`
- `0x11db0`
- `0x11dc0`
- `0x11dd0`
- `0x11f30`
- `0x11f40`
- `0x11f50`
- `0x11f60`
- `0x11f70`
- `0x11f80`
- `0x11f90`
- `0x11fa0`
- `0x11fd0`
- `0x12000`
- `0x13930`
- `0x13950`

## string_xrefs

- `0x11621`: `sessionToken`

## pseudocode

```c

```

## disassembly

```asm
0x11620  ldarg.1
0x11621  ldstr    aSessiontoken_0// "sessionToken"
0x11626  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1162b  call     class Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Instance()
0x11630  stloc.0
0x11631  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x11636  stloc.1
0x11637  ldloc.1
0x11638  ldloc.0
0x11639  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::CreateBinaryWriter(class [mscorlib]System.IO.Stream, class [System.Runtime.Serialization]System.Xml.IXmlDictionary)
0x1163e  stloc.2
0x1163f  ldloc.2
0x11640  ldloc.0
0x11641  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_SessionToken()
0x11646  ldloc.0
0x11647  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x1164c  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x11651  ldarg.1
0x11652  callvirt instance bool [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_IsPersistent()
0x11657  brfalse.s loc_11670
0x11659  ldloc.2
0x1165a  ldloc.0
0x1165b  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_PersistentTrue()
0x11660  ldloc.0
0x11661  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x11666  ldstr    asc_1DBD8// ""
0x1166b  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x11670  ldarg.1
0x11671  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_Context()
0x11676  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1167b  brtrue.s loc_11695
0x1167d  ldloc.2
0x1167e  ldloc.0
0x1167f  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Context()
0x11684  ldloc.0
0x11685  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x1168a  ldarg.1
0x1168b  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_Context()
0x11690  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteElementString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x11695  ldloc.2
0x11696  ldloc.0
0x11697  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Version()
0x1169c  ldloc.0
0x1169d  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x116a2  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x116a7  ldloc.2
0x116a8  ldstr    a1// "1"
0x116ad  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x116b2  ldloc.2
0x116b3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x116b8  ldloc.2
0x116b9  ldloc.0
0x116ba  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_SecureConversationVersion()
0x116bf  ldloc.0
0x116c0  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x116c5  ldarg.1
0x116c6  callvirt instance class [System]System.Uri [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_SecureConversationVersion()
0x116cb  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x116d0  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteElementString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x116d5  ldloc.2
0x116d6  ldloc.0
0x116d7  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Id()
0x116dc  ldloc.0
0x116dd  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x116e2  ldarg.1
0x116e3  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0x116e8  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteElementString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x116ed  ldloc.2
0x116ee  ldloc.0
0x116ef  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ContextId()
0x116f4  ldloc.0
0x116f5  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x116fa  ldarg.1
0x116fb  callvirt instance class [System.Runtime.Serialization]System.Xml.UniqueId [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_ContextId()
0x11700  callvirt instance string [mscorlib]System.Object::ToString()
0x11705  call     void Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::WriteElementStringAsUniqueId(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter writer, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString localName, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString ns, string id)
0x1170a  ldarg.1
0x1170b  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey> [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_SecurityKeys()
0x11710  ldc.i4.0
0x11711  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey>::get_Item(!!T0)
0x11716  castclass [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey
0x1171b  callvirt instance unsigned int8[] [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey::GetSymmetricKey()
0x11720  stloc.3
0x11721  ldloc.2
0x11722  ldloc.0
0x11723  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Key()
0x11728  ldloc.0
0x11729  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x1172e  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x11733  ldloc.2
0x11734  ldloc.3
0x11735  ldc.i4.0
0x11736  ldloc.3
0x11737  ldlen
0x11738  conv.i4
0x11739  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteBase64(unsigned int8[], int32, int32)
0x1173e  ldloc.2
0x1173f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x11744  ldarg.1
0x11745  callvirt instance class [System.Runtime.Serialization]System.Xml.UniqueId [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_KeyGeneration()
0x1174a  ldnull
0x1174b  call     bool [System.Runtime.Serialization]System.Xml.UniqueId::op_Inequality(class [System.Runtime.Serialization]System.Xml.UniqueId, class [System.Runtime.Serialization]System.Xml.UniqueId)
0x11750  brfalse.s loc_1176F
0x11752  ldloc.2
0x11753  ldloc.0
0x11754  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_KeyGeneration()
0x11759  ldloc.0
0x1175a  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x1175f  ldarg.1
0x11760  callvirt instance class [System.Runtime.Serialization]System.Xml.UniqueId [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_KeyGeneration()
0x11765  callvirt instance string [mscorlib]System.Object::ToString()
0x1176a  call     void Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::WriteElementStringAsUniqueId(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter writer, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString localName, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString ns, string id)
0x1176f  ldloc.2
0x11770  ldloc.0
0x11771  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EffectiveTime()
0x11776  ldloc.0
0x11777  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x1177c  ldarg.1
0x1177d  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0x11782  stloc.s  4
0x11784  ldloca.s 4
0x11786  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x1178b  stloc.s  4
0x1178d  ldloca.s 4
0x1178f  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x11794  call     void Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::WriteElementContentAsInt64(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter writer, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString localName, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString ns, int64 value)
0x11799  ldloc.2
0x1179a  ldloc.0
0x1179b  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ExpiryTime()
0x117a0  ldloc.0
0x117a1  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x117a6  ldarg.1
0x117a7  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0x117ac  stloc.s  4
0x117ae  ldloca.s 4
0x117b0  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x117b5  stloc.s  4
0x117b7  ldloca.s 4
0x117b9  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x117be  call     void Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::WriteElementContentAsInt64(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter writer, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString localName, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString ns, int64 value)
0x117c3  ldloc.2
0x117c4  ldloc.0
0x117c5  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_KeyEffectiveTime()
0x117ca  ldloc.0
0x117cb  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x117d0  ldarg.1
0x117d1  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_KeyEffectiveTime()
0x117d6  stloc.s  4
0x117d8  ldloca.s 4
0x117da  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x117df  stloc.s  4
0x117e1  ldloca.s 4
0x117e3  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x117e8  call     void Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::WriteElementContentAsInt64(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter writer, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString localName, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString ns, int64 value)
0x117ed  ldloc.2
0x117ee  ldloc.0
0x117ef  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_KeyExpiryTime()
0x117f4  ldloc.0
0x117f5  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x117fa  ldarg.1
0x117fb  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_KeyExpirationTime()
0x11800  stloc.s  4
0x11802  ldloca.s 4
0x11804  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x11809  stloc.s  4
0x1180b  ldloca.s 4
0x1180d  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x11812  call     void Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::WriteElementContentAsInt64(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter writer, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString localName, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString ns, int64 value)
0x11817  ldloc.2
0x11818  ldloc.0
0x11819  ldarg.1
0x1181a  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x1181f  call     void Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WritePrincipal(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter dictionaryWriter, class Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary dictionary, class [mscorlib]System.Security.Claims.ClaimsPrincipal principal)
0x11824  ldloc.2
0x11825  ldloc.0
0x11826  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EndpointId()
0x1182b  ldloc.0
0x1182c  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x11831  ldarg.1
0x11832  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_EndpointId()
0x11837  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteElementString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x1183c  ldloc.2
0x1183d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x11842  ldloc.2
0x11843  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x11848  ldloc.1
0x11849  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::ToArray()
0x1184e  stloc.s  5
0x11850  leave.s  loc_11866
0x11852  ldloc.2
0x11853  brfalse.s loc_1185B
0x11855  ldloc.2
0x11856  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1185b  endfinally
0x1185c  ldloc.1
0x1185d  brfalse.s loc_11865
0x1185f  ldloc.1
0x11860  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11865  endfinally
0x11866  ldloc.s  5
0x11868  ret
```
