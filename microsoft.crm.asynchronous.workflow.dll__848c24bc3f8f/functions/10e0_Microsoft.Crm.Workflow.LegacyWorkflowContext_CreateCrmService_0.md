# Microsoft.Crm.Workflow.LegacyWorkflowContext::CreateCrmService_0

- ea: `0x10e0`
- end: `0x111f`
- name: `Microsoft.Crm.Workflow.LegacyWorkflowContext::CreateCrmService_0`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10e0`

## pseudocode

```c

```

## disassembly

```asm
0x10e0  ldloca.s 0
0x10e2  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x10e8  ldarg.1
0x10e9  brtrue.s loc_10FD
0x10eb  ldloca.s 0
0x10ed  ldarg.0
0x10ee  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x10f3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_UserId()
0x10f8  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x10fd  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ICrmServiceFactory [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.LegacyCrmServiceFactory::get_Instance()
0x1102  ldarg.0
0x1103  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x1108  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x110d  ldloc.0
0x110e  ldarg.0
0x110f  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x1114  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::get_CorrelationToken()
0x1119  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ICrmService [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ICrmServiceFactory::CreateCrmService(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken)
0x111e  ret
```
