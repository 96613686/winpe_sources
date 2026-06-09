# Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadIdentity

- ea: `0x12d40`
- end: `0x12e81`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadIdentity`
- size: `321`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x12cd0`
- `0x12d40`

## callees

- `0x11cf0`
- `0x11d40`
- `0x11e30`
- `0x11e40`
- `0x11e90`
- `0x11ee0`
- `0x11ef0`
- `0x11f00`
- `0x11f50`
- `0x12d40`
- `0x12e90`

## string_xrefs

- `0x12d41`: `dictionaryReader`
- `0x12d8d`: `WindowsClaimsIdentity not supported`

## pseudocode

```c

```

## disassembly

```asm
0x12d40  ldarg.1
0x12d41  ldstr    aDictionaryread// "dictionaryReader"
0x12d46  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12d4b  ldarg.2
0x12d4c  ldstr    aDictionary// "dictionary"
0x12d51  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12d56  ldarg.1
0x12d57  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x12d5c  pop
0x12d5d  ldarg.1
0x12d5e  ldarg.2
0x12d5f  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Identity()
0x12d64  ldarg.2
0x12d65  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12d6a  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12d6f  brfalse  loc_12E54
0x12d74  ldarg.1
0x12d75  ldarg.2
0x12d76  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_WindowsLogOnName()
0x12d7b  ldarg.2
0x12d7c  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12d81  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::GetAttribute(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12d86  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12d8b  brtrue.s loc_12D98
0x12d8d  ldstr    aWindowsclaimsi// "WindowsClaimsIdentity not supported"
0x12d92  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x12d97  throw
0x12d98  ldarg.1
0x12d99  ldarg.2
0x12d9a  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_AuthenticationType()
0x12d9f  ldarg.2
0x12da0  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12da5  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::GetAttribute(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12daa  ldarg.1
0x12dab  ldarg.2
0x12dac  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_NameClaimType()
0x12db1  ldarg.2
0x12db2  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12db7  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::GetAttribute(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12dbc  stloc.0
0x12dbd  ldarg.1
0x12dbe  ldarg.2
0x12dbf  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_RoleClaimType()
0x12dc4  ldarg.2
0x12dc5  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12dca  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::GetAttribute(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12dcf  stloc.1
0x12dd0  ldloc.0
0x12dd1  ldloc.1
0x12dd2  newobj   instance void [mscorlib]System.Security.Claims.ClaimsIdentity::.ctor(string, string, string)
0x12dd7  stloc.2
0x12dd8  ldloc.2
0x12dd9  ldarg.1
0x12dda  ldarg.2
0x12ddb  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Label()
0x12de0  ldarg.2
0x12de1  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12de6  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::GetAttribute(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12deb  callvirt instance void [mscorlib]System.Security.Claims.ClaimsIdentity::set_Label(string)
0x12df0  ldarg.1
0x12df1  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::ReadFullStartElement()
0x12df6  ldarg.1
0x12df7  ldarg.2
0x12df8  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ClaimCollection()
0x12dfd  ldarg.2
0x12dfe  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12e03  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12e08  brfalse.s loc_12E1E
0x12e0a  ldarg.1
0x12e0b  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x12e10  ldarg.1
0x12e11  ldarg.2
0x12e12  ldloc.2
0x12e13  call     void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadClaims(class [System.Runtime.Serialization]System.Xml.XmlDictionaryReader dictionaryReader, class Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary dictionary, class [mscorlib]System.Security.Claims.ClaimsIdentity claimsIdentity)
0x12e18  ldarg.1
0x12e19  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x12e1e  ldarg.1
0x12e1f  ldarg.2
0x12e20  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Actor()
0x12e25  ldarg.2
0x12e26  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12e2b  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12e30  brfalse.s loc_12E4C
0x12e32  ldarg.1
0x12e33  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x12e38  ldloc.2
0x12e39  ldarg.0
0x12e3a  ldarg.1
0x12e3b  ldarg.2
0x12e3c  call     instance class [mscorlib]System.Security.Claims.ClaimsIdentity Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadIdentity(class [System.Runtime.Serialization]System.Xml.XmlDictionaryReader dictionaryReader, class Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary dictionary)
0x12e41  callvirt instance void [mscorlib]System.Security.Claims.ClaimsIdentity::set_Actor(class [mscorlib]System.Security.Claims.ClaimsIdentity)
0x12e46  ldarg.1
0x12e47  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x12e4c  ldarg.1
0x12e4d  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x12e52  ldloc.2
0x12e53  ret
0x12e54  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12e59  ldstr    aTheElement0Wit// "The element '{0}' with namespace '{1}' "...
0x12e5e  ldc.i4.2
0x12e5f  newarr   [mscorlib]System.Object
0x12e64  dup
0x12e65  ldc.i4.0
0x12e66  ldarg.1
0x12e67  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x12e6c  stelem.ref
0x12e6d  dup
0x12e6e  ldc.i4.1
0x12e6f  ldarg.1
0x12e70  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x12e75  stelem.ref
0x12e76  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12e7b  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x12e80  throw
```
