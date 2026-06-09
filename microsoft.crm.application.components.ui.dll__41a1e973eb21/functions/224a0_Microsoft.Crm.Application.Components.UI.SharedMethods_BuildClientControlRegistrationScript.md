# Microsoft.Crm.Application.Components.UI.SharedMethods::BuildClientControlRegistrationScript

- ea: `0x224a0`
- end: `0x224c8`
- name: `Microsoft.Crm.Application.Components.UI.SharedMethods::BuildClientControlRegistrationScript`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x22480`
- `0x22490`

## string_xrefs

- `0x224a5`: `<script type="text/javascript">Sys.Application.add_init(function(){{crmCreate({0},{{}},null,null,$get({1}));}});</script>`

## pseudocode

```c

```

## disassembly

```asm
0x224a0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x224a5  ldstr    aScriptTypeText_10// "<script type=\"text/javascript\">Sys.Ap"...
0x224aa  ldc.i4.2
0x224ab  newarr   [mscorlib]System.Object
0x224b0  dup
0x224b1  ldc.i4.0
0x224b2  ldarg.0
0x224b3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x224b8  stelem.ref
0x224b9  dup
0x224ba  ldc.i4.1
0x224bb  ldarg.1
0x224bc  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x224c1  stelem.ref
0x224c2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x224c7  ret
```
