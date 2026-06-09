# Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::AddChildWorkflow

- ea: `0x15c90`
- end: `0x15e5f`
- name: `Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::AddChildWorkflow`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x15700`

## callees

- `0x15c90`
- `0x17500`

## string_xrefs

- `0x15d22`: `BusinessHoursId`

## pseudocode

```c

```

## disassembly

```asm
0x15c90  ldarg.2
0x15c91  ldarg.1
0x15c92  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x15c97  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x15c9c  stloc.0
0x15c9d  ldarg.0
0x15c9e  ldfld    bool Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::useSLAKPI
0x15ca3  brfalse.s loc_15CB8
0x15ca5  ldarg.0
0x15ca6  ldarg.2
0x15ca7  ldarg.1
0x15ca8  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::CheckInvokeChildWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string stepId)
0x15cad  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x15cb2  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x15cb7  stloc.0
0x15cb8  ldarg.2
0x15cb9  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x15cbe  stloc.1
0x15cbf  ldloc.1
0x15cc0  ldarg.s  4
0x15cc2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Description(string)
0x15cc7  ldloc.1
0x15cc8  ldarg.2
0x15cc9  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x15cce  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x15cd3  ldloc.1
0x15cd4  ldarg.2
0x15cd5  ldarg.2
0x15cd6  ldarg.3
0x15cd7  box      [mscorlib]System.Guid
0x15cdc  ldc.i4.s 0xF
0x15cde  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x15ce3  ldc.i4.6
0x15ce4  ldc.i4   0x125F
0x15ce9  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetObjName(int32)
0x15cee  ldloc.1
0x15cef  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Name()
0x15cf4  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x15cf9  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::set_ChildWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x15cfe  ldloc.0
0x15cff  ldloc.1
0x15d00  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x15d05  ldarg.0
0x15d06  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_WorkflowAdapter()
0x15d0b  ldarg.3
0x15d0c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x15d11  ldloc.1
0x15d12  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::get_Inputs()
0x15d17  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Clear()
0x15d1c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo::.ctor()
0x15d21  stloc.2
0x15d22  ldstr    aBusinesshoursi_0// "BusinessHoursId"
0x15d27  ldc.i4.6
0x15d28  ldc.i4.1
0x15d29  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x15d2e  stloc.3
0x15d2f  ldloc.2
0x15d30  ldloc.3
0x15d31  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Name(string)
0x15d36  dup
0x15d37  ldloc.3
0x15d38  ldc.i4.1
0x15d39  callvirt instance object [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetVariableValue(string, bool)
0x15d3e  unbox.any [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x15d43  stloc.s  4
0x15d45  ldloc.2
0x15d46  ldloc.s  4
0x15d48  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::.ctor(var<u1>)
0x15d4d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_IdentifierDefinition(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>)
0x15d52  ldloc.2
0x15d53  ldloca.s 4
0x15d55  call     instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::GetClrType()
0x15d5a  callvirt instance string [mscorlib]System.Type::get_FullName()
0x15d5f  call     class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractiveWorkflowTypeHelper::GetCrmTypeFromDotNetType(string)
0x15d64  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Type(class [mscorlib]System.Type)
0x15d69  ldloc.2
0x15d6a  ldloca.s 4
0x15d6c  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::GetWorkflowDataType()
0x15d71  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_WorkflowAttributeType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x15d76  ldloc.2
0x15d77  ldloc.3
0x15d78  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_DependencyPropertyName(string)
0x15d7d  ldloc.2
0x15d7e  ldc.i4.1
0x15d7f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Required(bool)
0x15d84  ldarg.2
0x15d85  ldarg.2
0x15d86  ldarg.0
0x15d87  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::lookupValue
0x15d8c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_Value()
0x15d91  box      [mscorlib]System.Guid
0x15d96  ldc.i4.s 0xF
0x15d98  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x15d9d  ldc.i4.6
0x15d9e  ldarg.0
0x15d9f  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::lookupValue
0x15da4  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_type()
0x15da9  ldarg.0
0x15daa  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::lookupValue
0x15daf  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_name()
0x15db4  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x15db9  stloc.s  5
0x15dbb  ldloc.1
0x15dbc  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::get_Inputs()
0x15dc1  ldloc.2
0x15dc2  ldloc.s  5
0x15dc4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>, !!T0)
0x15dc9  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo::.ctor()
0x15dce  stloc.s  6
0x15dd0  ldstr    aCalculatedfail// "CalculatedFailureTimeout"
0x15dd5  ldc.i4.2
0x15dd6  ldc.i4.1
0x15dd7  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x15ddc  stloc.s  7
0x15dde  ldloc.s  6
0x15de0  ldloc.s  7
0x15de2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Name(string)
0x15de7  ldloc.s  7
0x15de9  ldc.i4.1
0x15dea  callvirt instance object [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetVariableValue(string, bool)
0x15def  stloc.s  8
0x15df1  ldarg.0
0x15df2  ldloc.s  8
0x15df4  unbox.any [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x15df9  stfld    valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::_failAfterInputArgument
0x15dfe  ldloc.s  6
0x15e00  ldarg.0
0x15e01  ldfld    valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::_failAfterInputArgument
0x15e06  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::.ctor(var<u1>)
0x15e0b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_IdentifierDefinition(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>)
0x15e10  ldloc.s  6
0x15e12  ldarg.0
0x15e13  ldflda   valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::_failAfterInputArgument
0x15e18  call     instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::GetClrType()
0x15e1d  callvirt instance string [mscorlib]System.Type::get_FullName()
0x15e22  call     class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractiveWorkflowTypeHelper::GetCrmTypeFromDotNetType(string)
0x15e27  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Type(class [mscorlib]System.Type)
0x15e2c  ldloc.s  6
0x15e2e  ldarg.0
0x15e2f  ldflda   valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::_failAfterInputArgument
0x15e34  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::GetWorkflowDataType()
0x15e39  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_WorkflowAttributeType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x15e3e  ldloc.s  6
0x15e40  ldloc.s  7
0x15e42  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_DependencyPropertyName(string)
0x15e47  ldloc.s  6
0x15e49  ldc.i4.1
0x15e4a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Required(bool)
0x15e4f  ldloc.1
0x15e50  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::get_Inputs()
0x15e55  ldloc.s  6
0x15e57  ldarg.s  5
0x15e59  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>, !!T0)
0x15e5e  ret
```
