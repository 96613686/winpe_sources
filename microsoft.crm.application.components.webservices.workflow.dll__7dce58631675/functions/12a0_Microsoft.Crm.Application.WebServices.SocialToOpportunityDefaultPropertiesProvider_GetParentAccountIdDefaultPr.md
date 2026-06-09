# Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetParentAccountIdDefaultProperty

- ea: `0x12a0`
- end: `0x12f7`
- name: `Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetParentAccountIdDefaultProperty`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x11f0`

## callees

- `0x1420`
- `0x1440`

## pseudocode

```c

```

## disassembly

```asm
0x12a0  ldarg.1
0x12a1  ldstr    aPostauthor// "postauthor"
0x12a6  ldstr    aContact// "contact"
0x12ab  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x12b0  stloc.0
0x12b1  ldarg.1
0x12b2  ldstr    aPostauthor// "postauthor"
0x12b7  ldstr    aAccount// "account"
0x12bc  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x12c1  stloc.1
0x12c2  ldc.i4.2
0x12c3  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression
0x12c8  dup
0x12c9  ldc.i4.0
0x12ca  ldloc.0
0x12cb  ldstr    aParentcustomer// "parentcustomerid"
0x12d0  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x12d5  stelem.ref
0x12d6  dup
0x12d7  ldc.i4.1
0x12d8  ldloc.1
0x12d9  ldstr    aAccountid// "accountid"
0x12de  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x12e3  stelem.ref
0x12e4  stloc.2
0x12e5  ldstr    aParentaccounti// "parentaccountid"
0x12ea  ldloc.2
0x12eb  ldarg.1
0x12ec  newobj   instance void Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::.ctor(string targetAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression[] sourceAttributeExpressions, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x12f1  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::GetProperty()
0x12f6  ret
```
