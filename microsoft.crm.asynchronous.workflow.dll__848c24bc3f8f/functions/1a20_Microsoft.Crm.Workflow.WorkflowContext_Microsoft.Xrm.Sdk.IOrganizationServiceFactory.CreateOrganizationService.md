# Microsoft.Crm.Workflow.WorkflowContext::Microsoft.Xrm.Sdk.IOrganizationServiceFactory.CreateOrganizationService

- ea: `0x1a20`
- end: `0x1a6c`
- name: `Microsoft.Crm.Workflow.WorkflowContext::Microsoft.Xrm.Sdk.IOrganizationServiceFactory.CreateOrganizationService`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a20`

## pseudocode

```c

```

## disassembly

```asm
0x1a20  ldarga.s 1
0x1a22  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x1a27  brfalse.s loc_1A49
0x1a29  ldarga.s 1
0x1a2b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x1a30  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a35  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a3a  brfalse.s loc_1A49
0x1a3c  ldarga.s 1
0x1a3e  ldarg.0
0x1a3f  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_UserId()
0x1a44  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x1a49  ldarg.0
0x1a4a  ldfld    class [Microsoft.Crm]Microsoft.Crm.AsyncOperationData [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_operationData
0x1a4f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm]Microsoft.Crm.AsyncOperationData::get_CallerOrigin()
0x1a54  ldarg.0
0x1a55  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_workflowInstanceData
0x1a5a  castclass [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent
0x1a5f  ldarg.1
0x1a60  ldarg.0
0x1a61  call     instance class [mscorlib]System.Reflection.Assembly [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_ProxyTypesAssembly()
0x1a66  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>, class [mscorlib]System.Reflection.Assembly)
0x1a6b  ret
```
