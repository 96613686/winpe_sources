# Microsoft.Crm.Workflow.LegacyWorkflowContext::CreateMetadataService

- ea: `0x1120`
- end: `0x1146`
- name: `Microsoft.Crm.Workflow.LegacyWorkflowContext::CreateMetadataService`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1120  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ICrmServiceFactory [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.LegacyCrmServiceFactory::get_Instance()
0x1125  ldarg.0
0x1126  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x112b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x1130  ldarg.0
0x1131  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x1136  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_UserId()
0x113b  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x1140  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IMetadataService [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ICrmServiceFactory::CreateMetadataService(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x1145  ret
```
