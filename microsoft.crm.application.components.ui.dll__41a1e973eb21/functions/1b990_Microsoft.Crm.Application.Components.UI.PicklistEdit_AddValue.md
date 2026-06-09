# Microsoft.Crm.Application.Components.UI.PicklistEdit::AddValue

- ea: `0x1b990`
- end: `0x1b9c1`
- name: `Microsoft.Crm.Application.Components.UI.PicklistEdit::AddValue`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1b9d0`
- `0x1ba00`
- `0x1ba30`

## callees

- `0x1b990`
- `0x1c940`

## string_xrefs

- `0x1b9a3`: `Value already exisit`

## pseudocode

```c

```

## disassembly

```asm
0x1b990  ldarg.0
0x1b991  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue> Microsoft.Crm.Application.Components.UI.PicklistEdit::_values
0x1b996  ldarg.1
0x1b997  callvirt instance int32 Microsoft.Crm.Application.Components.UI.ListItemValue::get_Value()
0x1b99c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue>::ContainsKey(var<u1>)
0x1b9a1  brfalse.s loc_1B9AE
0x1b9a3  ldstr    aValueAlreadyEx// "Value already exisit"
0x1b9a8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x1b9ad  throw
0x1b9ae  ldarg.0
0x1b9af  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue> Microsoft.Crm.Application.Components.UI.PicklistEdit::_values
0x1b9b4  ldarg.1
0x1b9b5  callvirt instance int32 Microsoft.Crm.Application.Components.UI.ListItemValue::get_Value()
0x1b9ba  ldarg.1
0x1b9bb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Components.UI.ListItemValue>::Add(var<u1>, !!T0)
0x1b9c0  ret
```
