# Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetCaseOriginCodeDefaultProperty

- ea: `0xfb0`
- end: `0xfd7`
- name: `Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetCaseOriginCodeDefaultProperty`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xeb0`

## callees

- `0x14e0`
- `0x16e0`

## pseudocode

```c

```

## disassembly

```asm
0xfb0  ldstr    aCaseorigin// "caseorigin"
0xfb5  call     class Microsoft.Crm.Application.WebServices.IExpressionProvider Microsoft.Crm.Application.WebServices.InputParameterExpressionProviderFactory::GetExpressionProvider(string inputParameterName)
0xfba  ldarg.1
0xfbb  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase[] Microsoft.Crm.Application.WebServices.IExpressionProvider::GetExpressions(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xfc0  stloc.0
0xfc1  ldarg.1
0xfc2  ldc.i4.s 0x16
0xfc4  ldloc.0
0xfc5  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0xfca  stloc.1
0xfcb  ldstr    aCaseorigincode// "caseorigincode"
0xfd0  ldloc.1
0xfd1  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::.ctor(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0xfd6  ret
```
