# XmlSchemaObjectComparer::GetObjectText

- ea: `0x10060`
- end: `0x100e2`
- name: `XmlSchemaObjectComparer::GetObjectText`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10030`

## callees

- `0x10060`

## pseudocode

```c

```

## disassembly

```asm
0x10060  ldarg.1
0x10061  isinst   [System.Xml]System.Xml.Schema.XmlSchemaImport
0x10066  stloc.0
0x10067  ldloc.0
0x10068  brfalse.s loc_1007B
0x1006a  ldstr    a1_0// "1."
0x1006f  ldloc.0
0x10070  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaImport::get_Namespace()
0x10075  call     string [mscorlib]System.String::Concat(string, string)
0x1007a  ret
0x1007b  ldarg.1
0x1007c  isinst   [System.Xml]System.Xml.Schema.XmlSchemaElement
0x10081  stloc.1
0x10082  ldloc.1
0x10083  brfalse.s loc_10096
0x10085  ldstr    a2_0// "2."
0x1008a  ldloc.1
0x1008b  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaElement::get_Name()
0x10090  call     string [mscorlib]System.String::Concat(string, string)
0x10095  ret
0x10096  ldarg.1
0x10097  isinst   [System.Xml]System.Xml.Schema.XmlSchemaAttribute
0x1009c  stloc.2
0x1009d  ldloc.2
0x1009e  brfalse.s loc_100B1
0x100a0  ldstr    a3// "3."
0x100a5  ldloc.2
0x100a6  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaAttribute::get_Name()
0x100ab  call     string [mscorlib]System.String::Concat(string, string)
0x100b0  ret
0x100b1  ldarg.1
0x100b2  isinst   [System.Xml]System.Xml.Schema.XmlSchemaType
0x100b7  stloc.3
0x100b8  ldloc.3
0x100b9  brfalse.s loc_100CC
0x100bb  ldstr    a4// "4."
0x100c0  ldloc.3
0x100c1  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaType::get_Name()
0x100c6  call     string [mscorlib]System.String::Concat(string, string)
0x100cb  ret
0x100cc  ldstr    a9// "9."
0x100d1  ldarg.1
0x100d2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x100d7  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x100dc  call     string [mscorlib]System.String::Concat(string, string)
0x100e1  ret
```
