# Microsoft.Crm.Application.Components.UI.EditableSelect::AddExpando

- ea: `0x17a30`
- end: `0x17a52`
- name: `Microsoft.Crm.Application.Components.UI.EditableSelect::AddExpando`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x17a30`
- `0x24210`

## string_xrefs

- `0x17a3e`: `When setting the onchange event, use the OnChange accessor and not the AddExpando method of the editable select control.`

## pseudocode

```c

```

## disassembly

```asm
0x17a30  ldarg.1
0x17a31  ldstr    aOnchange_0// "onchange"
0x17a36  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17a3b  brfalse.s loc_17A49
0x17a3d  ldc.i4.0
0x17a3e  ldstr    aWhenSettingThe// "When setting the onchange event, use th"...
0x17a43  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x17a48  ret
0x17a49  ldarg.0
0x17a4a  ldarg.1
0x17a4b  ldarg.2
0x17a4c  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x17a51  ret
```
