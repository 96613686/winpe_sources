# Microsoft.Crm.Application.Components.UI.PicklistEdit::BuildScript

- ea: `0x1c2c0`
- end: `0x1c2f9`
- name: `Microsoft.Crm.Application.Components.UI.PicklistEdit::BuildScript`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1c0f0`

## string_xrefs

- `0x1c2cb`: `_listEditComponent`
- `0x1c2db`: `{0}.runCommand('{1}');`

## pseudocode

```c

```

## disassembly

```asm
0x1c2c0  ldarg.0
0x1c2c1  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1c2c6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1c2cb  ldstr    aListeditcompon// "_listEditComponent"
0x1c2d0  call     string [mscorlib]System.String::Concat(string, string)
0x1c2d5  stloc.0
0x1c2d6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c2db  ldstr    a0Runcommand1// "{0}.runCommand('{1}');"
0x1c2e0  ldc.i4.2
0x1c2e1  newarr   [mscorlib]System.Object
0x1c2e6  dup
0x1c2e7  ldc.i4.0
0x1c2e8  ldloc.0
0x1c2e9  stelem.ref
0x1c2ea  dup
0x1c2eb  ldc.i4.1
0x1c2ec  ldarg.1
0x1c2ed  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1c2f2  stelem.ref
0x1c2f3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1c2f8  ret
```
