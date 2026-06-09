# Microsoft.Crm.Application.Utility.Util::RemoveNode_0

- ea: `0x46b70`
- end: `0x46bcc`
- name: `Microsoft.Crm.Application.Utility.Util::RemoveNode_0`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x46b60`

## callees

- `0x115b0`
- `0x46b70`

## string_xrefs

- `0x46b79`: `Attempt to RemoveNode without specifying the original xml.`
- `0x46b92`: `Attempt to remove xml node value without specifying the node to remove.`

## pseudocode

```c

```

## disassembly

```asm
0x46b70  ldarg.0
0x46b71  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x46b76  brfalse.s loc_46B89
0x46b78  ldc.i4.0
0x46b79  ldstr    aAttemptToRemov// "Attempt to RemoveNode without specifyin"...
0x46b7e  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x46b83  ldsfld   string [mscorlib]System.String::Empty
0x46b88  ret
0x46b89  ldarg.1
0x46b8a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x46b8f  brfalse.s loc_46B9E
0x46b91  ldc.i4.0
0x46b92  ldstr    aAttemptToRemov_0// "Attempt to remove xml node value withou"...
0x46b97  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x46b9c  ldarg.0
0x46b9d  ret
0x46b9e  ldarg.0
0x46b9f  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x46ba4  dup
0x46ba5  ldstr    asc_CAC3C// "//"
0x46baa  ldarg.1
0x46bab  call     string [mscorlib]System.String::Concat(string, string)
0x46bb0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x46bb5  stloc.0
0x46bb6  ldloc.0
0x46bb7  brfalse.s loc_46BC6
0x46bb9  ldloc.0
0x46bba  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x46bbf  ldloc.0
0x46bc0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x46bc5  pop
0x46bc6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x46bcb  ret
```
