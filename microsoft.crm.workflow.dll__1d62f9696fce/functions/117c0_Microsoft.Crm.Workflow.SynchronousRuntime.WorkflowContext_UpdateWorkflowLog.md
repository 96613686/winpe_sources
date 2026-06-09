# Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowContext::UpdateWorkflowLog

- ea: `0x117c0`
- end: `0x118cb`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowContext::UpdateWorkflowLog`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x7a00`
- `0xdee0`
- `0xe0c0`
- `0x11560`
- `0x117c0`

## string_xrefs

- `0x11854`: `completedon`

## pseudocode

```c

```

## disassembly

```asm
0x117c0  ldarg.1
0x117c1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x117c6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x117cb  brfalse  loc_118CA
0x117d0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x117d5  stloc.0
0x117d6  ldloc.0
0x117d7  ldstr    aWorkflowlog// "workflowlog"
0x117dc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x117e1  ldloc.0
0x117e2  ldarg.1
0x117e3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x117e8  ldloc.0
0x117e9  ldstr    aStatus// "status"
0x117ee  ldarg.s  4
0x117f0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x117f5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x117fa  ldarg.0
0x117fb  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Workflow.WorkflowContextBase::_stepRegardingRecord
0x11800  brfalse.s loc_11815
0x11802  ldloc.0
0x11803  ldstr    aRegardingobjec_0// "regardingobjectid"
0x11808  ldarg.0
0x11809  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Workflow.WorkflowContextBase::_stepRegardingRecord
0x1180e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x11813  br.s     loc_11821
0x11815  ldloc.0
0x11816  ldstr    aRegardingobjec_0// "regardingobjectid"
0x1181b  ldnull
0x1181c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x11821  ldarg.0
0x11822  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::_childWorkflowInstanceId
0x11827  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1182c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x11831  brfalse.s loc_1184E
0x11833  ldloc.0
0x11834  ldstr    aChildworkflowi// "childworkflowinstanceid"
0x11839  ldstr    aProcesssession_0// "processsession"
0x1183e  ldarg.0
0x1183f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::_childWorkflowInstanceId
0x11844  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x11849  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1184e  ldarg.s  4
0x11850  ldc.i4.2
0x11851  bne.un.s loc_11868
0x11853  ldloc.0
0x11854  ldstr    aCompletedon// "completedon"
0x11859  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1185e  box      [mscorlib]System.DateTime
0x11863  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x11868  ldarg.3
0x11869  brfalse.s loc_11877
0x1186b  ldloc.0
0x1186c  ldstr    aMessage// "message"
0x11871  ldarg.3
0x11872  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x11877  ldarg.2
0x11878  brfalse.s loc_1188B
0x1187a  ldloc.0
0x1187b  ldstr    aErrorcode// "errorcode"
0x11880  ldarg.2
0x11881  box      [mscorlib]System.Int32
0x11886  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1188b  ldarg.0
0x1188c  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowContext::get_InteractiveWorkflowInputContext()
0x11891  callvirt instance class Microsoft.Crm.Workflow.PageResult Microsoft.Crm.Workflow.InteractiveWorkflowInputContext::get_PageResult()
0x11896  callvirt instance string Microsoft.Crm.Workflow.PageResult::get_CurrentInteractionResult()
0x1189b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x118a0  brtrue.s loc_118BD
0x118a2  ldloc.0
0x118a3  ldstr    aInteractionact_0// "interactionactivityresult"
0x118a8  ldarg.0
0x118a9  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowContext::get_InteractiveWorkflowInputContext()
0x118ae  callvirt instance class Microsoft.Crm.Workflow.PageResult Microsoft.Crm.Workflow.InteractiveWorkflowInputContext::get_PageResult()
0x118b3  callvirt instance string Microsoft.Crm.Workflow.PageResult::get_CurrentInteractionResult()
0x118b8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x118bd  ldarg.0
0x118be  ldc.i4.1
0x118bf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.WorkflowContextBase::CreateSdkService(bool asAdminUser)
0x118c4  ldloc.0
0x118c5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x118ca  ret
```
