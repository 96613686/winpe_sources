# Microsoft.Crm.Application.WebServices.ParameterBag::GetNode

- ea: `0x70`
- end: `0x10f`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetNode`
- size: `159`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x190`
- `0x1a0`
- `0x200`

## callees

- `0x70`

## pseudocode

```c

```

## disassembly

```asm
0x70  ldarg.0
0x71  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.ParameterBag::_parameterBag
0x76  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x7b  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNamedNodeMap::GetEnumerator()
0x80  stloc.0
0x81  br.s     loc_A1
0x83  ldloc.0
0x84  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x89  castclass [System.Xml]System.Xml.XmlNode
0x8e  stloc.1
0x8f  ldloc.1
0x90  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x95  ldarg.1
0x96  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9b  brfalse.s loc_A1
0x9d  ldloc.1
0x9e  stloc.2
0x9f  leave.s  loc_10D
0xa1  ldloc.0
0xa2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa7  brtrue.s loc_83
0xa9  leave.s  loc_BC
0xab  ldloc.0
0xac  isinst   [mscorlib]System.IDisposable
0xb1  stloc.3
0xb2  ldloc.3
0xb3  brfalse.s loc_BB
0xb5  ldloc.3
0xb6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbb  endfinally
0xbc  ldarg.0
0xbd  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.ParameterBag::_parameterBag
0xc2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0xc7  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xcc  stloc.0
0xcd  br.s     loc_F0
0xcf  ldloc.0
0xd0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xd5  castclass [System.Xml]System.Xml.XmlNode
0xda  stloc.s  4
0xdc  ldloc.s  4
0xde  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xe3  ldarg.1
0xe4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe9  brfalse.s loc_F0
0xeb  ldloc.s  4
0xed  stloc.2
0xee  leave.s  loc_10D
0xf0  ldloc.0
0xf1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf6  brtrue.s loc_CF
0xf8  leave.s  loc_10B
0xfa  ldloc.0
0xfb  isinst   [mscorlib]System.IDisposable
0x100  stloc.3
0x101  ldloc.3
0x102  brfalse.s loc_10A
0x104  ldloc.3
0x105  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10a  endfinally
0x10b  ldnull
0x10c  ret
0x10d  ldloc.2
0x10e  ret
```
