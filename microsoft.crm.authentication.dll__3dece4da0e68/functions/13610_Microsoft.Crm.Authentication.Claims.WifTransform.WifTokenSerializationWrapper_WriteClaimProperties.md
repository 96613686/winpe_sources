# Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WriteClaimProperties

- ea: `0x13610`
- end: `0x136e0`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WriteClaimProperties`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x134f0`

## callees

- `0x10ef0`
- `0x10f00`
- `0x10f60`
- `0x10f70`
- `0x10ff0`
- `0x13610`

## string_xrefs

- `0x13611`: `dictionaryWriter`

## pseudocode

```c

```

## disassembly

```asm
0x13610  ldarg.0
0x13611  ldstr    aDictionarywrit// "dictionaryWriter"
0x13616  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1361b  ldarg.1
0x1361c  ldstr    aDictionary// "dictionary"
0x13621  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x13626  ldarg.2
0x13627  ldstr    aProperties// "properties"
0x1362c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x13631  ldarg.2
0x13632  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Count()
0x13637  ldc.i4.0
0x13638  ble      loc_136DF
0x1363d  ldarg.0
0x1363e  ldarg.1
0x1363f  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_ClaimProperties()
0x13644  ldarg.1
0x13645  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x1364a  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x1364f  ldarg.2
0x13650  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x13655  stloc.0
0x13656  br.s     loc_136C5
0x13658  ldloc.0
0x13659  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x1365e  stloc.1
0x1365f  ldloca.s 1
0x13661  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x13666  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1366b  brtrue.s loc_136C5
0x1366d  ldloca.s 1
0x1366f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x13674  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13679  brtrue.s loc_136C5
0x1367b  ldarg.0
0x1367c  ldarg.1
0x1367d  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_ClaimProperty()
0x13682  ldarg.1
0x13683  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13688  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x1368d  ldarg.0
0x1368e  ldarg.1
0x1368f  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_ClaimPropertyName()
0x13694  ldarg.1
0x13695  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x1369a  ldloca.s 1
0x1369c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x136a1  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x136a6  ldarg.0
0x136a7  ldarg.1
0x136a8  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_ClaimPropertyValue()
0x136ad  ldarg.1
0x136ae  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x136b3  ldloca.s 1
0x136b5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x136ba  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x136bf  ldarg.0
0x136c0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x136c5  ldloc.0
0x136c6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x136cb  brtrue.s loc_13658
0x136cd  leave.s  loc_136D9
0x136cf  ldloc.0
0x136d0  brfalse.s loc_136D8
0x136d2  ldloc.0
0x136d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x136d8  endfinally
0x136d9  ldarg.0
0x136da  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x136df  ret
```
