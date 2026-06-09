# Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthorService::.ctor

- ea: `0x60c0`
- end: `0x60d0`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthorService::.ctor`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb430`

## callees

- `0x92c0`

## string_xrefs

- `0x60c2`: `Microsoft.Crm.Service.Application.Platform.WorkflowLibrary.ConvertRuleWorkflowAuthoringHelper`

## pseudocode

```c

```

## disassembly

```asm
0x60c0  ldarg.0
0x60c1  ldarg.1
0x60c2  ldstr    aMicrosoftCrmSe// "Microsoft.Crm.Service.Application.Platf"...
0x60c7  ldc.i4.2
0x60c8  ldarg.2
0x60c9  ldarg.3
0x60ca  call     instance void Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::.ctor(string entityName, string wfAuthoringType, valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorType type, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x60cf  ret
```
