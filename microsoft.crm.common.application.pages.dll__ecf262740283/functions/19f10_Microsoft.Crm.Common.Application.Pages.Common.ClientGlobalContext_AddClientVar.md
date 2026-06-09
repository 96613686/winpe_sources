# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar

- ea: `0x19f10`
- end: `0x19f1f`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar`
- size: `15`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1a050`
- `0x1a420`
- `0x1a5b0`
- `0x1a8e0`

## callees

- `0x19f80`

## pseudocode

```c

```

## disassembly

```asm
0x19f10  ldarg.0
0x19f11  ldarg.1
0x19f12  ldarg.2
0x19f13  ldarg.3
0x19f14  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x19f19  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVarInternal(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x19f1e  ret
```
