# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteScriptReference

- ea: `0x1a860`
- end: `0x1a892`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteScriptReference`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1a700`
- `0x1a8e0`

## string_xrefs

- `0x1a86d`: `document.write('<script type="text/javascript" src="'+`

## pseudocode

```c

```

## disassembly

```asm
0x1a860  ldarg.1
0x1a861  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a866  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a86b  stloc.0
0x1a86c  ldarg.0
0x1a86d  ldstr    aDocumentWriteS_0// "document.write('<script type=\"text/jav"...
0x1a872  ldloc.0
0x1a873  callvirt instance string [mscorlib]System.Object::ToString()
0x1a878  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1a87d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1a882  ldstr    aScript_0// "+'\"></'+'script>')"
0x1a887  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a88c  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a891  ret
```
