# Microsoft.Crm.Application.RowDescriptor::IsRowOnlyContainsMultipleRowControl

- ea: `0x20170`
- end: `0x201f0`
- name: `Microsoft.Crm.Application.RowDescriptor::IsRowOnlyContainsMultipleRowControl`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x20080`

## callees

- `0x20170`

## string_xrefs

- `0x201a5`: `classid`
- `0x20173`: `cell/control[@classid]`

## pseudocode

```c

```

## disassembly

```asm
0x20170  ldc.i4.0
0x20171  stloc.0
0x20172  ldarg.1
0x20173  ldstr    aCellControlCla_0// "cell/control[@classid]"
0x20178  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x2017d  stloc.1
0x2017e  ldloc.1
0x2017f  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x20184  ldc.i4.0
0x20185  ble.s    loc_201E2
0x20187  ldc.i4.1
0x20188  stloc.0
0x20189  ldloc.1
0x2018a  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x2018f  stloc.2
0x20190  br.s     loc_201C4
0x20192  ldloc.2
0x20193  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x20198  castclass [System.Xml]System.Xml.XmlNode
0x2019d  stloc.3
0x2019e  ldarg.0
0x2019f  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Application.RowDescriptor::multipleRowControlClassIds
0x201a4  ldloc.3
0x201a5  ldstr    aClassid// "classid"
0x201aa  ldstr    asc_A9652// ""
0x201af  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x201b4  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x201b9  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x201be  brtrue.s loc_201C4
0x201c0  ldc.i4.0
0x201c1  stloc.0
0x201c2  leave.s  loc_201EE
0x201c4  ldloc.2
0x201c5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x201ca  brtrue.s loc_20192
0x201cc  leave.s  loc_201EE
0x201ce  ldloc.2
0x201cf  isinst   [mscorlib]System.IDisposable
0x201d4  stloc.s  4
0x201d6  ldloc.s  4
0x201d8  brfalse.s loc_201E1
0x201da  ldloc.s  4
0x201dc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x201e1  endfinally
0x201e2  leave.s  loc_201EE
0x201e4  ldloc.1
0x201e5  brfalse.s loc_201ED
0x201e7  ldloc.1
0x201e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x201ed  endfinally
0x201ee  ldloc.0
0x201ef  ret
```
