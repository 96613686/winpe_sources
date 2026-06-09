# Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::UpgradeConvertRuleItem

- ea: `0x197f0`
- end: `0x19887`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::UpgradeConvertRuleItem`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x17e90`

## callees

- `0x195d0`
- `0x19710`
- `0x19740`
- `0x197f0`
- `0x199b0`

## string_xrefs

- `0x1981e`: `propertiesxml`
- `0x19833`: `propertiesxml`

## pseudocode

```c

```

## disassembly

```asm
0x197f0  ldarg.0
0x197f1  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowErrorVisitorContext::.ctor()
0x197f6  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::CreateWorkflowInternal(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext workflowErrorVisitorContext)
0x197fb  stloc.0
0x197fc  ldarg.0
0x197fd  ldloc.0
0x197fe  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::AddCreateIncidentPrimaryActionStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x19803  stloc.1
0x19804  ldc.i4   0x2455
0x19809  stloc.2
0x1980a  ldloca.s 2
0x1980c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19811  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x19816  ldloc.1
0x19817  ldloc.0
0x19818  call     void Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::AddDefaultProperties(string rendererTypeCode, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep createStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep rootWorkflowStep)
0x1981d  ldarg.1
0x1981e  ldstr    aPropertiesxml// "propertiesxml"
0x19823  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x19828  brfalse.s loc_19847
0x1982a  ldarg.0
0x1982b  ldloc.0
0x1982c  ldloc.1
0x1982d  ldarg.1
0x1982e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x19833  ldstr    aPropertiesxml// "propertiesxml"
0x19838  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x1983d  callvirt instance string [mscorlib]System.Object::ToString()
0x19842  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::UpdateIncidentPropertiesStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep createStep, string propertiesXml)
0x19847  ldarg.0
0x19848  ldloc.0
0x19849  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowErrorVisitorContext::.ctor()
0x1984e  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::Save(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext)
0x19853  pop
0x19854  ldarg.1
0x19855  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1985a  ldstr    aWorkflowid// "workflowid"
0x1985f  ldstr    aWorkflow_0// "workflow"
0x19864  ldloc.0
0x19865  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x1986a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x1986f  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x19874  ldarg.0
0x19875  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x1987a  ldarg.1
0x1987b  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x19880  ldloc.0
0x19881  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x19886  ret
```
