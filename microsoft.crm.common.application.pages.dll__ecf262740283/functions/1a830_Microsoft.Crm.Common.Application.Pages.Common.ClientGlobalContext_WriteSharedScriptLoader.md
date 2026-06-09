# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteSharedScriptLoader

- ea: `0x1a830`
- end: `0x1a853`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteSharedScriptLoader`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1a700`

## string_xrefs

- `0x1a838`: `document.write(`

## pseudocode

```c

```

## disassembly

```asm
0x1a830  ldarg.1
0x1a831  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.SharedScript::GetScriptTagString()
0x1a836  stloc.0
0x1a837  ldarg.0
0x1a838  ldstr    aDocumentWrite// "document.write("
0x1a83d  ldloc.0
0x1a83e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1a843  ldstr    asc_31980// ");"
0x1a848  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a84d  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a852  ret
```
