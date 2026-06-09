# Microsoft.Crm.Workflow.LegacyWorkflowContext::CreateMetadataService_0

- ea: `0x1150`
- end: `0x1184`
- name: `Microsoft.Crm.Workflow.LegacyWorkflowContext::CreateMetadataService_0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1150`

## pseudocode

```c

```

## disassembly

```asm
0x1150  ldloca.s 0
0x1152  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x1158  ldarg.1
0x1159  brtrue.s loc_116D
0x115b  ldloca.s 0
0x115d  ldarg.0
0x115e  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x1163  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_UserId()
0x1168  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x116d  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ICrmServiceFactory [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.LegacyCrmServiceFactory::get_Instance()
0x1172  ldarg.0
0x1173  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x1178  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x117d  ldloc.0
0x117e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IMetadataService [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ICrmServiceFactory::CreateMetadataService(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x1183  ret
```
