# Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WritePrincipal

- ea: `0x13290`
- end: `0x132e0`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WritePrincipal`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x13020`

## callees

- `0x10dc0`
- `0x10ff0`
- `0x13290`
- `0x132e0`

## string_xrefs

- `0x13291`: `dictionaryWriter`

## pseudocode

```c

```

## disassembly

```asm
0x13290  ldarg.1
0x13291  ldstr    aDictionarywrit// "dictionaryWriter"
0x13296  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1329b  ldarg.2
0x1329c  ldstr    aDictionary// "dictionary"
0x132a1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x132a6  ldarg.3
0x132a7  ldstr    aPrincipal// "principal"
0x132ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x132b1  ldarg.1
0x132b2  ldarg.2
0x132b3  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_ClaimsPrincipal()
0x132b8  ldarg.2
0x132b9  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x132be  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x132c3  ldarg.3
0x132c4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.ClaimsIdentity> [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identities()
0x132c9  brfalse.s loc_132D9
0x132cb  ldarg.0
0x132cc  ldarg.1
0x132cd  ldarg.2
0x132ce  ldarg.3
0x132cf  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.ClaimsIdentity> [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identities()
0x132d4  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WriteIdentities(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter dictionaryWriter, class Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary dictionary, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.ClaimsIdentity> identities)
0x132d9  ldarg.1
0x132da  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x132df  ret
```
