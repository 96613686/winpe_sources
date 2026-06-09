# Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WriteIdentity

- ea: `0x11930`
- end: `0x11a5d`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WriteIdentity`
- size: `301`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x118c0`
- `0x11930`

## callees

- `0x11930`
- `0x11a60`
- `0x11d40`
- `0x11e30`
- `0x11e40`
- `0x11e90`
- `0x11ee0`
- `0x11ef0`
- `0x11f00`
- `0x11f50`

## string_xrefs

- `0x11931`: `dictionaryWriter`

## pseudocode

```c

```

## disassembly

```asm
0x11930  ldarg.0
0x11931  ldstr    aDictionarywrit// "dictionaryWriter"
0x11936  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1193b  ldarg.1
0x1193c  ldstr    aDictionary// "dictionary"
0x11941  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11946  ldarg.2
0x11947  ldstr    aIdentity_0// "identity"
0x1194c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11951  ldarg.0
0x11952  ldarg.1
0x11953  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Identity()
0x11958  ldarg.1
0x11959  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x1195e  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x11963  ldarg.2
0x11964  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_AuthenticationType()
0x11969  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1196e  brtrue.s loc_11988
0x11970  ldarg.0
0x11971  ldarg.1
0x11972  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_AuthenticationType()
0x11977  ldarg.1
0x11978  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x1197d  ldarg.2
0x1197e  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_AuthenticationType()
0x11983  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x11988  ldarg.2
0x11989  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Label()
0x1198e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11993  brtrue.s loc_119AD
0x11995  ldarg.0
0x11996  ldarg.1
0x11997  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Label()
0x1199c  ldarg.1
0x1199d  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x119a2  ldarg.2
0x119a3  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Label()
0x119a8  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x119ad  ldarg.2
0x119ae  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_NameClaimType()
0x119b3  brfalse.s loc_119CD
0x119b5  ldarg.0
0x119b6  ldarg.1
0x119b7  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_NameClaimType()
0x119bc  ldarg.1
0x119bd  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x119c2  ldarg.2
0x119c3  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_NameClaimType()
0x119c8  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x119cd  ldarg.2
0x119ce  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_RoleClaimType()
0x119d3  brfalse.s loc_119ED
0x119d5  ldarg.0
0x119d6  ldarg.1
0x119d7  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_RoleClaimType()
0x119dc  ldarg.1
0x119dd  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x119e2  ldarg.2
0x119e3  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_RoleClaimType()
0x119e8  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x119ed  ldarg.2
0x119ee  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [mscorlib]System.Security.Claims.ClaimsIdentity::get_Claims()
0x119f3  brfalse.s loc_11A29
0x119f5  ldarg.2
0x119f6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [mscorlib]System.Security.Claims.ClaimsIdentity::get_Claims()
0x119fb  call     T0x2B000028
0x11a00  brfalse.s loc_11A29
0x11a02  ldarg.0
0x11a03  ldarg.1
0x11a04  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ClaimCollection()
0x11a09  ldarg.1
0x11a0a  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x11a0f  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x11a14  ldarg.2
0x11a15  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [mscorlib]System.Security.Claims.ClaimsIdentity::get_Claims()
0x11a1a  stloc.0
0x11a1b  ldarg.0
0x11a1c  ldarg.1
0x11a1d  ldloc.0
0x11a1e  call     void Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WriteClaims(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter dictionaryWriter, class Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary dictionary, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> claims)
0x11a23  ldarg.0
0x11a24  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x11a29  ldarg.2
0x11a2a  callvirt instance class [mscorlib]System.Security.Claims.ClaimsIdentity [mscorlib]System.Security.Claims.ClaimsIdentity::get_Actor()
0x11a2f  brfalse.s loc_11A56
0x11a31  ldarg.0
0x11a32  ldarg.1
0x11a33  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Actor()
0x11a38  ldarg.1
0x11a39  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x11a3e  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x11a43  ldarg.0
0x11a44  ldarg.1
0x11a45  ldarg.2
0x11a46  callvirt instance class [mscorlib]System.Security.Claims.ClaimsIdentity [mscorlib]System.Security.Claims.ClaimsIdentity::get_Actor()
0x11a4b  call     void Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WriteIdentity(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter dictionaryWriter, class Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary dictionary, class [mscorlib]System.Security.Claims.ClaimsIdentity identity)
0x11a50  ldarg.0
0x11a51  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x11a56  ldarg.0
0x11a57  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x11a5c  ret
```
