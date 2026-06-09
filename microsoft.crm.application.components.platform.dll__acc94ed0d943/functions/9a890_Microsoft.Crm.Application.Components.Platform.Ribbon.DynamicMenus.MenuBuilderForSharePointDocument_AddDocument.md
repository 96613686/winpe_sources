# Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::AddDocumentLocationButtons

- ea: `0x9a890`
- end: `0x9aac5`
- name: `Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::AddDocumentLocationButtons`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a6d0`

## callees

- `0x4fbf0`
- `0x55800`
- `0x55820`
- `0x55840`
- `0x55860`
- `0x558c0`
- `0x558e0`
- `0x55900`
- `0x55ca0`
- `0x55cb0`
- `0x9a890`
- `0x9aad0`
- `0x9ada0`

## string_xrefs

- `0x9aa12`: `servicetype`
- `0x9a98d`: `Mscrm.DynamicMenu.Grid.OpenSource.`

## pseudocode

```c

```

## disassembly

```asm
0x9a890  ldc.i4.0
0x9a891  stloc.0
0x9a892  ldc.i4.0
0x9a893  stloc.1
0x9a894  ldarg.2
0x9a895  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x9a89a  stloc.2
0x9a89b  br       loc_9AAA8
0x9a8a0  ldloca.s 2
0x9a8a2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x9a8a7  stloc.3
0x9a8a8  ldarg.0
0x9a8a9  call     instance string Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_CommandPrefix()
0x9a8ae  ldloca.s 0
0x9a8b0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9a8b5  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9a8ba  call     string [mscorlib]System.String::Concat(string, string)
0x9a8bf  stloc.s  4
0x9a8c1  ldarg.0
0x9a8c2  ldarg.0
0x9a8c3  call     instance string Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_CommandPrefix()
0x9a8c8  ldloc.0
0x9a8c9  ldc.i4.1
0x9a8ca  add
0x9a8cb  stloc.s  8
0x9a8cd  ldloca.s 8
0x9a8cf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9a8d4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9a8d9  call     string [mscorlib]System.String::Concat(string, string)
0x9a8de  ldloc.3
0x9a8df  ldarg.3
0x9a8e0  call     instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::GetRibbonCommandDefinition(string commandId, string locationId, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>> sharePointAttr)
0x9a8e5  stloc.s  5
0x9a8e7  ldarg.s  4
0x9a8e9  ldloc.s  5
0x9a8eb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::Add(var<u1>)
0x9a8f0  ldarg.3
0x9a8f1  ldloc.3
0x9a8f2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>>::get_Item(void)
0x9a8f7  ldstr    aName// "name"
0x9a8fc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x9a901  stloc.s  6
0x9a903  ldarg.0
0x9a904  call     instance string Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_CommandPrefix()
0x9a909  ldloc.0
0x9a90a  ldc.i4.1
0x9a90b  add
0x9a90c  stloc.s  8
0x9a90e  ldloca.s 8
0x9a910  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9a915  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9a91a  call     string [mscorlib]System.String::Concat(string, string)
0x9a91f  newobj   instance void Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::.ctor(string id)
0x9a924  stloc.s  7
0x9a926  ldloc.s  7
0x9a928  ldloc.s  6
0x9a92a  callvirt instance void Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::set_Alt(string value)
0x9a92f  ldloc.s  7
0x9a931  ldloc.s  6
0x9a933  callvirt instance void Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::set_ToolTipTitle(string value)
0x9a938  ldloc.s  7
0x9a93a  ldloc.s  6
0x9a93c  callvirt instance void Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::set_LabelText(string value)
0x9a941  ldloc.s  7
0x9a943  ldloc.s  5
0x9a945  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x9a94a  callvirt instance void Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::set_Command(string value)
0x9a94f  ldloc.s  7
0x9a951  ldc.i4.s 0xA
0x9a953  ldloc.1
0x9a954  dup
0x9a955  ldc.i4.1
0x9a956  add
0x9a957  stloc.1
0x9a958  add
0x9a959  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x9a95e  callvirt instance void Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::set_Sequence(valuetype [mscorlib]System.Nullable`1<int32> value)
0x9a963  ldloc.0
0x9a964  ldc.i4.2
0x9a965  add
0x9a966  stloc.0
0x9a967  ldarg.0
0x9a968  call     instance string Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_CommandPrefix()
0x9a96d  stloc.s  9
0x9a96f  ldloc.s  9
0x9a971  ldstr    aMscrmDynamicme_17// "Mscrm.DynamicMenu.Grid.ChangeLocation."
0x9a976  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9a97b  brtrue.s loc_9A9A1
0x9a97d  ldloc.s  9
0x9a97f  ldstr    aMscrmDynamicme_18// "Mscrm.DynamicMenu.Grid.EditLocation."
0x9a984  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9a989  brtrue.s loc_9AA03
0x9a98b  ldloc.s  9
0x9a98d  ldstr    aMscrmDynamicme_19// "Mscrm.DynamicMenu.Grid.OpenSource."
0x9a992  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9a997  brtrue   loc_9AA82
0x9a99c  br       loc_9AAA8
0x9a9a1  ldarg.0
0x9a9a2  ldloc.s  4
0x9a9a4  ldloc.3
0x9a9a5  ldloc.1
0x9a9a6  call     instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::GetQueryCommandDefinition(string commandId, string locationId, int32 sequence)
0x9a9ab  stloc.s  0xA
0x9a9ad  ldarg.s  4
0x9a9af  ldloc.s  0xA
0x9a9b1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::Add(var<u1>)
0x9a9b6  ldloc.s  7
0x9a9b8  ldloc.s  0xA
0x9a9ba  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x9a9bf  callvirt instance void Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::set_QueryCommand(string value)
0x9a9c4  ldarg.1
0x9a9c5  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x9a9ca  ldloc.s  7
0x9a9cc  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::Add(var<u1>)
0x9a9d1  ldarg.0
0x9a9d2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_controlToCommandMap
0x9a9d7  ldloc.s  7
0x9a9d9  callvirt instance string Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_ID()
0x9a9de  ldloc.s  5
0x9a9e0  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x9a9e5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x9a9ea  ldarg.0
0x9a9eb  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_controlToCommandMap
0x9a9f0  ldloc.s  4
0x9a9f2  ldloc.s  0xA
0x9a9f4  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x9a9f9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x9a9fe  br       loc_9AAA8
0x9aa03  ldarg.0
0x9aa04  ldfld    bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::_hasServiceType
0x9aa09  brfalse.s loc_9AA5A
0x9aa0b  ldarg.3
0x9aa0c  ldloc.3
0x9aa0d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>>::get_Item(void)
0x9aa12  ldstr    aServicetype// "servicetype"
0x9aa17  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x9aa1c  ldc.i4.1
0x9aa1d  stloc.s  8
0x9aa1f  ldloca.s 8
0x9aa21  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9aa26  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9aa2b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x9aa30  brfalse.s loc_9AAA8
0x9aa32  ldarg.1
0x9aa33  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x9aa38  ldloc.s  7
0x9aa3a  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::Add(var<u1>)
0x9aa3f  ldarg.0
0x9aa40  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_controlToCommandMap
0x9aa45  ldloc.s  7
0x9aa47  callvirt instance string Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_ID()
0x9aa4c  ldloc.s  5
0x9aa4e  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x9aa53  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x9aa58  br.s     loc_9AAA8
0x9aa5a  ldarg.1
0x9aa5b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x9aa60  ldloc.s  7
0x9aa62  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::Add(var<u1>)
0x9aa67  ldarg.0
0x9aa68  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_controlToCommandMap
0x9aa6d  ldloc.s  7
0x9aa6f  callvirt instance string Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_ID()
0x9aa74  ldloc.s  5
0x9aa76  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x9aa7b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x9aa80  br.s     loc_9AAA8
0x9aa82  ldarg.1
0x9aa83  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x9aa88  ldloc.s  7
0x9aa8a  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::Add(var<u1>)
0x9aa8f  ldarg.0
0x9aa90  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_controlToCommandMap
0x9aa95  ldloc.s  7
0x9aa97  callvirt instance string Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_ID()
0x9aa9c  ldloc.s  5
0x9aa9e  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x9aaa3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x9aaa8  ldloca.s 2
0x9aaaa  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x9aaaf  brtrue   loc_9A8A0
0x9aab4  leave.s  loc_9AAC4
0x9aab6  ldloca.s 2
0x9aab8  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x9aabe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9aac3  endfinally
0x9aac4  ret
```
