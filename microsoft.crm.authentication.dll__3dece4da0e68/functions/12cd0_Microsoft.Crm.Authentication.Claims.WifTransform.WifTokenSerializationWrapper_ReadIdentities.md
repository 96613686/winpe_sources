# Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadIdentities

- ea: `0x12cd0`
- end: `0x12d3d`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadIdentities`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x12c70`

## callees

- `0x11d40`
- `0x11d50`
- `0x11f50`
- `0x12cd0`
- `0x12d40`

## string_xrefs

- `0x12cd1`: `dictionaryReader`

## pseudocode

```c

```

## disassembly

```asm
0x12cd0  ldarg.1
0x12cd1  ldstr    aDictionaryread// "dictionaryReader"
0x12cd6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12cdb  ldarg.2
0x12cdc  ldstr    aDictionary// "dictionary"
0x12ce1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12ce6  ldarg.3
0x12ce7  ldstr    aIdentities_0// "identities"
0x12cec  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12cf1  ldarg.1
0x12cf2  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x12cf7  pop
0x12cf8  ldarg.1
0x12cf9  ldarg.2
0x12cfa  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Identities()
0x12cff  ldarg.2
0x12d00  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12d05  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12d0a  brfalse.s loc_12D3C
0x12d0c  ldarg.1
0x12d0d  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::ReadFullStartElement()
0x12d12  br.s     loc_12D22
0x12d14  ldarg.3
0x12d15  ldarg.0
0x12d16  ldarg.1
0x12d17  ldarg.2
0x12d18  call     instance class [mscorlib]System.Security.Claims.ClaimsIdentity Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadIdentity(class [System.Runtime.Serialization]System.Xml.XmlDictionaryReader dictionaryReader, class Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary dictionary)
0x12d1d  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [mscorlib]System.Security.Claims.ClaimsIdentity>::Add(var<u1>)
0x12d22  ldarg.1
0x12d23  ldarg.2
0x12d24  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Identity()
0x12d29  ldarg.2
0x12d2a  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12d2f  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12d34  brtrue.s loc_12D14
0x12d36  ldarg.1
0x12d37  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x12d3c  ret
```
