# Microsoft.Crm.Application.WebServices.EmailToOpportunityDefaultPropertiesProvider::GetParentContactIdDefaultProperty

- ea: `0xdc0`
- end: `0xddf`
- name: `Microsoft.Crm.Application.WebServices.EmailToOpportunityDefaultPropertiesProvider::GetParentContactIdDefaultProperty`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xd50`

## callees

- `0x14e0`
- `0x16e0`

## pseudocode

```c

```

## disassembly

```asm
0xdc0  ldstr    aResolvedsender_0// "ResolvedSenderContactReference"
0xdc5  call     class Microsoft.Crm.Application.WebServices.IExpressionProvider Microsoft.Crm.Application.WebServices.InputParameterExpressionProviderFactory::GetExpressionProvider(string inputParameterName)
0xdca  ldarg.1
0xdcb  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase[] Microsoft.Crm.Application.WebServices.IExpressionProvider::GetExpressions(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xdd0  stloc.0
0xdd1  ldstr    aParentcontacti// "parentcontactid"
0xdd6  ldloc.0
0xdd7  ldc.i4.0
0xdd8  ldelem.ref
0xdd9  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::.ctor(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0xdde  ret
```
