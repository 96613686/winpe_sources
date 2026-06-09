# Microsoft.Crm.Application.WebServices.EmailToCaseDefaultPropertiesProvider::GetCaseOriginCodeDefaultProperty

- ea: `0xc30`
- end: `0xc57`
- name: `Microsoft.Crm.Application.WebServices.EmailToCaseDefaultPropertiesProvider::GetCaseOriginCodeDefaultProperty`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xbb0`

## callees

- `0x14e0`
- `0x16e0`

## pseudocode

```c

```

## disassembly

```asm
0xc30  ldstr    aCaseorigin// "caseorigin"
0xc35  call     class Microsoft.Crm.Application.WebServices.IExpressionProvider Microsoft.Crm.Application.WebServices.InputParameterExpressionProviderFactory::GetExpressionProvider(string inputParameterName)
0xc3a  ldarg.1
0xc3b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase[] Microsoft.Crm.Application.WebServices.IExpressionProvider::GetExpressions(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xc40  stloc.0
0xc41  ldarg.1
0xc42  ldc.i4.s 0x16
0xc44  ldloc.0
0xc45  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0xc4a  stloc.1
0xc4b  ldstr    aCaseorigincode// "caseorigincode"
0xc50  ldloc.1
0xc51  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::.ctor(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0xc56  ret
```
