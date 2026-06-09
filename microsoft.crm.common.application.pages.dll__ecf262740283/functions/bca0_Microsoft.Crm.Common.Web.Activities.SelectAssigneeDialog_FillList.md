# Microsoft.Crm.Common.Web.Activities.SelectAssigneeDialog::FillList

- ea: `0xbca0`
- end: `0xbdb9`
- name: `Microsoft.Crm.Common.Web.Activities.SelectAssigneeDialog::FillList`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xbdc0`

## callees

- `0xbca0`
- `0x1dc30`
- `0x1dc50`
- `0x1dc70`
- `0x1dc80`

## pseudocode

```c

```

## disassembly

```asm
0xbca0  ldarg.1
0xbca1  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xbca6  ldstr    aQueue// "queue"
0xbcab  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0xbcb0  stloc.0
0xbcb1  ldloc.0
0xbcb2  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xbcb7  stloc.1
0xbcb8  br       loc_BD8D
0xbcbd  ldloc.1
0xbcbe  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xbcc3  castclass [System.Xml]System.Xml.XmlNode
0xbcc8  stloc.2
0xbcc9  newobj   instance void QueueEntry::.ctor()
0xbcce  stloc.3
0xbccf  ldloc.3
0xbcd0  ldloc.2
0xbcd1  ldstr    aQueueid// "queueid"
0xbcd6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xbcdb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xbce0  callvirt instance void QueueEntry::set_Id(string value)
0xbce5  ldloc.2
0xbce6  ldstr    aQueuetypecode// "queuetypecode"
0xbceb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xbcf0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xbcf5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbcfa  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xbcff  ldc.i4.1
0xbd00  bne.un.s loc_BD38
0xbd02  ldloc.3
0xbd03  ldloc.2
0xbd04  ldstr    aName// "name"
0xbd09  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xbd0e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xbd13  callvirt instance void QueueEntry::set_Name(string value)
0xbd18  ldloc.3
0xbd19  ldc.i4   0x7E4
0xbd1e  stloc.s  4
0xbd20  ldloca.s 4
0xbd22  ldstr    aD// "D"
0xbd27  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbd2c  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0xbd31  callvirt instance void QueueEntry::set_ObjectTypeCode(string value)
0xbd36  br.s     loc_BD80
0xbd38  ldloc.2
0xbd39  ldstr    aPrimaryuserid// "primaryuserid"
0xbd3e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xbd43  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xbd48  ldstr    aName// "name"
0xbd4d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0xbd52  castclass [System.Xml]System.Xml.XmlAttribute
0xbd57  stloc.s  5
0xbd59  ldloc.3
0xbd5a  ldloc.s  5
0xbd5c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xbd61  callvirt instance void QueueEntry::set_Name(string value)
0xbd66  ldloc.3
0xbd67  ldc.i4.8
0xbd68  stloc.s  4
0xbd6a  ldloca.s 4
0xbd6c  ldstr    aD// "D"
0xbd71  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbd76  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0xbd7b  callvirt instance void QueueEntry::set_ObjectTypeCode(string value)
0xbd80  ldarg.0
0xbd81  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Common.Web.Activities.SelectAssigneeDialog::_queueEntries
0xbd86  ldloc.3
0xbd87  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xbd8c  pop
0xbd8d  ldloc.1
0xbd8e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbd93  brtrue   loc_BCBD
0xbd98  leave.s  loc_BDB8
0xbd9a  ldloc.1
0xbd9b  isinst   [mscorlib]System.IDisposable
0xbda0  stloc.s  6
0xbda2  ldloc.s  6
0xbda4  brfalse.s loc_BDAD
0xbda6  ldloc.s  6
0xbda8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbdad  endfinally
0xbdae  ldloc.0
0xbdaf  brfalse.s loc_BDB7
0xbdb1  ldloc.0
0xbdb2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbdb7  endfinally
0xbdb8  ret
```
