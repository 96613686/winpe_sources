# Microsoft.Crm.Application.Utility.Util::AppendInnerXml

- ea: `0x46990`
- end: `0x46a1f`
- name: `Microsoft.Crm.Application.Utility.Util::AppendInnerXml`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x46a20`

## callees

- `0x115b0`
- `0x46990`

## string_xrefs

- `0x4699a`: `Attempt to AppendInnerXml without specifying the original xml.`
- `0x469ae`: `Attempt to AppendInnerXml without specifying the xml to append.`

## pseudocode

```c

```

## disassembly

```asm
0x46990  ldarg.0
0x46991  ldind.ref
0x46992  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x46997  brfalse.s loc_469A5
0x46999  ldc.i4.0
0x4699a  ldstr    aAttemptToAppen// "Attempt to AppendInnerXml without speci"...
0x4699f  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x469a4  ret
0x469a5  ldarg.1
0x469a6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x469ab  brfalse.s loc_469B9
0x469ad  ldc.i4.0
0x469ae  ldstr    aAttemptToAppen_0// "Attempt to AppendInnerXml without speci"...
0x469b3  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x469b8  ret
0x469b9  ldarg.0
0x469ba  ldind.ref
0x469bb  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x469c0  stloc.0
0x469c1  ldloc.0
0x469c2  ldstr    aTemp// "temp"
0x469c7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x469cc  stloc.1
0x469cd  ldloc.1
0x469ce  ldarg.1
0x469cf  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x469d4  ldloc.1
0x469d5  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x469da  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x469df  ldc.i4.0
0x469e0  cgt
0x469e2  ldstr    aThreeMustBeAtL// "Three must be at least one child elemen"...
0x469e7  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x469ec  br.s     loc_46A08
0x469ee  ldloc.1
0x469ef  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x469f4  ldc.i4.0
0x469f5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x469fa  stloc.2
0x469fb  ldloc.0
0x469fc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x46a01  ldloc.2
0x46a02  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x46a07  pop
0x46a08  ldloc.1
0x46a09  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x46a0e  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x46a13  ldc.i4.0
0x46a14  bgt.s    loc_469EE
0x46a16  ldarg.0
0x46a17  ldloc.0
0x46a18  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x46a1d  stind.ref
0x46a1e  ret
```
