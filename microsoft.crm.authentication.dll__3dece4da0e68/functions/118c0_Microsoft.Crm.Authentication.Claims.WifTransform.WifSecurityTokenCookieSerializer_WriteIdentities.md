# Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WriteIdentities

- ea: `0x118c0`
- end: `0x11926`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WriteIdentities`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x11870`

## callees

- `0x118c0`
- `0x11930`
- `0x11d50`
- `0x11f50`

## string_xrefs

- `0x118c1`: `dictionaryWriter`

## pseudocode

```c

```

## disassembly

```asm
0x118c0  ldarg.0
0x118c1  ldstr    aDictionarywrit// "dictionaryWriter"
0x118c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x118cb  ldarg.1
0x118cc  ldstr    aDictionary// "dictionary"
0x118d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x118d6  ldarg.2
0x118d7  ldstr    aIdentities_0// "identities"
0x118dc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x118e1  ldarg.0
0x118e2  ldarg.1
0x118e3  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Identities()
0x118e8  ldarg.1
0x118e9  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x118ee  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x118f3  ldarg.2
0x118f4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.ClaimsIdentity>::GetEnumerator()
0x118f9  stloc.0
0x118fa  br.s     loc_1190B
0x118fc  ldloc.0
0x118fd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Security.Claims.ClaimsIdentity>::get_Current()
0x11902  stloc.1
0x11903  ldarg.0
0x11904  ldarg.1
0x11905  ldloc.1
0x11906  call     void Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::WriteIdentity(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter dictionaryWriter, class Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary dictionary, class [mscorlib]System.Security.Claims.ClaimsIdentity identity)
0x1190b  ldloc.0
0x1190c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11911  brtrue.s loc_118FC
0x11913  leave.s  loc_1191F
0x11915  ldloc.0
0x11916  brfalse.s loc_1191E
0x11918  ldloc.0
0x11919  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1191e  endfinally
0x1191f  ldarg.0
0x11920  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x11925  ret
```
