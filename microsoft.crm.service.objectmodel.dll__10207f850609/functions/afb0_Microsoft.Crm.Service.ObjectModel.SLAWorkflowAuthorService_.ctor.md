# Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthorService::.ctor

- ea: `0xafb0`
- end: `0xafc0`
- name: `Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthorService::.ctor`
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

- `0xafb2`: `Microsoft.Crm.Service.Application.Platform.WorkflowLibrary.SLAWorkflowAuthoringHelper`

## pseudocode

```c

```

## disassembly

```asm
0xafb0  ldarg.0
0xafb1  ldarg.1
0xafb2  ldstr    aMicrosoftCrmSe_2// "Microsoft.Crm.Service.Application.Platf"...
0xafb7  ldc.i4.0
0xafb8  ldarg.2
0xafb9  ldarg.3
0xafba  call     instance void Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::.ctor(string entityName, string wfAuthoringType, valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorType type, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xafbf  ret
```
