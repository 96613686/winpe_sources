# Microsoft.Crm.Application.WebServices.EmailToCaseDefaultPropertiesProvider::GetPrimaryContactIdDefaultProperty

- ea: `0xc60`
- end: `0xc7f`
- name: `Microsoft.Crm.Application.WebServices.EmailToCaseDefaultPropertiesProvider::GetPrimaryContactIdDefaultProperty`
- size: `31`
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
0xc60  ldstr    aResolvedsender_0// "ResolvedSenderContactReference"
0xc65  call     class Microsoft.Crm.Application.WebServices.IExpressionProvider Microsoft.Crm.Application.WebServices.InputParameterExpressionProviderFactory::GetExpressionProvider(string inputParameterName)
0xc6a  ldarg.1
0xc6b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase[] Microsoft.Crm.Application.WebServices.IExpressionProvider::GetExpressions(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xc70  stloc.0
0xc71  ldstr    aPrimarycontact// "primarycontactid"
0xc76  ldloc.0
0xc77  ldc.i4.0
0xc78  ldelem.ref
0xc79  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::.ctor(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0xc7e  ret
```
