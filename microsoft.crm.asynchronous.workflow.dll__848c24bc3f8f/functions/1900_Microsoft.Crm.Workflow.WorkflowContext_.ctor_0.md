# Microsoft.Crm.Workflow.WorkflowContext::.ctor_0

- ea: `0x1900`
- end: `0x1969`
- name: `Microsoft.Crm.Workflow.WorkflowContext::.ctor_0`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18e0`
- `0x1900`

## callees

- `0xe60`
- `0x1900`
- `0x2870`
- `0x2fe0`

## pseudocode

```c

```

## disassembly

```asm
0x1900  ldarg.0
0x1901  ldarg.1
0x1902  ldarg.3
0x1903  ldnull
0x1904  call     instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IWorkflowContextService, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowSdkServiceFactory)
0x1909  ldarg.0
0x190a  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationSucceededResult::.ctor()
0x190f  stfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_workflowOperationStatus
0x1914  ldarg.0
0x1915  ldarg.s  4
0x1917  stfld    class [Microsoft.Crm]Microsoft.Crm.AsyncOperationData [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_operationData
0x191c  ldarg.0
0x191d  newobj   instance void Microsoft.Crm.Workflow.AsyncWorkflowInstanceState::.ctor()
0x1922  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1927  ldarg.0
0x1928  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x192d  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::Clear()
0x1932  ldarg.0
0x1933  ldarg.0
0x1934  newobj   instance void Microsoft.Crm.Workflow.LegacyWorkflowContext::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext workflowContext)
0x1939  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ILegacyWorkflowContext Microsoft.Crm.Workflow.WorkflowContext::_legacyContext
0x193e  ldarg.s  4
0x1940  callvirt instance class [Microsoft.Crm]Microsoft.Crm.AsyncOperationData [Microsoft.Crm]Microsoft.Crm.AsyncOperationData::get_ParentContext()
0x1945  brfalse.s loc_195C
0x1947  ldarg.0
0x1948  ldarg.1
0x1949  ldarg.2
0x194a  ldarg.3
0x194b  ldarg.s  4
0x194d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.AsyncOperationData [Microsoft.Crm]Microsoft.Crm.AsyncOperationData::get_ParentContext()
0x1952  newobj   instance void Microsoft.Crm.Workflow.WorkflowContext::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IWorkflowContextService workflowContextService, string serviceName, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData workflowInstanceData, class [Microsoft.Crm]Microsoft.Crm.AsyncOperationData operationData)
0x1957  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_parentContext
0x195c  ldarg.0
0x195d  ldarg.0
0x195e  call     class Microsoft.Crm.Workflow.IWorkflowLogPersistentStrategy Microsoft.Crm.Workflow.WorkflowLogPersistentStrategyFactory::GetWorkflowLogPersistentStrategy(class Microsoft.Crm.Workflow.WorkflowContext context)
0x1963  stfld    class Microsoft.Crm.Workflow.IWorkflowLogPersistentStrategy Microsoft.Crm.Workflow.WorkflowContext::_workflowLogPersistentStrategy
0x1968  ret
```
