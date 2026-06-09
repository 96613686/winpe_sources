# Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::GetWorkflowAuthorType

- ea: `0x9460`
- end: `0x947c`
- name: `Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::GetWorkflowAuthorType`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x60d0`
- `0x9310`

## string_xrefs

- `0x9466`: `,Microsoft.Crm.Service.Application.Components.Platform`

## pseudocode

```c

```

## disassembly

```asm
0x9460  ldarg.0
0x9461  ldfld    string Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::_workflowAuthoringTypeFormat
0x9466  ldstr    aMicrosoftCrmSe_1// ",Microsoft.Crm.Service.Application.Comp"...
0x946b  call     string [mscorlib]System.String::Concat(string, string)
0x9470  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string)
0x9475  ldc.i4.1
0x9476  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool)
0x947b  ret
```
