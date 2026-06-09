# Microsoft.Crm.Service.ObjectModel.RoutingRuleWorkflowAuthorService::.ctor

- ea: `0x89c0`
- end: `0x89d0`
- name: `Microsoft.Crm.Service.ObjectModel.RoutingRuleWorkflowAuthorService::.ctor`
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

- `0x89c2`: `Microsoft.Crm.Service.Application.Platform.WorkflowLibrary.RoutingWorkflowAuthoringHelper`

## pseudocode

```c

```

## disassembly

```asm
0x89c0  ldarg.0
0x89c1  ldarg.1
0x89c2  ldstr    aMicrosoftCrmSe_0// "Microsoft.Crm.Service.Application.Platf"...
0x89c7  ldc.i4.1
0x89c8  ldarg.2
0x89c9  ldarg.3
0x89ca  call     instance void Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::.ctor(string entityName, string wfAuthoringType, valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorType type, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x89cf  ret
```
