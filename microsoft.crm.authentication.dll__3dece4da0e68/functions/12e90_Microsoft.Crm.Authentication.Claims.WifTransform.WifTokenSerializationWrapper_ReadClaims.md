# Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadClaims

- ea: `0x12e90`
- end: `0x12f6d`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadClaims`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x12d40`

## callees

- `0x11de0`
- `0x11e00`
- `0x11e10`
- `0x11e50`
- `0x11e70`
- `0x11e80`
- `0x11ea0`
- `0x11f50`
- `0x12e90`
- `0x12f70`

## string_xrefs

- `0x12e91`: `dictionaryReader`
- `0x12ea7`: `claimsIdentity`

## pseudocode

```c

```

## disassembly

```asm
0x12e90  ldarg.0
0x12e91  ldstr    aDictionaryread// "dictionaryReader"
0x12e96  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12e9b  ldarg.1
0x12e9c  ldstr    aDictionary// "dictionary"
0x12ea1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12ea6  ldarg.2
0x12ea7  ldstr    aClaimsidentity_12// "claimsIdentity"
0x12eac  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12eb1  br       loc_12F55
0x12eb6  ldarg.0
0x12eb7  ldarg.1
0x12eb8  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Type()
0x12ebd  ldarg.1
0x12ebe  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12ec3  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::GetAttribute(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12ec8  ldarg.0
0x12ec9  ldarg.1
0x12eca  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Value()
0x12ecf  ldarg.1
0x12ed0  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12ed5  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::GetAttribute(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12eda  stloc.0
0x12edb  ldarg.0
0x12edc  ldarg.1
0x12edd  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ValueType()
0x12ee2  ldarg.1
0x12ee3  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12ee8  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::GetAttribute(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12eed  stloc.1
0x12eee  ldarg.0
0x12eef  ldarg.1
0x12ef0  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Issuer()
0x12ef5  ldarg.1
0x12ef6  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12efb  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::GetAttribute(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12f00  stloc.2
0x12f01  ldarg.0
0x12f02  ldarg.1
0x12f03  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_OriginalIssuer()
0x12f08  ldarg.1
0x12f09  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12f0e  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::GetAttribute(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12f13  stloc.3
0x12f14  ldloc.0
0x12f15  ldloc.1
0x12f16  ldloc.2
0x12f17  ldloc.3
0x12f18  newobj   instance void [mscorlib]System.Security.Claims.Claim::.ctor(string, string, string, string, string)
0x12f1d  stloc.s  4
0x12f1f  ldarg.0
0x12f20  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::ReadFullStartElement()
0x12f25  ldarg.0
0x12f26  ldarg.1
0x12f27  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ClaimProperties()
0x12f2c  ldarg.1
0x12f2d  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12f32  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12f37  brfalse.s loc_12F47
0x12f39  ldarg.0
0x12f3a  ldarg.1
0x12f3b  ldloc.s  4
0x12f3d  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [mscorlib]System.Security.Claims.Claim::get_Properties()
0x12f42  call     void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadClaimProperties(class [System.Runtime.Serialization]System.Xml.XmlDictionaryReader dictionaryReader, class Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary dictionary, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties)
0x12f47  ldarg.0
0x12f48  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x12f4d  ldarg.2
0x12f4e  ldloc.s  4
0x12f50  callvirt instance void [mscorlib]System.Security.Claims.ClaimsIdentity::AddClaim(class [mscorlib]System.Security.Claims.Claim)
0x12f55  ldarg.0
0x12f56  ldarg.1
0x12f57  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Claim()
0x12f5c  ldarg.1
0x12f5d  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12f62  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12f67  brtrue   loc_12EB6
0x12f6c  ret
```
