# Microsoft.Crm.Reporting.SRSReport::ProcessReferencedReports

- ea: `0x5e0`
- end: `0x663`
- name: `Microsoft.Crm.Reporting.SRSReport::ProcessReferencedReports`
- size: `131`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x690`
- `0x6e0`
- `0x740`

## callees

- `0x5e0`
- `0x86b0`

## pseudocode

```c

```

## disassembly

```asm
0x5e0  ldarg.0
0x5e1  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x5e6  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x5eb  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x5f0  stloc.0
0x5f1  ldloc.0
0x5f2  ldstr    aD// "d"
0x5f7  ldarg.0
0x5f8  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x5fd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x602  callvirt instance string [System.Xml]System.Xml.XmlNode::get_NamespaceURI()
0x607  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x60c  ldarg.0
0x60d  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x612  ldarg.1
0x613  ldloc.0
0x614  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x619  stloc.1
0x61a  ldloc.1
0x61b  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x620  stloc.2
0x621  br.s     loc_63A
0x623  ldloc.2
0x624  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x629  castclass [System.Xml]System.Xml.XmlNode
0x62e  stloc.3
0x62f  ldarg.2
0x630  ldloc.3
0x631  callvirt instance bool ReferencedReportProcessor::Invoke(class [System.Xml]System.Xml.XmlNode referencedReport)
0x636  brtrue.s loc_63A
0x638  leave.s  loc_662
0x63a  ldloc.2
0x63b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x640  brtrue.s loc_623
0x642  leave.s  loc_662
0x644  ldloc.2
0x645  isinst   [mscorlib]System.IDisposable
0x64a  stloc.s  4
0x64c  ldloc.s  4
0x64e  brfalse.s loc_657
0x650  ldloc.s  4
0x652  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x657  endfinally
0x658  ldloc.1
0x659  brfalse.s loc_661
0x65b  ldloc.1
0x65c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x661  endfinally
0x662  ret
```
