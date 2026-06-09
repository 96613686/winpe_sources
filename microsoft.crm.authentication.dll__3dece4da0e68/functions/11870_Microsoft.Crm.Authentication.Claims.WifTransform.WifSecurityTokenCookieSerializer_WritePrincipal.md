# Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WritePrincipal

- ea: `0x11870`
- end: `0x118bf`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WritePrincipal`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x11620`

## callees

- `0x11870`
- `0x118c0`
- `0x11d00`
- `0x11f50`

## string_xrefs

- `0x11871`: `dictionaryWriter`

## pseudocode

```c

```

## disassembly

```asm
0x11870  ldarg.0
0x11871  ldstr    aDictionarywrit// "dictionaryWriter"
0x11876  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1187b  ldarg.1
0x1187c  ldstr    aDictionary// "dictionary"
0x11881  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11886  ldarg.2
0x11887  ldstr    aPrincipal// "principal"
0x1188c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11891  ldarg.0
0x11892  ldarg.1
0x11893  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ClaimsPrincipal()
0x11898  ldarg.1
0x11899  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x1189e  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x118a3  ldarg.2
0x118a4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.ClaimsIdentity> [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identities()
0x118a9  brfalse.s loc_118B8
0x118ab  ldarg.0
0x118ac  ldarg.1
0x118ad  ldarg.2
0x118ae  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.ClaimsIdentity> [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identities()
0x118b3  call     void Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WriteIdentities(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter dictionaryWriter, class Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary dictionary, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.ClaimsIdentity> identities)
0x118b8  ldarg.0
0x118b9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x118be  ret
```
