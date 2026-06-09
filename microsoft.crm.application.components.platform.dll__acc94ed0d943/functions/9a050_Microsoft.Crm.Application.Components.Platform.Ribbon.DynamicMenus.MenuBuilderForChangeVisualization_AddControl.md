# Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForChangeVisualization::AddControlButtons

- ea: `0x9a050`
- end: `0x9a1ca`
- name: `Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForChangeVisualization::AddControlButtons`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x99f20`

## callees

- `0x2fb90`
- `0x4fbf0`
- `0x4fc00`
- `0x55800`
- `0x55820`
- `0x55840`
- `0x55860`
- `0x558c0`
- `0x558e0`
- `0x55900`
- `0x55ca0`
- `0x55cb0`
- `0x99340`
- `0x994d0`
- `0x994e0`
- `0x9a050`
- `0x9a1d0`
- `0x9a2c0`

## string_xrefs

- `0x9a08c`: `{0}QueryCommand{1}`
- `0x9a0b5`: `{0}ButtonCommand{1}`

## pseudocode

```c

```

## disassembly

```asm
0x9a050  ldc.i4.0
0x9a051  stloc.0
0x9a052  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9a057  stloc.1
0x9a058  ldarg.2
0x9a059  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ControlConfiguration>::GetEnumerator()
0x9a05e  stloc.2
0x9a05f  br       loc_9A1AD
0x9a064  ldloca.s 2
0x9a066  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ControlConfiguration>::get_Current()
0x9a06b  stloc.3
0x9a06c  ldloc.3
0x9a06d  ldloc.1
0x9a06e  ldarg.0
0x9a06f  ldflda   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>> Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForChangeVisualization::loadedDataSetResources
0x9a074  newobj   instance void Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::.ctor(class Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ControlConfiguration controlConfiguration, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext context, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>>& loadedDataSetResources)
0x9a079  stloc.s  4
0x9a07b  ldloc.s  4
0x9a07d  callvirt instance bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::get_IsForWeb()
0x9a082  brfalse  loc_9A1AD
0x9a087  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9a08c  ldstr    a0Querycommand1// "{0}QueryCommand{1}"
0x9a091  ldc.i4.2
0x9a092  newarr   [mscorlib]System.Object
0x9a097  dup
0x9a098  ldc.i4.0
0x9a099  ldarg.0
0x9a09a  call     instance string Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_CommandPrefix()
0x9a09f  stelem.ref
0x9a0a0  dup
0x9a0a1  ldc.i4.1
0x9a0a2  ldloc.0
0x9a0a3  box      [mscorlib]System.Int32
0x9a0a8  stelem.ref
0x9a0a9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9a0ae  stloc.s  5
0x9a0b0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9a0b5  ldstr    a0Buttoncommand// "{0}ButtonCommand{1}"
0x9a0ba  ldc.i4.2
0x9a0bb  newarr   [mscorlib]System.Object
0x9a0c0  dup
0x9a0c1  ldc.i4.0
0x9a0c2  ldarg.0
0x9a0c3  call     instance string Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_CommandPrefix()
0x9a0c8  stelem.ref
0x9a0c9  dup
0x9a0ca  ldc.i4.1
0x9a0cb  ldloc.0
0x9a0cc  box      [mscorlib]System.Int32
0x9a0d1  stelem.ref
0x9a0d2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9a0d7  stloc.s  6
0x9a0d9  ldarg.0
0x9a0da  ldloc.s  6
0x9a0dc  ldloc.3
0x9a0dd  ldloc.s  4
0x9a0df  call     instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForChangeVisualization::GetButtonCommandDefinition(string commandId, class Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ControlConfiguration controlConfiguration, class Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper customControl)
0x9a0e4  stloc.s  7
0x9a0e6  ldarg.0
0x9a0e7  ldloc.s  5
0x9a0e9  ldloc.3
0x9a0ea  call     instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForChangeVisualization::GetQueryCommandDefinition(string commandId, class Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ControlConfiguration controlConfiguration)
0x9a0ef  stloc.s  8
0x9a0f1  ldarg.3
0x9a0f2  ldloc.s  7
0x9a0f4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::Add(var<u1>)
0x9a0f9  ldarg.3
0x9a0fa  ldloc.s  8
0x9a0fc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::Add(var<u1>)
0x9a101  ldloc.s  4
0x9a103  callvirt instance string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::get_Name()
0x9a108  stloc.s  9
0x9a10a  ldarg.0
0x9a10b  call     instance string Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_IdPrefix()
0x9a110  ldloca.s 0
0x9a112  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9a117  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9a11c  call     string [mscorlib]System.String::Concat(string, string)
0x9a121  newobj   instance void Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::.ctor(string id)
0x9a126  stloc.s  0xA
0x9a128  ldloc.s  0xA
0x9a12a  ldloc.s  9
0x9a12c  callvirt instance void Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::set_Alt(string value)
0x9a131  ldloc.s  0xA
0x9a133  ldloc.s  9
0x9a135  callvirt instance void Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::set_ToolTipTitle(string value)
0x9a13a  ldloc.s  0xA
0x9a13c  ldloc.s  9
0x9a13e  callvirt instance void Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::set_LabelText(string value)
0x9a143  ldloc.s  0xA
0x9a145  ldloc.s  7
0x9a147  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x9a14c  callvirt instance void Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::set_Command(string value)
0x9a151  ldloc.s  0xA
0x9a153  ldc.i4.s 0xA
0x9a155  ldloc.0
0x9a156  add
0x9a157  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x9a15c  callvirt instance void Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::set_Sequence(valuetype [mscorlib]System.Nullable`1<int32> value)
0x9a161  ldloc.0
0x9a162  ldc.i4.1
0x9a163  add
0x9a164  stloc.0
0x9a165  ldloc.s  0xA
0x9a167  ldloc.s  8
0x9a169  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x9a16e  callvirt instance void Microsoft.Crm.Application.Ribbon.XmlRendering.ToggleButton::set_QueryCommand(string value)
0x9a173  ldarg.1
0x9a174  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x9a179  ldloc.s  0xA
0x9a17b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::Add(var<u1>)
0x9a180  ldarg.0
0x9a181  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_controlToCommandMap
0x9a186  ldloc.s  0xA
0x9a188  callvirt instance string Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_ID()
0x9a18d  ldloc.s  7
0x9a18f  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x9a194  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x9a199  ldarg.0
0x9a19a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_controlToCommandMap
0x9a19f  ldloc.s  5
0x9a1a1  ldloc.s  8
0x9a1a3  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x9a1a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x9a1ad  ldloca.s 2
0x9a1af  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ControlConfiguration>::MoveNext()
0x9a1b4  brtrue   loc_9A064
0x9a1b9  leave.s  loc_9A1C9
0x9a1bb  ldloca.s 2
0x9a1bd  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ControlConfiguration>
0x9a1c3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9a1c8  endfinally
0x9a1c9  ret
```
