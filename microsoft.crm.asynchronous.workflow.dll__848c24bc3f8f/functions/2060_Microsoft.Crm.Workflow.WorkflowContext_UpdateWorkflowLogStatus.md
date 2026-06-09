# Microsoft.Crm.Workflow.WorkflowContext::UpdateWorkflowLogStatus

- ea: `0x2060`
- end: `0x20c2`
- name: `Microsoft.Crm.Workflow.WorkflowContext::UpdateWorkflowLogStatus`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2060`
- `0x28b0`

## pseudocode

```c

```

## disassembly

```asm
0x2060  ldarg.0
0x2061  ldfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_workflowLogId
0x2066  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x206b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2070  brfalse.s loc_20C1
0x2072  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x2077  stloc.0
0x2078  ldloc.0
0x2079  ldstr    aWorkflowlog// "workflowlog"
0x207e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x2083  ldloc.0
0x2084  ldarg.0
0x2085  ldfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_workflowLogId
0x208a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x208f  ldloc.0
0x2090  ldstr    aStatus// "status"
0x2095  ldarg.1
0x2096  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x209b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x20a0  ldloc.0
0x20a1  ldstr    aModifiedon_0// "modifiedon"
0x20a6  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x20ab  box      [mscorlib]System.DateTime
0x20b0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x20b5  ldarg.0
0x20b6  ldfld    class Microsoft.Crm.Workflow.IWorkflowLogPersistentStrategy Microsoft.Crm.Workflow.WorkflowContext::_workflowLogPersistentStrategy
0x20bb  ldloc.0
0x20bc  callvirt instance void Microsoft.Crm.Workflow.IWorkflowLogPersistentStrategy::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x20c1  ret
```
