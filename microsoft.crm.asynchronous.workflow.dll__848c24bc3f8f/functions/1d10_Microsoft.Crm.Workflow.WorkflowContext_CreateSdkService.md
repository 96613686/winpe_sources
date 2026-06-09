# Microsoft.Crm.Workflow.WorkflowContext::CreateSdkService

- ea: `0x1d10`
- end: `0x1d22`
- name: `Microsoft.Crm.Workflow.WorkflowContext::CreateSdkService`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1d10  ldarg.0
0x1d11  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_workflowInstanceData
0x1d16  castclass [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent
0x1d1b  ldarg.1
0x1d1c  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0x1d21  ret
```
