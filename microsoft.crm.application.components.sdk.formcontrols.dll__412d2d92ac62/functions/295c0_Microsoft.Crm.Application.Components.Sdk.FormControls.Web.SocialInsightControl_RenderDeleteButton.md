# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderDeleteButton

- ea: `0x295c0`
- end: `0x29610`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderDeleteButton`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x294f0`

## callees

- `0x17a10`

## string_xrefs

- `0x295c5`: `<div id='delete' class='button delete' title='{0}' tabindex='{1}'></div>`
- `0x295d7`: `NetBreeze.Runtime.DeleteConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x295c0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x295c5  ldstr    aDivIdDeleteCla// "<div id='delete' class='button delete' "...
0x295ca  ldc.i4.2
0x295cb  newarr   [mscorlib]System.Object
0x295d0  dup
0x295d1  ldc.i4.0
0x295d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x295d7  ldstr    aNetbreezeRunti_1// "NetBreeze.Runtime.DeleteConfiguration"
0x295dc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x295e1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x295e6  stelem.ref
0x295e7  dup
0x295e8  ldc.i4.1
0x295e9  ldarg.0
0x295ea  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x295ef  stloc.1
0x295f0  ldloca.s 1
0x295f2  ldstr    aD// "D"
0x295f7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x295fc  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x29601  stelem.ref
0x29602  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x29607  stloc.0
0x29608  ldarg.1
0x29609  ldloc.0
0x2960a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2960f  ret
```
