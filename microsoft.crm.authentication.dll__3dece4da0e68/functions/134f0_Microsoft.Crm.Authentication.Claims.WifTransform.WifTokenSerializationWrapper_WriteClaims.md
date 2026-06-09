# Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WriteClaims

- ea: `0x134f0`
- end: `0x1360f`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WriteClaims`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x13350`

## callees

- `0x10e90`
- `0x10ea0`
- `0x10eb0`
- `0x10f10`
- `0x10f20`
- `0x10f40`
- `0x10ff0`
- `0x134f0`
- `0x13610`

## string_xrefs

- `0x134f1`: `dictionaryWriter`

## pseudocode

```c

```

## disassembly

```asm
0x134f0  ldarg.0
0x134f1  ldstr    aDictionarywrit// "dictionaryWriter"
0x134f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x134fb  ldarg.1
0x134fc  ldstr    aDictionary// "dictionary"
0x13501  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x13506  ldarg.2
0x13507  ldstr    aClaims// "claims"
0x1350c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x13511  ldarg.2
0x13512  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim>::GetEnumerator()
0x13517  stloc.0
0x13518  br       loc_135F7
0x1351d  ldloc.0
0x1351e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Security.Claims.Claim>::get_Current()
0x13523  stloc.1
0x13524  ldloc.1
0x13525  brfalse  loc_135F7
0x1352a  ldarg.0
0x1352b  ldarg.1
0x1352c  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_Claim()
0x13531  ldarg.1
0x13532  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13537  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x1353c  ldloc.1
0x1353d  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Issuer()
0x13542  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13547  brtrue.s loc_13561
0x13549  ldarg.0
0x1354a  ldarg.1
0x1354b  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_Issuer()
0x13550  ldarg.1
0x13551  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13556  ldloc.1
0x13557  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Issuer()
0x1355c  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x13561  ldloc.1
0x13562  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_OriginalIssuer()
0x13567  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1356c  brtrue.s loc_13586
0x1356e  ldarg.0
0x1356f  ldarg.1
0x13570  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_OriginalIssuer()
0x13575  ldarg.1
0x13576  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x1357b  ldloc.1
0x1357c  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_OriginalIssuer()
0x13581  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x13586  ldarg.0
0x13587  ldarg.1
0x13588  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_Type()
0x1358d  ldarg.1
0x1358e  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13593  ldloc.1
0x13594  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Type()
0x13599  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x1359e  ldarg.0
0x1359f  ldarg.1
0x135a0  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_Value()
0x135a5  ldarg.1
0x135a6  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x135ab  ldloc.1
0x135ac  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x135b1  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x135b6  ldarg.0
0x135b7  ldarg.1
0x135b8  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_ValueType()
0x135bd  ldarg.1
0x135be  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x135c3  ldloc.1
0x135c4  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_ValueType()
0x135c9  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x135ce  ldloc.1
0x135cf  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [mscorlib]System.Security.Claims.Claim::get_Properties()
0x135d4  brfalse.s loc_135F1
0x135d6  ldloc.1
0x135d7  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [mscorlib]System.Security.Claims.Claim::get_Properties()
0x135dc  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Count()
0x135e1  ldc.i4.0
0x135e2  ble.s    loc_135F1
0x135e4  ldarg.0
0x135e5  ldarg.1
0x135e6  ldloc.1
0x135e7  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [mscorlib]System.Security.Claims.Claim::get_Properties()
0x135ec  call     void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WriteClaimProperties(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter dictionaryWriter, class Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary dictionary, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties)
0x135f1  ldarg.0
0x135f2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x135f7  ldloc.0
0x135f8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x135fd  brtrue   loc_1351D
0x13602  leave.s  loc_1360E
0x13604  ldloc.0
0x13605  brfalse.s loc_1360D
0x13607  ldloc.0
0x13608  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1360d  endfinally
0x1360e  ret
```
