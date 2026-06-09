# Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::BuildConvertRuleItemWorkflowAuthoringHelper

- ea: `0x19510`
- end: `0x195b5`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::BuildConvertRuleItemWorkflowAuthoringHelper`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x19410`
- `0x19490`

## callees

- `0x19510`
- `0x19fc0`

## pseudocode

```c

```

## disassembly

```asm
0x19510  ldarg.3
0x19511  ldc.i4.2
0x19512  bne.un.s loc_19561
0x19514  ldarg.0
0x19515  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x1951a  ldstr    aConvertruleite_1// "convertruleitem"
0x1951f  ldarg.1
0x19520  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x19525  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1952a  ldc.i4.1
0x1952b  newarr   [mscorlib]System.String
0x19530  dup
0x19531  ldc.i4.0
0x19532  ldstr    aWorkflowid// "workflowid"
0x19537  stelem.ref
0x19538  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x1953d  ldc.i4.1
0x1953e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, bool)
0x19543  ldstr    aWorkflowid// "workflowid"
0x19548  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1954d  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x19552  stloc.0
0x19553  ldarg.0
0x19554  ldloc.0
0x19555  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1955a  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_workflowId
0x1955f  br.s     loc_195AD
0x19561  ldarg.3
0x19562  ldc.i4.3
0x19563  beq.s    loc_19569
0x19565  ldarg.3
0x19566  ldc.i4.4
0x19567  bne.un.s loc_195AD
0x19569  ldarg.1
0x1956a  ldstr    aWorkflowid// "workflowid"
0x1956f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19574  brfalse.s loc_195AD
0x19576  ldarg.1
0x19577  ldstr    aWorkflowid// "workflowid"
0x1957c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19581  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x19586  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x1958b  brfalse.s loc_195AD
0x1958d  ldarg.0
0x1958e  ldarg.1
0x1958f  ldstr    aWorkflowid// "workflowid"
0x19594  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19599  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x1959e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x195a3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x195a8  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_workflowId
0x195ad  ldarg.0
0x195ae  ldarg.1
0x195af  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::SetConditionXml(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity currentEntity)
0x195b4  ret
```
