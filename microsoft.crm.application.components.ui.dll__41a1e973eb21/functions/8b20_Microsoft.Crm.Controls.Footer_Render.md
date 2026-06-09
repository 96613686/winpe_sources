# Microsoft.Crm.Controls.Footer::Render

- ea: `0x8b20`
- end: `0x8b58`
- name: `Microsoft.Crm.Controls.Footer::Render`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x2320`
- `0x3a60`
- `0x6400`
- `0x91a0`
- `0x2a5f0`

## string_xrefs

- `0x8b33`: `<link rel="stylesheet" type="text/css" href="{0}" id="{1}" />`

## pseudocode

```c

```

## disassembly

```asm
0x8b20  ldarg.0
0x8b21  call     instance void Microsoft.Crm.Controls.Footer::ConfigureForRendering()
0x8b26  ldarg.0
0x8b27  ldarg.1
0x8b28  ldarg.0
0x8b29  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_styles
0x8b2e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Values()
0x8b33  ldstr    aLinkRelStylesh// "<link rel=\"stylesheet\" type=\"text/cs"...
0x8b38  ldnull
0x8b39  ldftn    string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x8b3f  newobj   instance void EncodingFunction::.ctor(object object, native int method)
0x8b44  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteList(class [mscorlib]System.IO.TextWriter output, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> list, string mask, class EncodingFunction encodingFunction)
0x8b49  ldarg.0
0x8b4a  ldc.i4.1
0x8b4b  call     instance void Microsoft.Crm.Controls.PageResourceManager::set_HasRendered(bool value)
0x8b50  ldarg.0
0x8b51  ldarg.1
0x8b52  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::RenderScripts(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x8b57  ret
```
