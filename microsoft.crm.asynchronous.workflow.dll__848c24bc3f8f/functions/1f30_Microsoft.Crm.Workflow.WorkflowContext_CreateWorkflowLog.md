# Microsoft.Crm.Workflow.WorkflowContext::CreateWorkflowLog

- ea: `0x1f30`
- end: `0x205f`
- name: `Microsoft.Crm.Workflow.WorkflowContext::CreateWorkflowLog`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1f30`
- `0x28c0`

## string_xrefs

- `0x1fea`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x1f30  ldarg.0
0x1f31  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowLogsProperty [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_WorkflowLogsProperty()
0x1f36  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowLogsProperty::get_LogIds()
0x1f3b  ldarg.1
0x1f3c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x1f41  brfalse.s loc_1F55
0x1f43  ldarg.0
0x1f44  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowLogsProperty [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_WorkflowLogsProperty()
0x1f49  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowLogsProperty::get_LogIds()
0x1f4e  ldarg.1
0x1f4f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::get_Item(void)
0x1f54  ret
0x1f55  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x1f5a  stloc.0
0x1f5b  ldloc.0
0x1f5c  ldstr    aWorkflowlog// "workflowlog"
0x1f61  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x1f66  ldloc.0
0x1f67  ldstr    aAsyncoperation_1// "asyncoperationid"
0x1f6c  ldstr    aAsyncoperation_2// "asyncoperation"
0x1f71  ldarg.0
0x1f72  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_workflowInstanceData
0x1f77  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData::get_EventId()
0x1f7c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x1f81  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1f86  ldloc.0
0x1f87  ldstr    aStatus// "status"
0x1f8c  ldc.i4.1
0x1f8d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1f92  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1f97  ldloc.0
0x1f98  ldstr    aActivityname// "activityname"
0x1f9d  ldarg.1
0x1f9e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1fa3  ldarg.2
0x1fa4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fa9  brtrue.s loc_1FB7
0x1fab  ldloc.0
0x1fac  ldstr    aStepname// "stepname"
0x1fb1  ldarg.2
0x1fb2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1fb7  ldarg.3
0x1fb8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fbd  brtrue.s loc_1FCB
0x1fbf  ldloc.0
0x1fc0  ldstr    aDescription// "description"
0x1fc5  ldarg.3
0x1fc6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1fcb  ldarg.0
0x1fcc  call     instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_StageName()
0x1fd1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fd6  brtrue.s loc_1FE9
0x1fd8  ldloc.0
0x1fd9  ldstr    aStagename// "stagename"
0x1fde  ldarg.0
0x1fdf  call     instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_StageName()
0x1fe4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1fe9  ldloc.0
0x1fea  ldstr    aCreatedon// "createdon"
0x1fef  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1ff4  box      [mscorlib]System.DateTime
0x1ff9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1ffe  ldloc.0
0x1fff  ldstr    aModifiedon_0// "modifiedon"
0x2004  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2009  box      [mscorlib]System.DateTime
0x200e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x2013  ldarg.0
0x2014  ldfld    class Microsoft.Crm.Workflow.IWorkflowLogPersistentStrategy Microsoft.Crm.Workflow.WorkflowContext::_workflowLogPersistentStrategy
0x2019  ldloc.0
0x201a  callvirt instance void Microsoft.Crm.Workflow.IWorkflowLogPersistentStrategy::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x201f  ldarg.0
0x2020  ldloc.0
0x2021  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x2026  stfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_workflowLogId
0x202b  ldloc.0
0x202c  ldstr    aWorkflowlogid// "workflowlogid"
0x2031  ldloc.0
0x2032  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x2037  box      [mscorlib]System.Guid
0x203c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x2041  ldarg.0
0x2042  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowLogsProperty [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_WorkflowLogsProperty()
0x2047  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowLogsProperty::get_LogIds()
0x204c  ldarg.1
0x204d  ldarg.0
0x204e  ldfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_workflowLogId
0x2053  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::set_Item(var<u1>, !!T0)
0x2058  ldarg.0
0x2059  ldfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_workflowLogId
0x205e  ret
```
