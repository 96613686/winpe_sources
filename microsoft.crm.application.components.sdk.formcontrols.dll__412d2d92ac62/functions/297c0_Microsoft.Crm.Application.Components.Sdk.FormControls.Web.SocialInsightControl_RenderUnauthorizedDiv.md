# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderUnauthorizedDiv

- ea: `0x297c0`
- end: `0x2980e`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderUnauthorizedDiv`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x293e0`

## callees

- `0x17a10`

## string_xrefs

- `0x297d8`: `NetBreeze.Runtime.AskOwnerToConfigure`

## pseudocode

```c

```

## disassembly

```asm
0x297c0  ldarg.1
0x297c1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x297c6  ldstr    aDivIdUnauthori// "<div id='unauthorized' class='unauthori"...
0x297cb  ldc.i4.2
0x297cc  newarr   [mscorlib]System.Object
0x297d1  dup
0x297d2  ldc.i4.0
0x297d3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x297d8  ldstr    aNetbreezeRunti_7// "NetBreeze.Runtime.AskOwnerToConfigure"
0x297dd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x297e2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x297e7  stelem.ref
0x297e8  dup
0x297e9  ldc.i4.1
0x297ea  ldarg.0
0x297eb  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x297f0  stloc.0
0x297f1  ldloca.s 0
0x297f3  ldstr    aD// "D"
0x297f8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x297fd  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x29802  stelem.ref
0x29803  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x29808  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2980d  ret
```
