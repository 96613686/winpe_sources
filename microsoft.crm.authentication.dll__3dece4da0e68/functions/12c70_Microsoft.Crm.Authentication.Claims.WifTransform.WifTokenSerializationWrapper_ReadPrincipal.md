# Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadPrincipal

- ea: `0x12c70`
- end: `0x12cc9`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadPrincipal`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x127a0`

## callees

- `0x11d00`
- `0x11f50`
- `0x12c70`
- `0x12cd0`

## string_xrefs

- `0x12c71`: `dictionaryReader`

## pseudocode

```c

```

## disassembly

```asm
0x12c70  ldarg.1
0x12c71  ldstr    aDictionaryread// "dictionaryReader"
0x12c76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12c7b  ldarg.2
0x12c7c  ldstr    aDictionary// "dictionary"
0x12c81  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12c86  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Security.Claims.ClaimsIdentity>::.ctor()
0x12c8b  stloc.0
0x12c8c  ldarg.1
0x12c8d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x12c92  pop
0x12c93  ldarg.1
0x12c94  ldarg.2
0x12c95  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ClaimsPrincipal()
0x12c9a  ldarg.2
0x12c9b  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12ca0  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12ca5  brfalse.s loc_12CBC
0x12ca7  ldarg.1
0x12ca8  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::ReadFullStartElement()
0x12cad  ldarg.0
0x12cae  ldarg.1
0x12caf  ldarg.2
0x12cb0  ldloc.0
0x12cb1  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadIdentities(class [System.Runtime.Serialization]System.Xml.XmlDictionaryReader dictionaryReader, class Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary dictionary, class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.Security.Claims.ClaimsIdentity> identities)
0x12cb6  ldarg.1
0x12cb7  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x12cbc  newobj   instance void [mscorlib]System.Security.Claims.ClaimsPrincipal::.ctor()
0x12cc1  dup
0x12cc2  ldloc.0
0x12cc3  callvirt instance void [mscorlib]System.Security.Claims.ClaimsPrincipal::AddIdentities(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.ClaimsIdentity>)
0x12cc8  ret
```
