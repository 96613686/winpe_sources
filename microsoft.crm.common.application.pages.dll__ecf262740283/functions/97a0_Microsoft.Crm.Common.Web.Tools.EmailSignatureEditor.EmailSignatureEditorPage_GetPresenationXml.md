# Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::GetPresenationXml

- ea: `0x97a0`
- end: `0x9830`
- name: `Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::GetPresenationXml`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9670`

## callees

- `0x97a0`

## string_xrefs

- `0x97e7`: `presentationxml`

## pseudocode

```c

```

## disassembly

```asm
0x97a0  ldnull
0x97a1  stloc.0
0x97a2  ldarg.1
0x97a3  brfalse  loc_982E
0x97a8  ldarg.1
0x97a9  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x97ae  stloc.1
0x97af  ldloc.1
0x97b0  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x97b5  brfalse.s loc_982E
0x97b7  ldloc.1
0x97b8  ldstr    aEmailsignature_2// "/emailsignature"
0x97bd  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x97c2  ldc.i4.0
0x97c3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x97c8  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x97cd  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x97d2  stloc.2
0x97d3  br.s     loc_9810
0x97d5  ldloc.2
0x97d6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x97db  castclass [System.Xml]System.Xml.XmlNode
0x97e0  stloc.3
0x97e1  ldloc.3
0x97e2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x97e7  ldstr    aPresentationxm// "presentationxml"
0x97ec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x97f1  brfalse.s loc_9810
0x97f3  ldstr    aEmailsignature_3// "<emailsignature>"
0x97f8  ldloc.3
0x97f9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x97fe  ldstr    aEmailsignature_4// "</emailsignature>"
0x9803  call     string [mscorlib]System.String::Concat(string, string, string)
0x9808  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x980d  stloc.0
0x980e  leave.s  loc_982E
0x9810  ldloc.2
0x9811  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9816  brtrue.s loc_97D5
0x9818  leave.s  loc_982E
0x981a  ldloc.2
0x981b  isinst   [mscorlib]System.IDisposable
0x9820  stloc.s  4
0x9822  ldloc.s  4
0x9824  brfalse.s loc_982D
0x9826  ldloc.s  4
0x9828  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x982d  endfinally
0x982e  ldloc.0
0x982f  ret
```
