# Microsoft.Crm.Application.Components.UI.Select::AddExpando

- ea: `0x26850`
- end: `0x26872`
- name: `Microsoft.Crm.Application.Components.UI.Select::AddExpando`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1e140`

## callees

- `0x24210`
- `0x26850`

## string_xrefs

- `0x2685e`: `When setting the onchange event, use the OnChange accessor and not the AddExpando method of the select control.`

## pseudocode

```c

```

## disassembly

```asm
0x26850  ldarg.1
0x26851  ldstr    aOnchange_0// "onchange"
0x26856  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2685b  brfalse.s loc_26869
0x2685d  ldc.i4.0
0x2685e  ldstr    aWhenSettingThe_0// "When setting the onchange event, use th"...
0x26863  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x26868  ret
0x26869  ldarg.0
0x2686a  ldarg.1
0x2686b  ldarg.2
0x2686c  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x26871  ret
```
