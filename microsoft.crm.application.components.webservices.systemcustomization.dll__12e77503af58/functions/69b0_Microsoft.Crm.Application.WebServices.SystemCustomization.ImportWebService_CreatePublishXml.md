# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreatePublishXml

- ea: `0x69b0`
- end: `0x6a16`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreatePublishXml`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6900`

## callees

- `0x69b0`

## pseudocode

```c

```

## disassembly

```asm
0x69b0  ldstr    aPublishEntitie// "<publish><entities></entities></publish"...
0x69b5  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x69ba  stloc.0
0x69bb  ldloc.0
0x69bc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x69c1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x69c6  stloc.1
0x69c7  ldarg.1
0x69c8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x69cd  stloc.2
0x69ce  br.s     loc_69F6
0x69d0  ldloca.s 2
0x69d2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x69d7  stloc.3
0x69d8  ldloc.0
0x69d9  ldstr    aEntity_0// "Entity"
0x69de  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x69e3  stloc.s  4
0x69e5  ldloc.s  4
0x69e7  ldloc.3
0x69e8  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x69ed  ldloc.1
0x69ee  ldloc.s  4
0x69f0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x69f5  pop
0x69f6  ldloca.s 2
0x69f8  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x69fd  brtrue.s loc_69D0
0x69ff  leave.s  loc_6A0F
0x6a01  ldloca.s 2
0x6a03  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x6a09  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a0e  endfinally
0x6a0f  ldloc.0
0x6a10  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x6a15  ret
```
