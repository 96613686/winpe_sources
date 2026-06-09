# Microsoft.Crm.Workflow.Services.WorkflowService::SetWorkflowLoggingProperty

- ea: `0x1a5e0`
- end: `0x1a647`
- name: `Microsoft.Crm.Workflow.Services.WorkflowService::SetWorkflowLoggingProperty`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a650`

## callees

- `0x6960`
- `0x6970`
- `0x6980`
- `0x69a0`
- `0x1a550`

## string_xrefs

- `0x1a616`: `WorkflowAutoDeleteSet`

## pseudocode

```c

```

## disassembly

```asm
0x1a5e0  ldarg.1
0x1a5e1  callvirt T0x2B000009
0x1a5e6  stloc.0
0x1a5e7  ldloc.0
0x1a5e8  ldarg.0
0x1a5e9  ldloc.0
0x1a5ea  ldarg.2
0x1a5eb  call     instance bool Microsoft.Crm.Workflow.Services.WorkflowService::IsLoggingEnabled(class Microsoft.Crm.Workflow.ICommonWorkflowContext workflowContext, class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.Workflow workflow)
0x1a5f0  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::set_IsLoggingEnabled(bool value)
0x1a5f5  ldarg.1
0x1a5f6  callvirt instance class [System.Activities]System.Activities.ExecutionProperties [System.Activities]System.Activities.NativeActivityContext::get_Properties()
0x1a5fb  ldstr    aWorkflowloggin// "WorkflowLoggingEnabled"
0x1a600  ldloc.0
0x1a601  callvirt instance bool Microsoft.Crm.Workflow.ICommonWorkflowContext::get_IsLoggingEnabled()
0x1a606  box      [mscorlib]System.Boolean
0x1a60b  callvirt instance void [System.Activities]System.Activities.ExecutionProperties::Add(string, object)
0x1a610  ldarg.1
0x1a611  callvirt instance class [System.Activities]System.Activities.ExecutionProperties [System.Activities]System.Activities.NativeActivityContext::get_Properties()
0x1a616  ldstr    aWorkflowautode// "WorkflowAutoDeleteSet"
0x1a61b  ldloc.0
0x1a61c  callvirt instance bool Microsoft.Crm.Workflow.ICommonWorkflowContext::get_IsAutoDeleteSet()
0x1a621  box      [mscorlib]System.Boolean
0x1a626  callvirt instance void [System.Activities]System.Activities.ExecutionProperties::Add(string, object)
0x1a62b  ldarg.1
0x1a62c  callvirt instance class [System.Activities]System.Activities.ExecutionProperties [System.Activities]System.Activities.NativeActivityContext::get_Properties()
0x1a631  ldstr    aIscrmuiworkflo_0// "IsCrmUIWorkflow"
0x1a636  ldloc.0
0x1a637  callvirt instance bool Microsoft.Crm.Workflow.ICommonWorkflowContext::get_IsCrmUIWorkflow()
0x1a63c  box      [mscorlib]System.Boolean
0x1a641  callvirt instance void [System.Activities]System.Activities.ExecutionProperties::Add(string, object)
0x1a646  ret
```
