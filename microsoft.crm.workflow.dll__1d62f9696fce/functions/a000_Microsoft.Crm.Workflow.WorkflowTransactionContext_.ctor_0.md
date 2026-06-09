# Microsoft.Crm.Workflow.WorkflowTransactionContext::.ctor_0

- ea: `0xa000`
- end: `0xa057`
- name: `Microsoft.Crm.Workflow.WorkflowTransactionContext::.ctor_0`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x9fe0`

## callees

- `0xa000`

## string_xrefs

- `0xa017`: `openExecutionContext`

## pseudocode

```c

```

## disassembly

```asm
0xa000  ldarg.0
0xa001  call     instance void [mscorlib]System.Object::.ctor()
0xa006  ldarg.1
0xa007  brtrue.s loc_A014
0xa009  ldstr    aWorkflowcontex// "workflowContext"
0xa00e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa013  throw
0xa014  ldarg.2
0xa015  brtrue.s loc_A022
0xa017  ldstr    aOpenexecutionc// "openExecutionContext"
0xa01c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa021  throw
0xa022  ldarg.3
0xa023  brtrue.s loc_A030
0xa025  ldstr    aDependencies// "dependencies"
0xa02a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa02f  throw
0xa030  ldarg.0
0xa031  ldarg.1
0xa032  stfld    class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.IWorkflowContext Microsoft.Crm.Workflow.WorkflowTransactionContext::workflowContext
0xa037  ldarg.0
0xa038  ldarg.2
0xa039  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IOpenExecutionContext Microsoft.Crm.Workflow.WorkflowTransactionContext::openExecutionContext
0xa03e  ldarg.0
0xa03f  ldarg.3
0xa040  stfld    class Microsoft.Crm.Workflow.IWorkflowTransactionContextDependencies Microsoft.Crm.Workflow.WorkflowTransactionContext::dependencies
0xa045  ldarg.0
0xa046  ldarg.0
0xa047  ldfld    class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.IWorkflowContext Microsoft.Crm.Workflow.WorkflowTransactionContext::workflowContext
0xa04c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0xa051  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowTransactionContext::transactionContextId
0xa056  ret
```
