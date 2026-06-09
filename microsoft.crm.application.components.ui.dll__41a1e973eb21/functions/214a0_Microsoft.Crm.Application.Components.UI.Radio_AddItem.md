# Microsoft.Crm.Application.Components.UI.Radio::AddItem

- ea: `0x214a0`
- end: `0x2150c`
- name: `Microsoft.Crm.Application.Components.UI.Radio::AddItem`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1e140`
- `0x21510`

## callees

- `0x20f90`
- `0x20fc0`
- `0x214a0`
- `0x218d0`
- `0x218f0`
- `0x23c20`
- `0x23c30`
- `0x242c0`
- `0x242d0`

## pseudocode

```c

```

## disassembly

```asm
0x214a0  ldarg.0
0x214a1  ldfld    class Microsoft.Crm.Application.Components.UI.RadioOptionCollection Microsoft.Crm.Application.Components.UI.Radio::_options
0x214a6  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x214ab  ldc.i4.0
0x214ac  bgt.s    loc_214B1
0x214ae  ldc.i4.1
0x214af  br.s     loc_214D0
0x214b1  ldarg.0
0x214b2  ldfld    class Microsoft.Crm.Application.Components.UI.RadioOptionCollection Microsoft.Crm.Application.Components.UI.Radio::_options
0x214b7  ldarg.0
0x214b8  ldfld    class Microsoft.Crm.Application.Components.UI.RadioOptionCollection Microsoft.Crm.Application.Components.UI.Radio::_options
0x214bd  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x214c2  ldc.i4.1
0x214c3  sub
0x214c4  callvirt instance class Microsoft.Crm.Application.Components.UI.RadioOption Microsoft.Crm.Application.Components.UI.RadioOptionCollection::get_Item(int32 index)
0x214c9  callvirt instance int32 Microsoft.Crm.Application.Components.UI.RadioOption::get_OptionNumber()
0x214ce  ldc.i4.1
0x214cf  add
0x214d0  stloc.0
0x214d1  ldarg.1
0x214d2  ldarg.2
0x214d3  ldloc.0
0x214d4  newobj   instance void Microsoft.Crm.Application.Components.UI.RadioOption::.ctor(string label, string value, int32 optionNumber)
0x214d9  stloc.1
0x214da  ldloc.1
0x214db  ldarg.0
0x214dc  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x214e1  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x214e6  ldloc.1
0x214e7  ldarg.0
0x214e8  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x214ed  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::set_TabIndex(int32 value)
0x214f2  ldloc.1
0x214f3  ldarg.0
0x214f4  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x214f9  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x214fe  ldarg.0
0x214ff  ldfld    class Microsoft.Crm.Application.Components.UI.RadioOptionCollection Microsoft.Crm.Application.Components.UI.Radio::_options
0x21504  ldloc.1
0x21505  callvirt instance int32 Microsoft.Crm.Application.Components.UI.RadioOptionCollection::Add(class Microsoft.Crm.Application.Components.UI.RadioOption value)
0x2150a  pop
0x2150b  ret
```
