# Microsoft.Crm.Workflow.ActivityHost::AddHandlersAndExtensions

- ea: `0x5d0`
- end: `0x637`
- name: `Microsoft.Crm.Workflow.ActivityHost::AddHandlersAndExtensions`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x3c0`

## callees

- `0x5d0`
- `0x3440`
- `0x3620`

## pseudocode

```c

```

## disassembly

```asm
0x5d0  ldarg.0
0x5d1  ldarg.1
0x5d2  ldarg.2
0x5d3  call     instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::AddHandlersAndExtensions(class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext)
0x5d8  ldarg.2
0x5d9  isinst   Microsoft.Crm.Workflow.WorkflowContext
0x5de  stloc.0
0x5df  ldloc.0
0x5e0  brfalse.s loc_5F4
0x5e2  ldarg.1
0x5e3  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x5e8  ldloc.0
0x5e9  ldloc.0
0x5ea  newobj   instance void [Microsoft.Crm.ServiceBus]Microsoft.Crm.ServiceBus.ServiceBusService::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext)
0x5ef  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x5f4  ldarg.0
0x5f5  ldftn    instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::WorkflowResolveOrganizationConfiguration(valuetype [mscorlib]System.Guid)
0x5fb  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowResolveOrganizationConfiguration::.ctor(object, native int)
0x600  ldarg.2
0x601  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x606  ldarg.2
0x607  newobj   instance void ContextService::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowResolveOrganizationConfiguration organizationConfigurationResolver, valuetype [mscorlib]System.Guid instanceId, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x60c  stloc.1
0x60d  ldarg.1
0x60e  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x613  ldloc.1
0x614  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x619  ldarg.1
0x61a  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x61f  ldarg.3
0x620  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x625  ldarg.1
0x626  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x62b  ldarg.2
0x62c  newobj   instance void Microsoft.Crm.Workflow.Services.AsyncExpressionService::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x631  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x636  ret
```
