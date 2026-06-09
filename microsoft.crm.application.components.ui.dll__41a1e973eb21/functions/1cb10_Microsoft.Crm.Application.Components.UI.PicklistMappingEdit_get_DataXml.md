# Microsoft.Crm.Application.Components.UI.PicklistMappingEdit::get_DataXml

- ea: `0x1cb10`
- end: `0x1cc77`
- name: `Microsoft.Crm.Application.Components.UI.PicklistMappingEdit::get_DataXml`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1ccf0`

## callees

- `0x1c940`
- `0x1c960`
- `0x1c9c0`
- `0x1c9e0`
- `0x1ca00`
- `0x1ca20`
- `0x1cb10`

## pseudocode

```c

```

## disassembly

```asm
0x1cb10  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1cb15  stloc.0
0x1cb16  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x1cb1b  stloc.1
0x1cb1c  ldloc.1
0x1cb1d  ldc.i4.1
0x1cb1e  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x1cb23  ldloc.0
0x1cb24  ldloc.1
0x1cb25  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x1cb2a  stloc.2
0x1cb2b  ldloc.2
0x1cb2c  ldstr    aValues// "values"
0x1cb31  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1cb36  ldloc.2
0x1cb37  ldstr    aNext// "next"
0x1cb3c  ldarg.0
0x1cb3d  ldflda   int32 Microsoft.Crm.Application.Components.UI.PicklistMappingEdit::_nextValue
0x1cb42  ldstr    aD_1// "D"
0x1cb47  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1cb4c  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1cb51  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1cb56  ldloc.2
0x1cb57  ldstr    aPrefix// "prefix"
0x1cb5c  ldarg.0
0x1cb5d  ldflda   int32 Microsoft.Crm.Application.Components.UI.PicklistMappingEdit::_prefixValue
0x1cb62  ldstr    aD_1// "D"
0x1cb67  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1cb6c  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1cb71  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1cb76  ldarg.0
0x1cb77  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue> Microsoft.Crm.Application.Components.UI.PicklistMappingEdit::_values
0x1cb7c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue>::get_Values()
0x1cb81  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue>::GetEnumerator()
0x1cb86  stloc.3
0x1cb87  br       loc_1CC3C
0x1cb8c  ldloca.s 3
0x1cb8e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue>::get_Current()
0x1cb93  stloc.s  4
0x1cb95  ldloc.2
0x1cb96  ldstr    aValue_0// "value"
0x1cb9b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1cba0  ldloc.2
0x1cba1  ldstr    aValue_0// "value"
0x1cba6  ldloc.s  4
0x1cba8  callvirt instance int32 Microsoft.Crm.Application.Components.UI.ListItemValue::get_Value()
0x1cbad  stloc.s  5
0x1cbaf  ldloca.s 5
0x1cbb1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1cbb6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1cbbb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1cbc0  ldloc.2
0x1cbc1  ldstr    aLabel// "label"
0x1cbc6  ldloc.s  4
0x1cbc8  callvirt instance string Microsoft.Crm.Application.Components.UI.ListItemValue::get_Label()
0x1cbcd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1cbd2  ldloc.2
0x1cbd3  ldstr    aEditable_0// "editable"
0x1cbd8  ldloc.s  4
0x1cbda  callvirt instance bool Microsoft.Crm.Application.Components.UI.ListItemValue::get_Editable()
0x1cbdf  brtrue.s loc_1CBE8
0x1cbe1  ldstr    a0// "0"
0x1cbe6  br.s     loc_1CBED
0x1cbe8  ldstr    a1// "1"
0x1cbed  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1cbf2  ldloc.2
0x1cbf3  ldstr    aDescription// "description"
0x1cbf8  ldloc.s  4
0x1cbfa  callvirt instance string Microsoft.Crm.Application.Components.UI.ListItemValue::get_Description()
0x1cbff  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1cc04  ldloc.2
0x1cc05  ldstr    aColor// "color"
0x1cc0a  ldloc.s  4
0x1cc0c  callvirt instance string Microsoft.Crm.Application.Components.UI.ListItemValue::get_Color()
0x1cc11  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1cc16  ldloc.s  4
0x1cc18  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<int32> Microsoft.Crm.Application.Components.UI.ListItemValue::get_ParentValues()
0x1cc1d  brfalse.s loc_1CC36
0x1cc1f  ldloc.2
0x1cc20  ldstr    aParentvalues// "parentvalues"
0x1cc25  ldloc.s  4
0x1cc27  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<int32> Microsoft.Crm.Application.Components.UI.ListItemValue::get_ParentValues()
0x1cc2c  call     T0x2B000026
0x1cc31  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1cc36  ldloc.2
0x1cc37  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1cc3c  ldloca.s 3
0x1cc3e  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue>::MoveNext()
0x1cc43  brtrue   loc_1CB8C
0x1cc48  leave.s  loc_1CC58
0x1cc4a  ldloca.s 3
0x1cc4c  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue>
0x1cc52  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1cc57  endfinally
0x1cc58  ldloc.2
0x1cc59  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1cc5e  ldloc.2
0x1cc5f  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x1cc64  leave.s  loc_1CC70
0x1cc66  ldloc.2
0x1cc67  brfalse.s loc_1CC6F
0x1cc69  ldloc.2
0x1cc6a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1cc6f  endfinally
0x1cc70  ldloc.0
0x1cc71  callvirt instance string [mscorlib]System.Object::ToString()
0x1cc76  ret
```
