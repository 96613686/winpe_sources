# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteStyleReference

- ea: `0x1a8a0`
- end: `0x1a8d2`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteStyleReference`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1a8e0`

## string_xrefs

- `0x1a8ad`: `document.write('<link rel="stylesheet" href="'+`

## pseudocode

```c

```

## disassembly

```asm
0x1a8a0  ldarg.1
0x1a8a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a8a6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a8ab  stloc.0
0x1a8ac  ldarg.0
0x1a8ad  ldstr    aDocumentWriteL// "document.write('<link rel=\"stylesheet"...
0x1a8b2  ldloc.0
0x1a8b3  callvirt instance string [mscorlib]System.Object::ToString()
0x1a8b8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1a8bd  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1a8c2  ldstr    asc_34D4A// "+'\">')"
0x1a8c7  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a8cc  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a8d1  ret
```
