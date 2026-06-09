# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSendEmailFromTemplateStep

- ea: `0x1fd50`
- end: `0x1fe25`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSendEmailFromTemplateStep`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1fd50`
- `0x22a40`
- `0x22c00`
- `0x25150`

## pseudocode

```c

```

## disassembly

```asm
0x1fd50  ldarg.0
0x1fd51  ldfld    class Microsoft.Crm.Workflow.ObjectModel.IUIDataHelper Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_uiDataHelper
0x1fd56  ldc.i4.1
0x1fd57  callvirt instance string Microsoft.Crm.Workflow.ObjectModel.IUIDataHelper::GetObjectName(valuetype Microsoft.Crm.Workflow.ObjectModel.ObjectName objectName)
0x1fd5c  stloc.0
0x1fd5d  ldarg.0
0x1fd5e  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1fd63  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x1fd68  stloc.1
0x1fd69  ldloc.1
0x1fd6a  ldloc.0
0x1fd6b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep, string)
0x1fd70  stloc.2
0x1fd71  ldarg.0
0x1fd72  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_createdEntities
0x1fd77  ldarg.1
0x1fd78  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::LocalParameterVariableName
0x1fd7d  call     string [mscorlib]System.String::Concat(string, string)
0x1fd82  ldloc.2
0x1fd83  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep>::Add(var<u1>, !!T0)
0x1fd88  ldnull
0x1fd89  stloc.3
0x1fd8a  ldarg.0
0x1fd8b  ldarg.2
0x1fd8c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x1fd91  ldc.i4.0
0x1fd92  call     T0x2B000022
0x1fd97  stloc.s  4
0x1fd99  ldloc.s  4
0x1fd9b  brfalse.s loc_1FE1C
0x1fd9d  ldloc.s  4
0x1fd9f  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SendEmailFromTemplate::get_TemplateId()
0x1fda4  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid>::get_Expression()
0x1fda9  castclass class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [mscorlib]System.Guid>
0x1fdae  stloc.s  5
0x1fdb0  ldloc.s  4
0x1fdb2  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SendEmailFromTemplate::get_RegardingType()
0x1fdb7  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x1fdbc  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x1fdc1  stloc.s  6
0x1fdc3  ldloc.s  4
0x1fdc5  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SendEmailFromTemplate::get_RegardingId()
0x1fdca  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid>::get_Expression()
0x1fdcf  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<valuetype [mscorlib]System.Guid>
0x1fdd4  stloc.s  7
0x1fdd6  ldarg.0
0x1fdd7  ldarg.2
0x1fdd8  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x1fddd  ldtoken  [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SendEmailFromTemplate
0x1fde2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1fde7  ldloc.0
0x1fde8  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntitySpecification(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, string entityName)
0x1fded  stloc.3
0x1fdee  ldloc.1
0x1fdef  ldloc.s  5
0x1fdf1  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [mscorlib]System.Guid>::get_Value()
0x1fdf6  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_EmailTemplateId(valuetype [mscorlib]System.Guid)
0x1fdfb  ldloc.1
0x1fdfc  ldc.i4.1
0x1fdfd  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_SendEmailStepType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailType)
0x1fe02  ldloc.1
0x1fe03  ldarg.0
0x1fe04  ldloc.s  7
0x1fe06  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<valuetype [mscorlib]System.Guid>::get_ExpressionText()
0x1fe0b  ldloc.s  6
0x1fe0d  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x1fe12  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntity(string entityInfo, string entityName)
0x1fe17  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_RegardingEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x1fe1c  ldloc.1
0x1fe1d  ldloc.3
0x1fe1e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification)
0x1fe23  ldloc.1
0x1fe24  ret
```
