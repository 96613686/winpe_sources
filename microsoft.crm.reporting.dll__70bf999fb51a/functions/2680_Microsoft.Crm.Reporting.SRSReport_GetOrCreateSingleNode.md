# Microsoft.Crm.Reporting.SRSReport::GetOrCreateSingleNode

- ea: `0x2680`
- end: `0x26ed`
- name: `Microsoft.Crm.Reporting.SRSReport::GetOrCreateSingleNode`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2460`
- `0x27d0`

## callees

- `0x2680`

## pseudocode

```c

```

## disassembly

```asm
0x2680  ldnull
0x2681  stloc.0
0x2682  ldarg.1
0x2683  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x2688  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x268d  stloc.1
0x268e  br.s     loc_26BC
0x2690  ldloc.1
0x2691  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2696  castclass [System.Xml]System.Xml.XmlNode
0x269b  stloc.2
0x269c  ldloc.2
0x269d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_NamespaceURI()
0x26a2  ldarg.3
0x26a3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26a8  brfalse.s loc_26BC
0x26aa  ldloc.2
0x26ab  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x26b0  ldarg.2
0x26b1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26b6  brfalse.s loc_26BC
0x26b8  ldloc.2
0x26b9  stloc.0
0x26ba  leave.s  loc_26D7
0x26bc  ldloc.1
0x26bd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26c2  brtrue.s loc_2690
0x26c4  leave.s  loc_26D7
0x26c6  ldloc.1
0x26c7  isinst   [mscorlib]System.IDisposable
0x26cc  stloc.3
0x26cd  ldloc.3
0x26ce  brfalse.s loc_26D6
0x26d0  ldloc.3
0x26d1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26d6  endfinally
0x26d7  ldloc.0
0x26d8  brtrue.s loc_26EB
0x26da  ldarg.0
0x26db  ldarg.2
0x26dc  ldarg.3
0x26dd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0x26e2  stloc.0
0x26e3  ldarg.1
0x26e4  ldloc.0
0x26e5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x26ea  pop
0x26eb  ldloc.0
0x26ec  ret
```
