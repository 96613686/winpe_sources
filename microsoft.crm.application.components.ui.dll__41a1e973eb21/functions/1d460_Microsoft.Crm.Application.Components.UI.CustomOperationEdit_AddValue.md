# Microsoft.Crm.Application.Components.UI.CustomOperationEdit::AddValue

- ea: `0x1d460`
- end: `0x1d491`
- name: `Microsoft.Crm.Application.Components.UI.CustomOperationEdit::AddValue`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1d4a0`

## callees

- `0x1d460`
- `0x1e920`

## string_xrefs

- `0x1d473`: `Value already exisit`

## pseudocode

```c

```

## disassembly

```asm
0x1d460  ldarg.0
0x1d461  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue> Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_values
0x1d466  ldarg.1
0x1d467  callvirt instance string Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::get_Name()
0x1d46c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue>::ContainsKey(var<u1>)
0x1d471  brfalse.s loc_1D47E
0x1d473  ldstr    aValueAlreadyEx// "Value already exisit"
0x1d478  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x1d47d  throw
0x1d47e  ldarg.0
0x1d47f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue> Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_values
0x1d484  ldarg.1
0x1d485  callvirt instance string Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue::get_Name()
0x1d48a  ldarg.1
0x1d48b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.CustomOperationListItemValue>::Add(var<u1>, !!T0)
0x1d490  ret
```
