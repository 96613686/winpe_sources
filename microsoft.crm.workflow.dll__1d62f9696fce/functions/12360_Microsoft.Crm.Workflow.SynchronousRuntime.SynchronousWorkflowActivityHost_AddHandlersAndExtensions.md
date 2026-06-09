# Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::AddHandlersAndExtensions

- ea: `0x12360`
- end: `0x124f3`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::AddHandlersAndExtensions`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x120a0`

## callees

- `0x6890`
- `0x14f00`
- `0x14f40`
- `0x155a0`
- `0x15b80`
- `0x15dc0`
- `0x16400`
- `0x16520`
- `0x165c0`
- `0x16ab0`
- `0x16cc0`
- `0x19180`
- `0x192e0`
- `0x194a0`
- `0x19630`
- `0x198d0`
- `0x19ab0`
- `0x19d10`
- `0x19e20`
- `0x1a3a0`
- `0x1a520`
- `0x1a7d0`

## pseudocode

```c

```

## disassembly

```asm
0x12360  ldarg.1
0x12361  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x12366  ldarg.2
0x12367  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x1236c  ldarg.1
0x1236d  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x12372  ldarg.0
0x12373  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ICrmServiceFactory Microsoft.Crm.Workflow.ActivityHostBase::_crmServiceFactory
0x12378  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x1237d  ldarg.1
0x1237e  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x12383  newobj   instance void Microsoft.Crm.Workflow.Services.ExecutionPointersService::.ctor()
0x12388  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x1238d  ldarg.1
0x1238e  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x12393  ldarg.2
0x12394  callvirt instance class Microsoft.Crm.Workflow.WorkflowTracingService Microsoft.Crm.Workflow.ICommonWorkflowContext::get_WorkflowTracingService()
0x12399  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x1239e  ldarg.1
0x1239f  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x123a4  ldarg.2
0x123a5  newobj   instance void Microsoft.Crm.Workflow.Services.AssignActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x123aa  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x123af  ldarg.1
0x123b0  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x123b5  ldarg.2
0x123b6  newobj   instance void Microsoft.Crm.Workflow.Services.CreateActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x123bb  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x123c0  ldarg.1
0x123c1  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x123c6  ldarg.2
0x123c7  newobj   instance void Microsoft.Crm.Workflow.Services.RetrieveActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x123cc  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x123d1  ldarg.1
0x123d2  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x123d7  ldarg.2
0x123d8  newobj   instance void Microsoft.Crm.Workflow.Services.SendEmailFromTemplateActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x123dd  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x123e2  ldarg.1
0x123e3  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x123e8  ldarg.2
0x123e9  newobj   instance void Microsoft.Crm.Workflow.Services.SendEmailActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x123ee  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x123f3  ldarg.1
0x123f4  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x123f9  ldarg.2
0x123fa  newobj   instance void Microsoft.Crm.Workflow.Services.SetStateActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x123ff  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x12404  ldarg.1
0x12405  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x1240a  ldarg.2
0x1240b  newobj   instance void Microsoft.Crm.Workflow.Services.UpdateActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x12410  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x12415  ldarg.1
0x12416  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x1241b  ldarg.2
0x1241c  newobj   instance void Microsoft.Crm.Workflow.Services.ChildWorkflowActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x12421  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x12426  ldarg.1
0x12427  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x1242c  ldarg.2
0x1242d  newobj   instance void Microsoft.Crm.Workflow.Services.ConditionBranchService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x12432  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x12437  ldarg.1
0x12438  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x1243d  ldarg.2
0x1243e  newobj   instance void Microsoft.Crm.Workflow.Services.ConditionActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x12443  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x12448  ldarg.1
0x12449  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x1244e  ldarg.2
0x1244f  newobj   instance void Microsoft.Crm.Workflow.Services.WorkflowService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x12454  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x12459  ldarg.1
0x1245a  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x1245f  ldarg.2
0x12460  newobj   instance void Microsoft.Crm.Workflow.Services.CompositeActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x12465  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x1246a  ldarg.1
0x1246b  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x12470  ldarg.2
0x12471  newobj   instance void Microsoft.Crm.Workflow.Services.ActivityReferenceService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x12476  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x1247b  ldarg.1
0x1247c  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x12481  ldarg.2
0x12482  newobj   instance void Microsoft.Crm.Workflow.Services.WebActivityReferenceService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x12487  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x1248c  ldarg.1
0x1248d  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x12492  ldarg.2
0x12493  newobj   instance void Microsoft.Crm.Workflow.Services.InvokeSdkMessageService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x12498  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x1249d  ldarg.1
0x1249e  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x124a3  ldarg.2
0x124a4  newobj   instance void Microsoft.Crm.Workflow.Services.SynchronousExpressionService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x124a9  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x124ae  ldarg.1
0x124af  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x124b4  ldarg.2
0x124b5  newobj   instance void Microsoft.Crm.Workflow.Services.SetAttributeValueService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x124ba  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x124bf  ldarg.1
0x124c0  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x124c5  ldarg.2
0x124c6  newobj   instance void Microsoft.Crm.Workflow.Services.SetDefaultValueService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x124cb  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x124d0  ldarg.1
0x124d1  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x124d6  ldarg.2
0x124d7  newobj   instance void Microsoft.Crm.Workflow.Services.SetMessageService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x124dc  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x124e1  ldarg.1
0x124e2  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x124e7  ldarg.2
0x124e8  newobj   instance void Microsoft.Crm.Workflow.Services.SetFieldRequiredLevelService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x124ed  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x124f2  ret
```
