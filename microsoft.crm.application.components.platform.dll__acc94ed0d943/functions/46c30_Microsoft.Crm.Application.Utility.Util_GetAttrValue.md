# Microsoft.Crm.Application.Utility.Util::GetAttrValue

- ea: `0x46c30`
- end: `0x46cc6`
- name: `Microsoft.Crm.Application.Utility.Util::GetAttrValue`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15cf0`

## callees

- `0x115b0`
- `0x46c30`

## string_xrefs

- `0x46c39`: `Attempt to get xml attribute value without specifying the xml.`
- `0x46c52`: `Attempt to get xml attribute value without specifying the node name.`
- `0x46c6b`: `Attempt to get xml attribute value without specifying the attribute name.`

## pseudocode

```c

```

## disassembly

```asm
0x46c30  ldarg.0
0x46c31  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x46c36  brfalse.s loc_46C49
0x46c38  ldc.i4.0
0x46c39  ldstr    aAttemptToGetXm// "Attempt to get xml attribute value with"...
0x46c3e  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x46c43  ldsfld   string [mscorlib]System.String::Empty
0x46c48  ret
0x46c49  ldarg.1
0x46c4a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x46c4f  brfalse.s loc_46C62
0x46c51  ldc.i4.0
0x46c52  ldstr    aAttemptToGetXm_0// "Attempt to get xml attribute value with"...
0x46c57  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x46c5c  ldsfld   string [mscorlib]System.String::Empty
0x46c61  ret
0x46c62  ldarg.2
0x46c63  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x46c68  brfalse.s loc_46C7B
0x46c6a  ldc.i4.0
0x46c6b  ldstr    aAttemptToGetXm_1// "Attempt to get xml attribute value with"...
0x46c70  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x46c75  ldsfld   string [mscorlib]System.String::Empty
0x46c7a  ret
0x46c7b  ldarg.0
0x46c7c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x46c81  brtrue.s loc_46C93
0x46c83  ldarg.1
0x46c84  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x46c89  brtrue.s loc_46C93
0x46c8b  ldarg.2
0x46c8c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x46c91  brfalse.s loc_46C99
0x46c93  ldsfld   string [mscorlib]System.String::Empty
0x46c98  ret
0x46c99  ldarg.0
0x46c9a  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x46c9f  ldstr    asc_CAC3C// "//"
0x46ca4  ldarg.1
0x46ca5  ldstr    asc_CAED6// "/@"
0x46caa  ldarg.2
0x46cab  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x46cb0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x46cb5  stloc.0
0x46cb6  ldloc.0
0x46cb7  brfalse.s loc_46CC0
0x46cb9  ldloc.0
0x46cba  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x46cbf  ret
0x46cc0  ldsfld   string [mscorlib]System.String::Empty
0x46cc5  ret
```
