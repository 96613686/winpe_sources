# Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowContext::CreateWorkflowLog

- ea: `0x119a0`
- end: `0x11a8c`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowContext::CreateWorkflowLog`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1b0`
- `0x75e0`
- `0x7780`
- `0x7a00`
- `0x9100`
- `0x119a0`

## pseudocode

```c

```

## disassembly

```asm
0x119a0  ldarg.0
0x119a1  call     instance class Microsoft.Crm.Workflow.WorkflowLogsProperty Microsoft.Crm.Workflow.WorkflowContextBase::get_WorkflowLogsProperty()
0x119a6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Workflow.WorkflowLogsProperty::get_LogIds()
0x119ab  ldarg.1
0x119ac  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x119b1  brfalse.s loc_119C5
0x119b3  ldarg.0
0x119b4  call     instance class Microsoft.Crm.Workflow.WorkflowLogsProperty Microsoft.Crm.Workflow.WorkflowContextBase::get_WorkflowLogsProperty()
0x119b9  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Workflow.WorkflowLogsProperty::get_LogIds()
0x119be  ldarg.1
0x119bf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::get_Item(void)
0x119c4  ret
0x119c5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x119ca  stloc.0
0x119cb  ldloc.0
0x119cc  ldstr    aWorkflowlog// "workflowlog"
0x119d1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x119d6  ldloc.0
0x119d7  ldstr    aAsyncoperation_0// "asyncoperationid"
0x119dc  ldstr    aProcesssession_0// "processsession"
0x119e1  ldarg.0
0x119e2  ldfld    class Microsoft.Crm.Asynchronous.IGenericEventData Microsoft.Crm.Workflow.WorkflowContextBase::_workflowInstanceData
0x119e7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IGenericEventData::get_EventId()
0x119ec  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x119f1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x119f6  ldloc.0
0x119f7  ldstr    aStatus// "status"
0x119fc  ldc.i4.1
0x119fd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x11a02  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x11a07  ldloc.0
0x11a08  ldstr    aActivityname// "activityname"
0x11a0d  ldarg.1
0x11a0e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x11a13  ldarg.2
0x11a14  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11a19  brtrue.s loc_11A27
0x11a1b  ldloc.0
0x11a1c  ldstr    aStepname// "stepname"
0x11a21  ldarg.2
0x11a22  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x11a27  ldarg.3
0x11a28  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11a2d  brtrue.s loc_11A3B
0x11a2f  ldloc.0
0x11a30  ldstr    aDescription// "description"
0x11a35  ldarg.3
0x11a36  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x11a3b  ldarg.0
0x11a3c  call     instance string Microsoft.Crm.Workflow.WorkflowContextBase::get_StageName()
0x11a41  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11a46  brtrue.s loc_11A59
0x11a48  ldloc.0
0x11a49  ldstr    aStagename// "stagename"
0x11a4e  ldarg.0
0x11a4f  call     instance string Microsoft.Crm.Workflow.WorkflowContextBase::get_StageName()
0x11a54  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x11a59  ldarg.0
0x11a5a  ldc.i4.1
0x11a5b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.WorkflowContextBase::CreateSdkService(bool asAdminUser)
0x11a60  stloc.1
0x11a61  ldarg.0
0x11a62  ldloc.1
0x11a63  ldloc.0
0x11a64  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x11a69  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::_workflowLogId
0x11a6e  ldarg.0
0x11a6f  call     instance class Microsoft.Crm.Workflow.WorkflowLogsProperty Microsoft.Crm.Workflow.WorkflowContextBase::get_WorkflowLogsProperty()
0x11a74  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Workflow.WorkflowLogsProperty::get_LogIds()
0x11a79  ldarg.1
0x11a7a  ldarg.0
0x11a7b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::_workflowLogId
0x11a80  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::set_Item(var<u1>, !!T0)
0x11a85  ldarg.0
0x11a86  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::_workflowLogId
0x11a8b  ret
```
