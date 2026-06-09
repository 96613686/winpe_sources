# Microsoft.Crm.Application.WebServices.ParameterBag::GetNodeArray

- ea: `0x110`
- end: `0x187`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetNodeArray`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c0`

## callees

- `0x110`

## pseudocode

```c

```

## disassembly

```asm
0x110  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x115  stloc.0
0x116  ldarg.0
0x117  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.ParameterBag::_parameterBag
0x11c  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x121  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x126  stloc.1
0x127  br.s     loc_14B
0x129  ldloc.1
0x12a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x12f  castclass [System.Xml]System.Xml.XmlNode
0x134  stloc.2
0x135  ldloc.2
0x136  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x13b  ldarg.1
0x13c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x141  brfalse.s loc_14B
0x143  ldloc.0
0x144  ldloc.2
0x145  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x14a  pop
0x14b  ldloc.1
0x14c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x151  brtrue.s loc_129
0x153  leave.s  loc_166
0x155  ldloc.1
0x156  isinst   [mscorlib]System.IDisposable
0x15b  stloc.3
0x15c  ldloc.3
0x15d  brfalse.s loc_165
0x15f  ldloc.3
0x160  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x165  endfinally
0x166  ldloc.0
0x167  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x16c  ldc.i4.0
0x16d  bgt.s    loc_171
0x16f  ldnull
0x170  ret
0x171  ldloc.0
0x172  ldtoken  [System.Xml]System.Xml.XmlNode
0x177  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17c  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x181  castclass class [System.Xml]System.Xml.XmlNode[]
0x186  ret
```
