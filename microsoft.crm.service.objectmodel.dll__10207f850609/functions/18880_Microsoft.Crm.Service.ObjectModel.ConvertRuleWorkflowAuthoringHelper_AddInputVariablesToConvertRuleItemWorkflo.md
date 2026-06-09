# Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddInputVariablesToConvertRuleItemWorkflow

- ea: `0x18880`
- end: `0x189ea`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddInputVariablesToConvertRuleItemWorkflow`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x17e90`

## callees

- `0x18880`
- `0x189f0`
- `0x18ac0`
- `0x18b00`
- `0x18b20`

## pseudocode

```c

```

## disassembly

```asm
0x18880  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18885  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1888a  ldarg.1
0x1888b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x18890  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x18895  stloc.0
0x18896  ldloc.0
0x18897  call     void Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::RemoveExistingWorkflowVariables(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x1889c  ldarg.2
0x1889d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x188a2  brtrue.s loc_188AB
0x188a4  ldloc.0
0x188a5  ldarg.2
0x188a6  call     void Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddPropertyBagRelatedParamsAsInputVariable(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string channelPropertyGroupId)
0x188ab  ldloc.0
0x188ac  ldstr    aConversionscen// "ConversionScenario"
0x188b1  ldc.i4.5
0x188b2  ldtoken  [mscorlib]System.Int32
0x188b7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x188bc  ldc.i4.1
0x188bd  box      [mscorlib]System.Int32
0x188c2  call     string Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddParameterAsInputVariable(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string variableName, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType workflowType, class [mscorlib]System.Type systemType, object value)
0x188c7  pop
0x188c8  ldloc.0
0x188c9  ldstr    aAllowprimaryac// "AllowPrimaryActionBlockRecordCreation"
0x188ce  ldc.i4.5
0x188cf  ldtoken  [mscorlib]System.Int32
0x188d4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x188d9  ldc.i4.1
0x188da  box      [mscorlib]System.Int32
0x188df  call     string Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddParameterAsInputVariable(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string variableName, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType workflowType, class [mscorlib]System.Type systemType, object value)
0x188e4  pop
0x188e5  ldloc.0
0x188e6  ldstr    aCaseorigin// "caseorigin"
0x188eb  ldc.i4.5
0x188ec  ldtoken  [mscorlib]System.Int32
0x188f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x188f6  ldc.i4.m1
0x188f7  box      [mscorlib]System.Int32
0x188fc  call     string Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddParameterAsInputVariable(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string variableName, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType workflowType, class [mscorlib]System.Type systemType, object value)
0x18901  pop
0x18902  ldloca.s 4
0x18904  initobj  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x1890a  ldloca.s 4
0x1890c  ldc.i4.5
0x1890d  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32)
0x18912  ldloca.s 4
0x18914  ldstr    aResolvedsender// "ResolvedSenderReference"
0x18919  ldc.i4.6
0x1891a  ldc.i4.1
0x1891b  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x18920  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string)
0x18925  ldloca.s 4
0x18927  ldc.i4.0
0x18928  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_IsMetadataBound(bool)
0x1892d  ldloca.s 4
0x1892f  ldsfld   valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::Empty
0x18934  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_MetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x18939  ldloca.s 4
0x1893b  ldc.i4.0
0x1893c  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_HasValue(bool)
0x18941  ldloc.s  4
0x18943  stloc.1
0x18944  ldloc.0
0x18945  ldloc.1
0x18946  call     string Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddParameterAsInputVariable(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition definition)
0x1894b  pop
0x1894c  ldloca.s 4
0x1894e  initobj  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x18954  ldloca.s 4
0x18956  ldc.i4.5
0x18957  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32)
0x1895c  ldloca.s 4
0x1895e  ldstr    aResolvedsender_0// "ResolvedSenderContactReference"
0x18963  ldc.i4.6
0x18964  ldc.i4.1
0x18965  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x1896a  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string)
0x1896f  ldloca.s 4
0x18971  ldc.i4.0
0x18972  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_IsMetadataBound(bool)
0x18977  ldloca.s 4
0x18979  ldsfld   valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::Empty
0x1897e  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_MetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x18983  ldloca.s 4
0x18985  ldc.i4.0
0x18986  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_HasValue(bool)
0x1898b  ldloc.s  4
0x1898d  stloc.2
0x1898e  ldloc.0
0x1898f  ldloc.2
0x18990  call     string Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddParameterAsInputVariable(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition definition)
0x18995  pop
0x18996  ldloca.s 4
0x18998  initobj  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x1899e  ldloca.s 4
0x189a0  ldc.i4.5
0x189a1  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32)
0x189a6  ldloca.s 4
0x189a8  ldstr    aSenderforautor// "SenderForAutoResponse"
0x189ad  ldc.i4.6
0x189ae  ldc.i4.1
0x189af  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x189b4  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string)
0x189b9  ldloca.s 4
0x189bb  ldc.i4.0
0x189bc  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_IsMetadataBound(bool)
0x189c1  ldloca.s 4
0x189c3  ldsfld   valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::Empty
0x189c8  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_MetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x189cd  ldloca.s 4
0x189cf  ldc.i4.0
0x189d0  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_HasValue(bool)
0x189d5  ldloc.s  4
0x189d7  stloc.3
0x189d8  ldloc.0
0x189d9  ldloc.3
0x189da  call     string Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddParameterAsInputVariable(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition definition)
0x189df  pop
0x189e0  ldarg.0
0x189e1  ldloc.0
0x189e2  ldarg.3
0x189e3  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::Save(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext)
0x189e8  pop
0x189e9  ret
```
