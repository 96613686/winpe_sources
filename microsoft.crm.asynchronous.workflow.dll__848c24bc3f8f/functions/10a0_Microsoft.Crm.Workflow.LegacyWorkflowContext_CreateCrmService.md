# Microsoft.Crm.Workflow.LegacyWorkflowContext::CreateCrmService

- ea: `0x10a0`
- end: `0x10d1`
- name: `Microsoft.Crm.Workflow.LegacyWorkflowContext::CreateCrmService`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x10a0  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ICrmServiceFactory [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.LegacyCrmServiceFactory::get_Instance()
0x10a5  ldarg.0
0x10a6  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x10ab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x10b0  ldarg.0
0x10b1  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x10b6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_UserId()
0x10bb  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x10c0  ldarg.0
0x10c1  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x10c6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::get_CorrelationToken()
0x10cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ICrmService [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ICrmServiceFactory::CreateCrmService(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken)
0x10d0  ret
```
