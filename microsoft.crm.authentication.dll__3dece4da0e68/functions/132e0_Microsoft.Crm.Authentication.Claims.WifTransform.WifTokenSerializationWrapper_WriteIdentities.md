# Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WriteIdentities

- ea: `0x132e0`
- end: `0x13347`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WriteIdentities`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x13290`

## callees

- `0x10e00`
- `0x10ff0`
- `0x132e0`
- `0x13350`

## string_xrefs

- `0x132e1`: `dictionaryWriter`

## pseudocode

```c

```

## disassembly

```asm
0x132e0  ldarg.1
0x132e1  ldstr    aDictionarywrit// "dictionaryWriter"
0x132e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x132eb  ldarg.2
0x132ec  ldstr    aDictionary// "dictionary"
0x132f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x132f6  ldarg.3
0x132f7  ldstr    aIdentities_0// "identities"
0x132fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x13301  ldarg.1
0x13302  ldarg.2
0x13303  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_Identities()
0x13308  ldarg.2
0x13309  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x1330e  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x13313  ldarg.3
0x13314  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.ClaimsIdentity>::GetEnumerator()
0x13319  stloc.0
0x1331a  br.s     loc_1332C
0x1331c  ldloc.0
0x1331d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Security.Claims.ClaimsIdentity>::get_Current()
0x13322  stloc.1
0x13323  ldarg.0
0x13324  ldarg.1
0x13325  ldarg.2
0x13326  ldloc.1
0x13327  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WriteIdentity(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter dictionaryWriter, class Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary dictionary, class [mscorlib]System.Security.Claims.ClaimsIdentity identity)
0x1332c  ldloc.0
0x1332d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13332  brtrue.s loc_1331C
0x13334  leave.s  loc_13340
0x13336  ldloc.0
0x13337  brfalse.s loc_1333F
0x13339  ldloc.0
0x1333a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1333f  endfinally
0x13340  ldarg.1
0x13341  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x13346  ret
```
