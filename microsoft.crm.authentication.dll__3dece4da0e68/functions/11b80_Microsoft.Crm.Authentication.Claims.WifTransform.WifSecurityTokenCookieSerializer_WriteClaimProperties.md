# Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WriteClaimProperties

- ea: `0x11b80`
- end: `0x11c34`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WriteClaimProperties`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x11a60`

## callees

- `0x11b80`
- `0x11e50`
- `0x11e60`
- `0x11ec0`
- `0x11ed0`
- `0x11f50`

## string_xrefs

- `0x11b81`: `dictionaryWriter`

## pseudocode

```c

```

## disassembly

```asm
0x11b80  ldarg.0
0x11b81  ldstr    aDictionarywrit// "dictionaryWriter"
0x11b86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11b8b  ldarg.1
0x11b8c  ldstr    aDictionary// "dictionary"
0x11b91  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11b96  ldarg.2
0x11b97  ldstr    aProperties// "properties"
0x11b9c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11ba1  ldarg.2
0x11ba2  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Count()
0x11ba7  ldc.i4.0
0x11ba8  ble      loc_11C33
0x11bad  ldarg.0
0x11bae  ldarg.1
0x11baf  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ClaimProperties()
0x11bb4  ldarg.1
0x11bb5  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x11bba  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x11bbf  ldarg.2
0x11bc0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x11bc5  stloc.0
0x11bc6  br.s     loc_11C19
0x11bc8  ldloc.0
0x11bc9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x11bce  stloc.1
0x11bcf  ldarg.0
0x11bd0  ldarg.1
0x11bd1  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ClaimProperty()
0x11bd6  ldarg.1
0x11bd7  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x11bdc  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x11be1  ldarg.0
0x11be2  ldarg.1
0x11be3  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ClaimPropertyName()
0x11be8  ldarg.1
0x11be9  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x11bee  ldloca.s 1
0x11bf0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x11bf5  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x11bfa  ldarg.0
0x11bfb  ldarg.1
0x11bfc  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ClaimPropertyValue()
0x11c01  ldarg.1
0x11c02  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x11c07  ldloca.s 1
0x11c09  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x11c0e  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x11c13  ldarg.0
0x11c14  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x11c19  ldloc.0
0x11c1a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11c1f  brtrue.s loc_11BC8
0x11c21  leave.s  loc_11C2D
0x11c23  ldloc.0
0x11c24  brfalse.s loc_11C2C
0x11c26  ldloc.0
0x11c27  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11c2c  endfinally
0x11c2d  ldarg.0
0x11c2e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x11c33  ret
```
