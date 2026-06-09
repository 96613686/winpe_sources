# Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddIncidentPropertiesAndSendEmailStep

- ea: `0x18d40`
- end: `0x18dbd`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddIncidentPropertiesAndSendEmailStep`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x17e90`

## callees

- `0x18d40`
- `0x18e00`
- `0x18e90`
- `0x19120`

## string_xrefs

- `0x18d62`: `propertiesxml`
- `0x18d73`: `propertiesxml`

## pseudocode

```c

```

## disassembly

```asm
0x18d40  ldarg.0
0x18d41  ldarg.1
0x18d42  ldarg.2
0x18d43  ldarg.3
0x18d44  ldstr    asc_1EEAE// ""
0x18d49  ldarg.s  6
0x18d4b  ldarg.s  7
0x18d4d  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::CreateIncidentStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase parentStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition inputArgument, string descriptionXml, string originInputArgumentName, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition inputArgumentContact)
0x18d52  stloc.0
0x18d53  ldarg.0
0x18d54  ldloc.0
0x18d55  ldarg.1
0x18d56  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddUpdatePrimaryEntityStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep createStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x18d5b  ldarg.s  4
0x18d5d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x18d62  ldstr    aPropertiesxml// "propertiesxml"
0x18d67  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x18d6c  brfalse.s loc_18D8C
0x18d6e  ldarg.0
0x18d6f  ldarg.1
0x18d70  ldloc.0
0x18d71  ldarg.s  4
0x18d73  ldstr    aPropertiesxml// "propertiesxml"
0x18d78  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x18d7d  callvirt instance string [mscorlib]System.Object::ToString()
0x18d82  ldstr    aIncident_0// "incident"
0x18d87  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::UpdateIncidentPropertiesStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflow, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep createStep, string xml, string entityName)
0x18d8c  ldarg.0
0x18d8d  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::convertRuleEntity
0x18d92  ldstr    aSendautomaticr// "sendautomaticresponse"
0x18d97  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x18d9c  unbox.any [mscorlib]System.Boolean
0x18da1  brfalse.s loc_18DB4
0x18da3  ldarg.0
0x18da4  ldarg.1
0x18da5  ldarg.2
0x18da6  ldloc.0
0x18da7  ldarg.s  5
0x18da9  ldarg.0
0x18daa  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::responseTemplateId
0x18daf  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddSendEmailStepForConvertRuleAndConvertRuleItemWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition, valuetype [mscorlib]System.Guid)
0x18db4  ldarg.0
0x18db5  ldarg.1
0x18db6  ldarg.2
0x18db7  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::StopWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase)
0x18dbc  ret
```
