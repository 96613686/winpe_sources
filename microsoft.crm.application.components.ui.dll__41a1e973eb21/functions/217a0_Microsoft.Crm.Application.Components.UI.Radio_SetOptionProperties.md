# Microsoft.Crm.Application.Components.UI.Radio::SetOptionProperties

- ea: `0x217a0`
- end: `0x2182d`
- name: `Microsoft.Crm.Application.Components.UI.Radio::SetOptionProperties`
- size: `141`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x21630`
- `0x216c0`

## callees

- `0x217a0`
- `0x21890`
- `0x218c0`
- `0x23c20`
- `0x23c30`
- `0x24260`
- `0x24290`

## pseudocode

```c

```

## disassembly

```asm
0x217a0  ldarg.1
0x217a1  ldarg.0
0x217a2  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x217a7  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x217ac  ldarg.1
0x217ad  ldarg.0
0x217ae  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x217b3  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::set_ReadOnly(bool value)
0x217b8  ldarg.0
0x217b9  ldstr    aAtype// "atype"
0x217be  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::GetExpando(string name)
0x217c3  stloc.0
0x217c4  ldarg.0
0x217c5  ldfld    string Microsoft.Crm.Application.Components.UI.Radio::_value
0x217ca  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x217cf  brfalse.s loc_21812
0x217d1  ldc.i4.5
0x217d2  stloc.1
0x217d3  ldloca.s 1
0x217d5  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType
0x217db  callvirt instance string [mscorlib]System.Object::ToString()
0x217e0  ldloc.0
0x217e1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x217e6  brtrue.s loc_21807
0x217e8  ldc.i4.0
0x217e9  stloc.1
0x217ea  ldloca.s 1
0x217ec  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType
0x217f2  callvirt instance string [mscorlib]System.Object::ToString()
0x217f7  ldloc.0
0x217f8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x217fd  brtrue.s loc_21807
0x217ff  ldloc.0
0x21800  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x21805  brfalse.s loc_21812
0x21807  ldarg.0
0x21808  ldstr    a1_0// "-1"
0x2180d  stfld    string Microsoft.Crm.Application.Components.UI.Radio::_value
0x21812  ldarg.1
0x21813  callvirt instance string Microsoft.Crm.Application.Components.UI.RadioOption::get_Value()
0x21818  ldarg.0
0x21819  ldfld    string Microsoft.Crm.Application.Components.UI.Radio::_value
0x2181e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x21823  brfalse.s loc_2182C
0x21825  ldarg.1
0x21826  ldc.i4.1
0x21827  callvirt instance void Microsoft.Crm.Application.Components.UI.RadioOption::set_Checked(bool value)
0x2182c  ret
```
