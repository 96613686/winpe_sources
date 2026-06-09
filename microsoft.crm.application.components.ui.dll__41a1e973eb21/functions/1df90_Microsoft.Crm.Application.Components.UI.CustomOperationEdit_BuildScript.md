# Microsoft.Crm.Application.Components.UI.CustomOperationEdit::BuildScript

- ea: `0x1df90`
- end: `0x1dfbf`
- name: `Microsoft.Crm.Application.Components.UI.CustomOperationEdit::BuildScript`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1ddc0`

## string_xrefs

- `0x1dfa1`: `$find('{0}').runCommand('{1}');`

## pseudocode

```c

```

## disassembly

```asm
0x1df90  ldarg.0
0x1df91  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1df96  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1df9b  stloc.0
0x1df9c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1dfa1  ldstr    aFind0Runcomman// "$find('{0}').runCommand('{1}');"
0x1dfa6  ldc.i4.2
0x1dfa7  newarr   [mscorlib]System.Object
0x1dfac  dup
0x1dfad  ldc.i4.0
0x1dfae  ldloc.0
0x1dfaf  stelem.ref
0x1dfb0  dup
0x1dfb1  ldc.i4.1
0x1dfb2  ldarg.1
0x1dfb3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1dfb8  stelem.ref
0x1dfb9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1dfbe  ret
```
