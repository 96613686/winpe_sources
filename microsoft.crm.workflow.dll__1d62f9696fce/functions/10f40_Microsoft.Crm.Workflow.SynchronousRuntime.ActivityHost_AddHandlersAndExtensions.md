# Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::AddHandlersAndExtensions

- ea: `0x10f40`
- end: `0x10f9e`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::AddHandlersAndExtensions`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x51a0`
- `0x15ff0`
- `0x16cc0`
- `0x18860`
- `0x18ca0`
- `0x19010`

## pseudocode

```c

```

## disassembly

```asm
0x10f40  ldarg.0
0x10f41  ldarg.1
0x10f42  ldarg.2
0x10f43  call     instance void Microsoft.Crm.Workflow.ActivityHostBase::AddHandlersAndExtensions(class [System.Activities]System.Activities.WorkflowApplication activityInstance, class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10f48  ldarg.1
0x10f49  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x10f4e  ldarg.2
0x10f4f  newobj   instance void Microsoft.Crm.Workflow.Services.SynchronousExpressionService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10f54  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x10f59  ldarg.1
0x10f5a  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x10f5f  ldarg.2
0x10f60  newobj   instance void Microsoft.Crm.Workflow.Services.InteractionActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10f65  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x10f6a  ldarg.1
0x10f6b  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x10f70  ldarg.2
0x10f71  newobj   instance void Microsoft.Crm.Workflow.Services.InteractionPageActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10f76  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x10f7b  ldarg.1
0x10f7c  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x10f81  ldarg.2
0x10f82  newobj   instance void Microsoft.Crm.Workflow.Services.QueryDataActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10f87  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x10f8c  ldarg.1
0x10f8d  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x10f92  ldarg.2
0x10f93  newobj   instance void Microsoft.Crm.Workflow.Services.ChildInteractiveWorkflowActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10f98  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x10f9d  ret
```
