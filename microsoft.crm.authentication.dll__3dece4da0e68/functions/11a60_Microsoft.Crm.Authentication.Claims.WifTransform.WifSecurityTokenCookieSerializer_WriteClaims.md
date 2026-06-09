# Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WriteClaims

- ea: `0x11a60`
- end: `0x11b7f`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WriteClaims`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x11930`

## callees

- `0x11a60`
- `0x11b80`
- `0x11de0`
- `0x11e00`
- `0x11e10`
- `0x11e70`
- `0x11e80`
- `0x11ea0`
- `0x11f50`

## string_xrefs

- `0x11a61`: `dictionaryWriter`

## pseudocode

```c

```

## disassembly

```asm
0x11a60  ldarg.0
0x11a61  ldstr    aDictionarywrit// "dictionaryWriter"
0x11a66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11a6b  ldarg.1
0x11a6c  ldstr    aDictionary// "dictionary"
0x11a71  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11a76  ldarg.2
0x11a77  ldstr    aClaims// "claims"
0x11a7c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11a81  ldarg.2
0x11a82  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim>::GetEnumerator()
0x11a87  stloc.0
0x11a88  br       loc_11B67
0x11a8d  ldloc.0
0x11a8e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Security.Claims.Claim>::get_Current()
0x11a93  stloc.1
0x11a94  ldloc.1
0x11a95  brfalse  loc_11B67
0x11a9a  ldarg.0
0x11a9b  ldarg.1
0x11a9c  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Claim()
0x11aa1  ldarg.1
0x11aa2  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x11aa7  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x11aac  ldloc.1
0x11aad  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Issuer()
0x11ab2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11ab7  brtrue.s loc_11AD1
0x11ab9  ldarg.0
0x11aba  ldarg.1
0x11abb  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Issuer()
0x11ac0  ldarg.1
0x11ac1  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x11ac6  ldloc.1
0x11ac7  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Issuer()
0x11acc  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x11ad1  ldloc.1
0x11ad2  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_OriginalIssuer()
0x11ad7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11adc  brtrue.s loc_11AF6
0x11ade  ldarg.0
0x11adf  ldarg.1
0x11ae0  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_OriginalIssuer()
0x11ae5  ldarg.1
0x11ae6  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x11aeb  ldloc.1
0x11aec  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_OriginalIssuer()
0x11af1  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x11af6  ldarg.0
0x11af7  ldarg.1
0x11af8  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Type()
0x11afd  ldarg.1
0x11afe  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x11b03  ldloc.1
0x11b04  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Type()
0x11b09  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x11b0e  ldarg.0
0x11b0f  ldarg.1
0x11b10  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Value()
0x11b15  ldarg.1
0x11b16  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x11b1b  ldloc.1
0x11b1c  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x11b21  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x11b26  ldarg.0
0x11b27  ldarg.1
0x11b28  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ValueType()
0x11b2d  ldarg.1
0x11b2e  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x11b33  ldloc.1
0x11b34  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_ValueType()
0x11b39  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x11b3e  ldloc.1
0x11b3f  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [mscorlib]System.Security.Claims.Claim::get_Properties()
0x11b44  brfalse.s loc_11B61
0x11b46  ldloc.1
0x11b47  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [mscorlib]System.Security.Claims.Claim::get_Properties()
0x11b4c  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Count()
0x11b51  ldc.i4.0
0x11b52  ble.s    loc_11B61
0x11b54  ldarg.0
0x11b55  ldarg.1
0x11b56  ldloc.1
0x11b57  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [mscorlib]System.Security.Claims.Claim::get_Properties()
0x11b5c  call     void Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WriteClaimProperties(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter dictionaryWriter, class Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary dictionary, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties)
0x11b61  ldarg.0
0x11b62  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x11b67  ldloc.0
0x11b68  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11b6d  brtrue   loc_11A8D
0x11b72  leave.s  loc_11B7E
0x11b74  ldloc.0
0x11b75  brfalse.s loc_11B7D
0x11b77  ldloc.0
0x11b78  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11b7d  endfinally
0x11b7e  ret
```
