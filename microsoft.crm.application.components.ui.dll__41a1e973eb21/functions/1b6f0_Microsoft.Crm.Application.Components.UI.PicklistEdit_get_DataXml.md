# Microsoft.Crm.Application.Components.UI.PicklistEdit::get_DataXml

- ea: `0x1b6f0`
- end: `0x1b892`
- name: `Microsoft.Crm.Application.Components.UI.PicklistEdit::get_DataXml`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1bd00`

## callees

- `0x1b6f0`
- `0x1bf90`
- `0x1c940`
- `0x1c960`
- `0x1c980`
- `0x1c9c0`
- `0x1c9e0`
- `0x1ca00`
- `0x1ca20`

## pseudocode

```c

```

## disassembly

```asm
0x1b6f0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1b6f5  stloc.0
0x1b6f6  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x1b6fb  stloc.1
0x1b6fc  ldloc.1
0x1b6fd  ldc.i4.1
0x1b6fe  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x1b703  ldloc.0
0x1b704  ldloc.1
0x1b705  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x1b70a  stloc.2
0x1b70b  ldloc.2
0x1b70c  ldstr    aValues// "values"
0x1b711  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1b716  ldarg.0
0x1b717  ldc.i4.8
0x1b718  call     instance bool Microsoft.Crm.Application.Components.UI.PicklistEdit::CheckFunction(valuetype Function function)
0x1b71d  brfalse.s loc_1B73F
0x1b71f  ldloc.2
0x1b720  ldstr    aDefault// "default"
0x1b725  ldarg.0
0x1b726  ldflda   int32 Microsoft.Crm.Application.Components.UI.PicklistEdit::_defaultValue
0x1b72b  ldstr    aD_1// "D"
0x1b730  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b735  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1b73a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1b73f  ldloc.2
0x1b740  ldstr    aNext// "next"
0x1b745  ldarg.0
0x1b746  ldflda   int32 Microsoft.Crm.Application.Components.UI.PicklistEdit::_nextValue
0x1b74b  ldstr    aD_1// "D"
0x1b750  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b755  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1b75a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1b75f  ldloc.2
0x1b760  ldstr    aPrefix// "prefix"
0x1b765  ldarg.0
0x1b766  ldflda   int32 Microsoft.Crm.Application.Components.UI.PicklistEdit::_prefixValue
0x1b76b  ldstr    aD_1// "D"
0x1b770  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b775  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1b77a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1b77f  ldarg.0
0x1b780  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue> Microsoft.Crm.Application.Components.UI.PicklistEdit::_values
0x1b785  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue>::get_Values()
0x1b78a  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue>::GetEnumerator()
0x1b78f  stloc.3
0x1b790  br       loc_1B857
0x1b795  ldloca.s 3
0x1b797  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue>::get_Current()
0x1b79c  stloc.s  4
0x1b79e  ldloc.2
0x1b79f  ldstr    aValue_0// "value"
0x1b7a4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1b7a9  ldloc.2
0x1b7aa  ldstr    aValue_0// "value"
0x1b7af  ldloc.s  4
0x1b7b1  callvirt instance int32 Microsoft.Crm.Application.Components.UI.ListItemValue::get_Value()
0x1b7b6  stloc.s  5
0x1b7b8  ldloca.s 5
0x1b7ba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b7bf  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1b7c4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1b7c9  ldloc.2
0x1b7ca  ldstr    aLabel// "label"
0x1b7cf  ldloc.s  4
0x1b7d1  callvirt instance string Microsoft.Crm.Application.Components.UI.ListItemValue::get_Label()
0x1b7d6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1b7db  ldloc.2
0x1b7dc  ldstr    aExternalname// "externalname"
0x1b7e1  ldloc.s  4
0x1b7e3  callvirt instance string Microsoft.Crm.Application.Components.UI.ListItemValue::get_ExternalName()
0x1b7e8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1b7ed  ldloc.2
0x1b7ee  ldstr    aEditable_0// "editable"
0x1b7f3  ldloc.s  4
0x1b7f5  callvirt instance bool Microsoft.Crm.Application.Components.UI.ListItemValue::get_Editable()
0x1b7fa  brtrue.s loc_1B803
0x1b7fc  ldstr    a0// "0"
0x1b801  br.s     loc_1B808
0x1b803  ldstr    a1// "1"
0x1b808  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1b80d  ldloc.2
0x1b80e  ldstr    aDescription// "description"
0x1b813  ldloc.s  4
0x1b815  callvirt instance string Microsoft.Crm.Application.Components.UI.ListItemValue::get_Description()
0x1b81a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1b81f  ldloc.2
0x1b820  ldstr    aColor// "color"
0x1b825  ldloc.s  4
0x1b827  callvirt instance string Microsoft.Crm.Application.Components.UI.ListItemValue::get_Color()
0x1b82c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1b831  ldloc.s  4
0x1b833  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<int32> Microsoft.Crm.Application.Components.UI.ListItemValue::get_ParentValues()
0x1b838  brfalse.s loc_1B851
0x1b83a  ldloc.2
0x1b83b  ldstr    aParentvalues// "parentvalues"
0x1b840  ldloc.s  4
0x1b842  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<int32> Microsoft.Crm.Application.Components.UI.ListItemValue::get_ParentValues()
0x1b847  call     T0x2B000026
0x1b84c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1b851  ldloc.2
0x1b852  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1b857  ldloca.s 3
0x1b859  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue>::MoveNext()
0x1b85e  brtrue   loc_1B795
0x1b863  leave.s  loc_1B873
0x1b865  ldloca.s 3
0x1b867  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue>
0x1b86d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b872  endfinally
0x1b873  ldloc.2
0x1b874  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1b879  ldloc.2
0x1b87a  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x1b87f  leave.s  loc_1B88B
0x1b881  ldloc.2
0x1b882  brfalse.s loc_1B88A
0x1b884  ldloc.2
0x1b885  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b88a  endfinally
0x1b88b  ldloc.0
0x1b88c  callvirt instance string [mscorlib]System.Object::ToString()
0x1b891  ret
```
