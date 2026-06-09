# Microsoft.Crm.Controls.CommandBarButton::SerializeToXml

- ea: `0x10010`
- end: `0x10198`
- name: `Microsoft.Crm.Controls.CommandBarButton::SerializeToXml`
- size: `392`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0xfe60`
- `0x10010`
- `0x116d0`
- `0x116f0`
- `0x11710`
- `0x11740`
- `0x11800`
- `0x118d0`
- `0x119e0`
- `0x23c20`

## pseudocode

```c

```

## disassembly

```asm
0x10010  ldarg.0
0x10011  ldstr    aMi// "_MI"
0x10016  ldarg.0
0x10017  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Controls.CommandBarControl::get_CustomProperties()
0x1001c  ldstr    aGridid// "gridid"
0x10021  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x10026  call     string [mscorlib]System.String::Concat(object, object)
0x1002b  call     instance void Microsoft.Crm.Controls.CommandBarControl::SetTestIdFromAction(string prefix)
0x10030  ldarg.1
0x10031  ldstr    aItem// "item"
0x10036  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1003b  ldarg.1
0x1003c  ldstr    aType// "type"
0x10041  ldc.i4.1
0x10042  stloc.0
0x10043  ldloca.s 0
0x10045  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1004a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1004f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x10054  ldarg.0
0x10055  call     instance valuetype CommandBarButtonStyle Microsoft.Crm.Controls.CommandBarButton::get_ButtonStyle()
0x1005a  ldc.i4.2
0x1005b  beq.s    loc_1006E
0x1005d  ldarg.1
0x1005e  ldstr    aAction// "action"
0x10063  ldarg.0
0x10064  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Action()
0x10069  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1006e  ldarg.0
0x1006f  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x10074  brfalse.s loc_10086
0x10076  ldarg.1
0x10077  ldstr    aDisabled// "disabled"
0x1007c  ldstr    aTrue// "true"
0x10081  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x10086  ldarg.0
0x10087  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Controls.CommandBarControl::get_CustomProperties()
0x1008c  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0x10091  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x10096  stloc.1
0x10097  br.s     loc_100BD
0x10099  ldloc.1
0x1009a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1009f  stloc.2
0x100a0  ldarg.1
0x100a1  ldloc.2
0x100a2  castclass [mscorlib]System.String
0x100a7  ldarg.0
0x100a8  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Controls.CommandBarControl::get_CustomProperties()
0x100ad  ldloc.2
0x100ae  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x100b3  castclass [mscorlib]System.String
0x100b8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x100bd  ldloc.1
0x100be  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x100c3  brtrue.s loc_10099
0x100c5  leave.s  loc_100D8
0x100c7  ldloc.1
0x100c8  isinst   [mscorlib]System.IDisposable
0x100cd  stloc.3
0x100ce  ldloc.3
0x100cf  brfalse.s loc_100D7
0x100d1  ldloc.3
0x100d2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x100d7  endfinally
0x100d8  ldarg.0
0x100d9  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0x100de  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x100e3  brtrue.s loc_100F6
0x100e5  ldarg.1
0x100e6  ldstr    aKey// "key"
0x100eb  ldarg.0
0x100ec  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0x100f1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x100f6  ldarg.0
0x100f7  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x100fc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10101  brtrue.s loc_10114
0x10103  ldarg.1
0x10104  ldstr    aId// "id"
0x10109  ldarg.0
0x1010a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1010f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x10114  ldarg.1
0x10115  ldstr    aButtonstyle// "buttonstyle"
0x1011a  ldarg.0
0x1011b  call     instance valuetype CommandBarButtonStyle Microsoft.Crm.Controls.CommandBarButton::get_ButtonStyle()
0x10120  stloc.0
0x10121  ldloca.s 0
0x10123  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10128  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1012d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x10132  ldarg.0
0x10133  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.CommandBarControl::get_Icon()
0x10138  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x1013d  brtrue.s loc_10155
0x1013f  ldarg.1
0x10140  ldstr    aIcon// "icon"
0x10145  ldarg.0
0x10146  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.CommandBarControl::get_Icon()
0x1014b  callvirt instance string [mscorlib]System.Object::ToString()
0x10150  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x10155  ldarg.0
0x10156  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x1015b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10160  brtrue.s loc_10173
0x10162  ldarg.1
0x10163  ldstr    aTitle_2// "title"
0x10168  ldarg.0
0x10169  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x1016e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x10173  ldarg.0
0x10174  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0x10179  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1017e  brtrue.s loc_10191
0x10180  ldarg.1
0x10181  ldstr    aTooltip// "tooltip"
0x10186  ldarg.0
0x10187  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0x1018c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x10191  ldarg.1
0x10192  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x10197  ret
```
