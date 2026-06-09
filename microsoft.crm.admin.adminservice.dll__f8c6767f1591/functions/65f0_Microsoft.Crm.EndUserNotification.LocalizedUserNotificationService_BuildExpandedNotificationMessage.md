# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildExpandedNotificationMessage

- ea: `0x65f0`
- end: `0x66ef`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildExpandedNotificationMessage`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x5df0`

## callees

- `0x4af0`
- `0x4b00`
- `0x4b10`
- `0x4b20`
- `0x4b30`
- `0x65f0`

## string_xrefs

- `0x6628`: `EndUserNotificationTemplate/EmailContent/Subject`
- `0x660e`: `EndUserNotificationTemplate/WebContent/Title`
- `0x661a`: `EndUserNotificationTemplate/WebContent/Message`
- `0x6634`: `EndUserNotificationTemplate/EmailContent/Body`

## pseudocode

```c

```

## disassembly

```asm
0x65f0  newobj   instance void Microsoft.Crm.EndUserNotification.EndUserNotificationMessage::.ctor()
0x65f5  stloc.0
0x65f6  ldarg.0
0x65f7  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x65fc  stloc.1
0x65fd  ldnull
0x65fe  stloc.2
0x65ff  ldnull
0x6600  stloc.3
0x6601  ldarg.2
0x6602  ldc.i4.1
0x6603  sub
0x6604  ldc.i4.2
0x6605  ble.un.s loc_660D
0x6607  ldarg.2
0x6608  ldc.i4.4
0x6609  beq.s    loc_6627
0x660b  br.s     loc_663F
0x660d  ldloc.1
0x660e  ldstr    aEndusernotific_2// "EndUserNotificationTemplate/WebContent/"...
0x6613  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6618  stloc.2
0x6619  ldloc.1
0x661a  ldstr    aEndusernotific_3// "EndUserNotificationTemplate/WebContent/"...
0x661f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6624  stloc.3
0x6625  br.s     loc_663F
0x6627  ldloc.1
0x6628  ldstr    aEndusernotific// "EndUserNotificationTemplate/EmailConten"...
0x662d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6632  stloc.2
0x6633  ldloc.1
0x6634  ldstr    aEndusernotific_4// "EndUserNotificationTemplate/EmailConten"...
0x6639  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x663e  stloc.3
0x663f  ldloc.0
0x6640  ldloc.2
0x6641  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6646  callvirt instance void Microsoft.Crm.EndUserNotification.EndUserNotificationMessage::set_Title(string value)
0x664b  ldloc.0
0x664c  ldloc.3
0x664d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6652  callvirt instance void Microsoft.Crm.EndUserNotification.EndUserNotificationMessage::set_Content(string value)
0x6657  ldarg.1
0x6658  brfalse  loc_66ED
0x665d  ldarg.1
0x665e  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x6663  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x6668  stloc.s  4
0x666a  br.s     loc_66D4
0x666c  ldloca.s 4
0x666e  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x6673  stloc.s  5
0x6675  ldstr    asc_4DBC2// "["
0x667a  ldloc.s  5
0x667c  ldstr    aName// "Name"
0x6681  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x6686  castclass [mscorlib]System.String
0x668b  ldstr    asc_4DBC6// "]"
0x6690  call     string [mscorlib]System.String::Concat(string, string, string)
0x6695  stloc.s  6
0x6697  ldloc.s  5
0x6699  ldstr    aValue_0// "Value"
0x669e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x66a3  castclass [mscorlib]System.String
0x66a8  stloc.s  7
0x66aa  ldloc.0
0x66ab  ldloc.0
0x66ac  callvirt instance string Microsoft.Crm.EndUserNotification.EndUserNotificationMessage::get_Content()
0x66b1  ldloc.s  6
0x66b3  ldloc.s  7
0x66b5  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x66ba  callvirt instance void Microsoft.Crm.EndUserNotification.EndUserNotificationMessage::set_Content(string value)
0x66bf  ldloc.0
0x66c0  ldloc.0
0x66c1  callvirt instance string Microsoft.Crm.EndUserNotification.EndUserNotificationMessage::get_Title()
0x66c6  ldloc.s  6
0x66c8  ldloc.s  7
0x66ca  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x66cf  callvirt instance void Microsoft.Crm.EndUserNotification.EndUserNotificationMessage::set_Title(string value)
0x66d4  ldloca.s 4
0x66d6  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x66db  brtrue.s loc_666C
0x66dd  leave.s  loc_66ED
0x66df  ldloca.s 4
0x66e1  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x66e7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66ec  endfinally
0x66ed  ldloc.0
0x66ee  ret
```
