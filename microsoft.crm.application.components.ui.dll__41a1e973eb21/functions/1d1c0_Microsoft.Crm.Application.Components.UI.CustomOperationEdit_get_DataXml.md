# Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_DataXml

- ea: `0x1d1c0`
- end: `0x1d36f`
- name: `Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_DataXml`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1d7b0`

## callees

- `0x1d1c0`
- `0x1db70`
- `0x1e8c0`
- `0x1e8e0`
- `0x1e900`
- `0x1e920`
- `0x1e940`
- `0x1e960`
- `0x1e9a0`
- `0x1e9c0`

## pseudocode

```c

```

## disassembly

```asm
0x1d1c0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d1c5  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x1d1ca  stloc.0
0x1d1cb  ldloc.0
0x1d1cc  ldc.i4.1
0x1d1cd  call     class [System.Xml]System.Xml.XmlWriter [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlWriter(class [mscorlib]System.IO.TextWriter, bool)
0x1d1d2  stloc.1
0x1d1d3  ldloc.1
0x1d1d4  ldstr    aValues// "values"
0x1d1d9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1d1de  ldarg.0
0x1d1df  ldc.i4.8
0x1d1e0  call     instance bool Microsoft.Crm.Application.Components.UI.CustomOperationEdit::CheckFunction(valuetype Microsoft.Crm.Application.Components.UI.CustomOperationFunction function)
0x1d1e5  brfalse.s loc_1D207
0x1d1e7  ldloc.1
0x1d1e8  ldstr    aDefault// "default"
0x1d1ed  ldarg.0
0x1d1ee  ldflda   int32 Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_defaultValue
0x1d1f3  ldstr    aD_1// "D"
0x1d1f8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d1fd  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1d202  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d207  ldloc.1
0x1d208  ldstr    aNext// "next"
0x1d20d  ldarg.0
0x1d20e  ldflda   int32 Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_nextValue
0x1d213  ldstr    aD_1// "D"
0x1d218  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d21d  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1d222  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d227  ldloc.1
0x1d228  ldstr    aPrefix// "prefix"
0x1d22d  ldarg.0
0x1d22e  ldflda   int32 Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_prefixValue
0x1d233  ldstr    aD_1// "D"
0x1d238  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d23d  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1d242  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d247  ldarg.0
0x1d248  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue> Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_values
0x1d24d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue>::get_Values()
0x1d252  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue>::GetEnumerator()
0x1d257  stloc.2
0x1d258  br       loc_1D324
0x1d25d  ldloca.s 2
0x1d25f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue>::get_Current()
0x1d264  stloc.3
0x1d265  ldloc.1
0x1d266  ldstr    aValue_0// "value"
0x1d26b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1d270  ldloc.1
0x1d271  ldstr    aName_0// "name"
0x1d276  ldloc.3
0x1d277  callvirt instance string Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::get_Name()
0x1d27c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d281  callvirt instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0x1d286  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d28b  ldloc.1
0x1d28c  ldstr    aType// "type"
0x1d291  ldloc.3
0x1d292  callvirt instance string Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::get_Type()
0x1d297  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d29c  ldloc.1
0x1d29d  ldstr    aTypename// "typename"
0x1d2a2  ldloc.3
0x1d2a3  callvirt instance string Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::get_TypeName()
0x1d2a8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d2ad  ldloc.1
0x1d2ae  ldstr    aOptional// "optional"
0x1d2b3  ldloc.3
0x1d2b4  callvirt instance bool Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::get_Optional()
0x1d2b9  brtrue.s loc_1D2C2
0x1d2bb  ldstr    a0// "0"
0x1d2c0  br.s     loc_1D2C7
0x1d2c2  ldstr    a1// "1"
0x1d2c7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d2cc  ldloc.1
0x1d2cd  ldstr    aDirection// "direction"
0x1d2d2  ldloc.3
0x1d2d3  callvirt instance string Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::get_Direction()
0x1d2d8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d2dd  ldloc.1
0x1d2de  ldstr    aEditable_0// "editable"
0x1d2e3  ldloc.3
0x1d2e4  callvirt instance bool Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::get_Editable()
0x1d2e9  brtrue.s loc_1D2F2
0x1d2eb  ldstr    a0// "0"
0x1d2f0  br.s     loc_1D2F7
0x1d2f2  ldstr    a1// "1"
0x1d2f7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d2fc  ldloc.1
0x1d2fd  ldstr    aDescription// "description"
0x1d302  ldloc.3
0x1d303  callvirt instance string Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::get_Description()
0x1d308  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d30d  ldloc.1
0x1d30e  ldstr    aEntity// "entity"
0x1d313  ldloc.3
0x1d314  callvirt instance string Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::get_EntityName()
0x1d319  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d31e  ldloc.1
0x1d31f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1d324  ldloca.s 2
0x1d326  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue>::MoveNext()
0x1d32b  brtrue   loc_1D25D
0x1d330  leave.s  loc_1D340
0x1d332  ldloca.s 2
0x1d334  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue>
0x1d33a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d33f  endfinally
0x1d340  ldloc.1
0x1d341  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1d346  ldloc.1
0x1d347  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x1d34c  leave.s  loc_1D358
0x1d34e  ldloc.1
0x1d34f  brfalse.s loc_1D357
0x1d351  ldloc.1
0x1d352  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d357  endfinally
0x1d358  ldloc.0
0x1d359  callvirt instance string [mscorlib]System.Object::ToString()
0x1d35e  stloc.s  4
0x1d360  leave.s  loc_1D36C
0x1d362  ldloc.0
0x1d363  brfalse.s loc_1D36B
0x1d365  ldloc.0
0x1d366  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d36b  endfinally
0x1d36c  ldloc.s  4
0x1d36e  ret
```
