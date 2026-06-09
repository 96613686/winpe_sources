# Microsoft.Crm.Service.ObjectModel.WorkflowAuthorServiceFactory::Create

- ea: `0xb430`
- end: `0xb467`
- name: `Microsoft.Crm.Service.ObjectModel.WorkflowAuthorServiceFactory::Create`
- size: `55`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x5680`
- `0x81c0`
- `0x8db0`
- `0x9fc0`

## callees

- `0x60c0`
- `0x89c0`
- `0xafb0`
- `0xb430`

## pseudocode

```c

```

## disassembly

```asm
0xb430  ldnull
0xb431  stloc.0
0xb432  ldarg.3
0xb433  switch   loc_B446, loc_B451, loc_B45C
0xb444  br.s     loc_B465
0xb446  ldarg.0
0xb447  ldarg.1
0xb448  ldarg.2
0xb449  newobj   instance void Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthorService::.ctor(string entityName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xb44e  stloc.0
0xb44f  br.s     loc_B465
0xb451  ldarg.0
0xb452  ldarg.1
0xb453  ldarg.2
0xb454  newobj   instance void Microsoft.Crm.Service.ObjectModel.RoutingRuleWorkflowAuthorService::.ctor(string entityName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xb459  stloc.0
0xb45a  br.s     loc_B465
0xb45c  ldarg.0
0xb45d  ldarg.1
0xb45e  ldarg.2
0xb45f  newobj   instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthorService::.ctor(string entityName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xb464  stloc.0
0xb465  ldloc.0
0xb466  ret
```
