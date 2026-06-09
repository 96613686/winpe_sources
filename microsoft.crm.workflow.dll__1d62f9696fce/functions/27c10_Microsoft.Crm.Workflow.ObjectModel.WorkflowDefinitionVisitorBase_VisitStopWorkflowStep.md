# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitStopWorkflowStep

- ea: `0x27c10`
- end: `0x27e74`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitStopWorkflowStep`
- size: `612`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x27c10`
- `0x27e80`
- `0x27ea0`
- `0x2ba20`

## string_xrefs

- `0x27ca9`: `New Microsoft.Xrm.Sdk.InvalidPluginExecutionException(Microsoft.Xrm.Sdk.OperationStatus.`

## pseudocode

```c

```

## disassembly

```asm
0x27c10  newobj   instance void [System.Activities]System.Activities.Statements.Sequence::.ctor()
0x27c15  stloc.0
0x27c16  ldloc.0
0x27c17  ldarg.1
0x27c18  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x27c1d  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x27c22  ldarg.1
0x27c23  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x27c28  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x27c2d  brtrue.s loc_27C4B
0x27c2f  ldloc.0
0x27c30  dup
0x27c31  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x27c36  ldstr    asc_3C24E// ": "
0x27c3b  ldarg.1
0x27c3c  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x27c41  call     string [mscorlib]System.String::Concat(string, string, string)
0x27c46  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x27c4b  ldarg.0
0x27c4c  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x27c51  stloc.1
0x27c52  ldarg.0
0x27c53  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x27c58  stloc.2
0x27c59  ldarg.0
0x27c5a  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x27c5f  ldloc.0
0x27c60  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x27c65  ldarg.0
0x27c66  ldloc.0
0x27c67  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x27c6c  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x27c71  ldarg.0
0x27c72  ldloc.0
0x27c73  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x27c78  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x27c7d  ldarg.1
0x27c7e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x27c83  stloc.3
0x27c84  ldarg.1
0x27c85  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x27c8a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x27c8f  brtrue.s loc_27CA3
0x27c91  ldloc.3
0x27c92  ldstr    asc_3C24E// ": "
0x27c97  ldarg.1
0x27c98  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x27c9d  call     string [mscorlib]System.String::Concat(string, string, string)
0x27ca2  stloc.3
0x27ca3  newobj   instance void [System.Activities]System.Activities.Statements.TerminateWorkflow::.ctor()
0x27ca8  dup
0x27ca9  ldstr    aNewMicrosoftXr// "New Microsoft.Xrm.Sdk.InvalidPluginExec"...
0x27cae  ldarg.1
0x27caf  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.Activities.WorkflowCompletionStatus [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep::get_Status()
0x27cb4  stloc.s  5
0x27cb6  ldloca.s 5
0x27cb8  constrained. [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.Activities.WorkflowCompletionStatus
0x27cbe  callvirt instance string [mscorlib]System.Object::ToString()
0x27cc3  ldstr    asc_3C264// ")"
0x27cc8  call     string [mscorlib]System.String::Concat(string, string, string)
0x27ccd  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [mscorlib]System.Exception>::.ctor(string)
0x27cd2  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Exception>::op_Implicit(!!T0)
0x27cd7  callvirt instance void [System.Activities]System.Activities.Statements.TerminateWorkflow::set_Exception(class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Exception>)
0x27cdc  dup
0x27cdd  ldloc.3
0x27cde  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x27ce3  stloc.s  4
0x27ce5  ldarg.1
0x27ce6  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep::get_StatusMessage()
0x27ceb  brfalse  loc_27E58
0x27cf0  ldarg.1
0x27cf1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep::get_StatusMessage()
0x27cf6  ldarg.0
0x27cf7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::Accept(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.IExpressionVisitor)
0x27cfc  ldloc.s  4
0x27cfe  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<string>::.ctor()
0x27d03  stloc.s  6
0x27d05  ldloc.s  6
0x27d07  ldc.i4.5
0x27d08  newarr   [mscorlib]System.String
0x27d0d  dup
0x27d0e  ldc.i4.0
0x27d0f  ldstr    aDirectcast// "DirectCast("
0x27d14  stelem.ref
0x27d15  dup
0x27d16  ldc.i4.1
0x27d17  ldarg.0
0x27d18  ldarg.1
0x27d19  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep::get_StatusMessage()
0x27d1e  call     instance string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::GetVariable(object key)
0x27d23  stelem.ref
0x27d24  dup
0x27d25  ldc.i4.2
0x27d26  ldstr    asc_39DD8// ", "
0x27d2b  stelem.ref
0x27d2c  dup
0x27d2d  ldc.i4.3
0x27d2e  ldtoken  [mscorlib]System.String
0x27d33  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27d38  callvirt instance string [mscorlib]System.Type::get_FullName()
0x27d3d  stelem.ref
0x27d3e  dup
0x27d3f  ldc.i4.4
0x27d40  ldstr    asc_3C264// ")"
0x27d45  stelem.ref
0x27d46  call     string [mscorlib]System.String::Concat(string[])
0x27d4b  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<string>::set_ExpressionText(string)
0x27d50  ldloc.s  6
0x27d52  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::op_Implicit(!!T0)
0x27d57  callvirt instance void [System.Activities]System.Activities.Statements.TerminateWorkflow::set_Reason(class [System.Activities]System.Activities.InArgument`1<string>)
0x27d5c  ldarg.1
0x27d5d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep::get_StatusMessage()
0x27d62  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression
0x27d67  brfalse  loc_27E58
0x27d6c  ldc.i4.0
0x27d6d  stloc.s  7
0x27d6f  ldarg.0
0x27d70  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_definition
0x27d75  ldstr    aLanguagecode// "languagecode"
0x27d7a  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x27d7f  brfalse.s loc_27DAC
0x27d81  ldarg.0
0x27d82  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_definition
0x27d87  ldstr    aLanguagecode// "languagecode"
0x27d8c  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x27d91  brfalse.s loc_27DAC
0x27d93  ldarg.0
0x27d94  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_definition
0x27d99  ldstr    aLanguagecode// "languagecode"
0x27d9e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x27da3  unbox.any [mscorlib]System.Int32
0x27da8  stloc.s  7
0x27daa  br.s     loc_27DE6
0x27dac  ldarg.0
0x27dad  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_context
0x27db2  brtrue.s loc_27DC4
0x27db4  ldstr    aIorganizationc// "IOrganizationContext is null"
0x27db9  ldc.i4   0x80040216
0x27dbe  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x27dc3  throw
0x27dc4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x27dc9  ldarg.0
0x27dca  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_context
0x27dcf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x27dd4  ldarg.0
0x27dd5  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_context
0x27dda  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x27ddf  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x27de4  stloc.s  7
0x27de6  ldarg.1
0x27de7  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep::get_StatusMessage()
0x27dec  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression
0x27df1  callvirt instance object [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::get_Value()
0x27df6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27dfb  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x27e00  stloc.s  8
0x27e02  ldarg.0
0x27e03  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x27e08  stloc.s  0xA
0x27e0a  ldloca.s 0xA
0x27e0c  constrained. [mscorlib]System.Guid
0x27e12  callvirt instance string [mscorlib]System.Object::ToString()
0x27e17  ldloc.s  8
0x27e19  ldloc.s  7
0x27e1b  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::CreateStepLabel(string labelId, string description, int32 languageCode)
0x27e20  stloc.s  9
0x27e22  ldarg.1
0x27e23  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x27e28  brfalse.s loc_27E50
0x27e2a  ldarg.1
0x27e2b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x27e30  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection::get_Count()
0x27e35  ldc.i4.0
0x27e36  ble.s    loc_27E50
0x27e38  ldloc.s  9
0x27e3a  ldarg.1
0x27e3b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x27e40  ldc.i4.0
0x27e41  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection::get_Item(int32)
0x27e46  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::get_LabelId()
0x27e4b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::set_LabelId(string)
0x27e50  ldarg.0
0x27e51  ldloc.s  9
0x27e53  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::SetStepLabelVariables(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel stepLabel)
0x27e58  ldarg.0
0x27e59  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x27e5e  ldloc.s  4
0x27e60  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x27e65  ldarg.0
0x27e66  ldloc.1
0x27e67  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x27e6c  ldarg.0
0x27e6d  ldloc.2
0x27e6e  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x27e73  ret
```
