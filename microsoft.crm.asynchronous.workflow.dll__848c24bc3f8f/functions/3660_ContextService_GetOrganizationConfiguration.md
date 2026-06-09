# ContextService::GetOrganizationConfiguration

- ea: `0x3660`
- end: `0x36a0`
- name: `ContextService::GetOrganizationConfiguration`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x36a0`
- `0x36c0`

## callees

- `0x3660`

## pseudocode

```c

```

## disassembly

```asm
0x3660  ldarg.1
0x3661  ldarg.0
0x3662  ldfld    valuetype [mscorlib]System.Guid ContextService::_instanceId
0x3667  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x366c  brfalse.s loc_3687
0x366e  ldc.i4   0x80040216
0x3673  ldc.i4.1
0x3674  newarr   [mscorlib]System.Object
0x3679  dup
0x367a  ldc.i4.0
0x367b  ldstr    aWorkflowInstan// "Workflow instance is not in memory"
0x3680  stelem.ref
0x3681  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3686  throw
0x3687  ldarg.0
0x3688  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext ContextService::_context
0x368d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x3692  stloc.0
0x3693  ldarg.0
0x3694  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowResolveOrganizationConfiguration ContextService::_organizationConfigurationResolver
0x3699  ldloc.0
0x369a  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowResolveOrganizationConfiguration::Invoke(valuetype [mscorlib]System.Guid)
0x369f  ret
```
