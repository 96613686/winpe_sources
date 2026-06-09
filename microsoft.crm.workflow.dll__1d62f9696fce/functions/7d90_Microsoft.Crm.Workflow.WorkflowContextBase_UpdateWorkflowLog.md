# Microsoft.Crm.Workflow.WorkflowContextBase::UpdateWorkflowLog

- ea: `0x7d90`
- end: `0x7e69`
- name: `Microsoft.Crm.Workflow.WorkflowContextBase::UpdateWorkflowLog`
- size: `217`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7970`
- `0x79e0`
- `0x10420`
- `0x118d0`

## callees

- `0x7a00`
- `0x7d90`

## string_xrefs

- `0x7e24`: `completedon`

## pseudocode

```c

```

## disassembly

```asm
0x7d90  ldarg.1
0x7d91  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7d96  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7d9b  brfalse  loc_7E68
0x7da0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x7da5  stloc.0
0x7da6  ldloc.0
0x7da7  ldstr    aWorkflowlog// "workflowlog"
0x7dac  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x7db1  ldloc.0
0x7db2  ldarg.1
0x7db3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x7db8  ldloc.0
0x7db9  ldstr    aStatus// "status"
0x7dbe  ldarg.s  4
0x7dc0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x7dc5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x7dca  ldarg.0
0x7dcb  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Workflow.WorkflowContextBase::_stepRegardingRecord
0x7dd0  brfalse.s loc_7DE5
0x7dd2  ldloc.0
0x7dd3  ldstr    aRegardingobjec_0// "regardingobjectid"
0x7dd8  ldarg.0
0x7dd9  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Workflow.WorkflowContextBase::_stepRegardingRecord
0x7dde  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x7de3  br.s     loc_7DF1
0x7de5  ldloc.0
0x7de6  ldstr    aRegardingobjec_0// "regardingobjectid"
0x7deb  ldnull
0x7dec  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x7df1  ldarg.0
0x7df2  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::_childWorkflowInstanceId
0x7df7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7dfc  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7e01  brfalse.s loc_7E1E
0x7e03  ldloc.0
0x7e04  ldstr    aChildworkflowi// "childworkflowinstanceid"
0x7e09  ldstr    aAsyncoperation// "asyncoperation"
0x7e0e  ldarg.0
0x7e0f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::_childWorkflowInstanceId
0x7e14  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x7e19  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x7e1e  ldarg.s  4
0x7e20  ldc.i4.2
0x7e21  bne.un.s loc_7E38
0x7e23  ldloc.0
0x7e24  ldstr    aCompletedon// "completedon"
0x7e29  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x7e2e  box      [mscorlib]System.DateTime
0x7e33  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x7e38  ldarg.3
0x7e39  brfalse.s loc_7E47
0x7e3b  ldloc.0
0x7e3c  ldstr    aMessage// "message"
0x7e41  ldarg.3
0x7e42  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x7e47  ldarg.2
0x7e48  brfalse.s loc_7E5B
0x7e4a  ldloc.0
0x7e4b  ldstr    aErrorcode// "errorcode"
0x7e50  ldarg.2
0x7e51  box      [mscorlib]System.Int32
0x7e56  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x7e5b  ldarg.0
0x7e5c  ldc.i4.1
0x7e5d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.WorkflowContextBase::CreateSdkService(bool asAdminUser)
0x7e62  ldloc.0
0x7e63  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x7e68  ret
```
