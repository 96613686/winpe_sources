# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitUpdateStep

- ea: `0x28ec0`
- end: `0x291c7`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitUpdateStep`
- size: `775`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x25a90`
- `0x28ec0`
- `0x2ab00`

## pseudocode

```c

```

## disassembly

```asm
0x28ec0  newobj   instance void [System.Activities]System.Activities.Statements.Sequence::.ctor()
0x28ec5  stloc.0
0x28ec6  ldloc.0
0x28ec7  ldarg.1
0x28ec8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x28ecd  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x28ed2  ldarg.1
0x28ed3  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x28ed8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x28edd  brtrue.s loc_28EFB
0x28edf  ldloc.0
0x28ee0  dup
0x28ee1  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x28ee6  ldstr    asc_3C24E// ": "
0x28eeb  ldarg.1
0x28eec  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x28ef1  call     string [mscorlib]System.String::Concat(string, string, string)
0x28ef6  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x28efb  newobj   instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.UpdateEntity::.ctor()
0x28f00  stloc.1
0x28f01  ldloc.1
0x28f02  ldarg.0
0x28f03  ldarg.1
0x28f04  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x28f09  ldc.i4.1
0x28f0a  call     instance class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::GetEntityAsInOutArgument(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase entity, bool temporaryEntity)
0x28f0f  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.UpdateEntity::set_Entity(class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>)
0x28f14  ldloc.1
0x28f15  ldarg.1
0x28f16  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x28f1b  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x28f20  ldloc.1
0x28f21  ldarg.1
0x28f22  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x28f27  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x28f2c  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::op_Implicit(!!T0)
0x28f31  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.UpdateEntity::set_EntityName(class [System.Activities]System.Activities.InArgument`1<string>)
0x28f36  ldarg.0
0x28f37  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x28f3c  ldloc.0
0x28f3d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x28f42  ldarg.0
0x28f43  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x28f48  stloc.2
0x28f49  ldarg.0
0x28f4a  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x28f4f  stloc.3
0x28f50  ldarg.0
0x28f51  ldloc.0
0x28f52  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x28f57  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x28f5c  ldarg.0
0x28f5d  ldloc.0
0x28f5e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x28f63  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x28f68  ldarg.1
0x28f69  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x28f6e  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep
0x28f73  brtrue.s loc_28F7C
0x28f75  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::InputEntitiesVariableName
0x28f7a  br.s     loc_28F81
0x28f7c  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::LocalEntitiesVariableName
0x28f81  stloc.s  4
0x28f83  ldarg.1
0x28f84  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x28f89  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep
0x28f8e  brfalse.s loc_28FA9
0x28f90  ldarg.1
0x28f91  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x28f96  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep
0x28f9b  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::get_IsCustomOperationArgument()
0x28fa0  brfalse.s loc_28FA9
0x28fa2  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::InputEntitiesVariableName
0x28fa7  stloc.s  4
0x28fa9  newobj   instance void class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x28fae  stloc.s  8
0x28fb0  ldloc.s  8
0x28fb2  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x28fb7  stloc.s  9
0x28fb9  ldloc.s  9
0x28fbb  ldc.i4.5
0x28fbc  newarr   [mscorlib]System.String
0x28fc1  dup
0x28fc2  ldc.i4.0
0x28fc3  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::LocalEntitiesVariableName
0x28fc8  stelem.ref
0x28fc9  dup
0x28fca  ldc.i4.1
0x28fcb  ldstr    asc_3C35A// "(\""
0x28fd0  stelem.ref
0x28fd1  dup
0x28fd2  ldc.i4.2
0x28fd3  ldarg.1
0x28fd4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x28fd9  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_XamlKey()
0x28fde  stelem.ref
0x28fdf  dup
0x28fe0  ldc.i4.3
0x28fe1  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::TemporaryEntitySuffix
0x28fe6  stelem.ref
0x28fe7  dup
0x28fe8  ldc.i4.4
0x28fe9  ldstr    asc_3C360// "\")"
0x28fee  stelem.ref
0x28fef  call     string [mscorlib]System.String::Concat(string[])
0x28ff4  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_ExpressionText(string)
0x28ff9  ldloc.s  9
0x28ffb  newobj   instance void class [System.Activities]System.Activities.OutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor(class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>>)
0x29000  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_To(class [System.Activities]System.Activities.OutArgument`1<var<u1>>)
0x29005  ldloc.s  8
0x29007  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x2900c  dup
0x2900d  ldstr    aNewEntity// "New Entity(\""
0x29012  ldarg.1
0x29013  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x29018  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x2901d  ldstr    asc_3C360// "\")"
0x29022  call     string [mscorlib]System.String::Concat(string, string, string)
0x29027  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_ExpressionText(string)
0x2902c  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::op_Implicit(!!T0)
0x29031  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_Value(class [System.Activities]System.Activities.InArgument`1<var<u1>>)
0x29036  ldloc.s  8
0x29038  stloc.s  5
0x2903a  newobj   instance void class [System.Activities]System.Activities.Statements.Assign`1<valuetype [mscorlib]System.Guid>::.ctor()
0x2903f  stloc.s  0xA
0x29041  ldloc.s  0xA
0x29043  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<valuetype [mscorlib]System.Guid>::.ctor()
0x29048  stloc.s  0xB
0x2904a  ldloc.s  0xB
0x2904c  ldc.i4.5
0x2904d  newarr   [mscorlib]System.String
0x29052  dup
0x29053  ldc.i4.0
0x29054  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::LocalEntitiesVariableName
0x29059  stelem.ref
0x2905a  dup
0x2905b  ldc.i4.1
0x2905c  ldstr    asc_3C35A// "(\""
0x29061  stelem.ref
0x29062  dup
0x29063  ldc.i4.2
0x29064  ldarg.1
0x29065  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x2906a  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_XamlKey()
0x2906f  stelem.ref
0x29070  dup
0x29071  ldc.i4.3
0x29072  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::TemporaryEntitySuffix
0x29077  stelem.ref
0x29078  dup
0x29079  ldc.i4.4
0x2907a  ldstr    aId_3// "\").Id"
0x2907f  stelem.ref
0x29080  call     string [mscorlib]System.String::Concat(string[])
0x29085  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<valuetype [mscorlib]System.Guid>::set_ExpressionText(string)
0x2908a  ldloc.s  0xB
0x2908c  newobj   instance void class [System.Activities]System.Activities.OutArgument`1<valuetype [mscorlib]System.Guid>::.ctor(class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>>)
0x29091  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<valuetype [mscorlib]System.Guid>::set_To(class [System.Activities]System.Activities.OutArgument`1<var<u1>>)
0x29096  ldloc.s  0xA
0x29098  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<valuetype [mscorlib]System.Guid>::.ctor()
0x2909d  dup
0x2909e  ldloc.s  4
0x290a0  ldstr    asc_3C35A// "(\""
0x290a5  ldarg.1
0x290a6  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x290ab  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_XamlKey()
0x290b0  ldstr    aId_3// "\").Id"
0x290b5  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x290ba  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<valuetype [mscorlib]System.Guid>::set_ExpressionText(string)
0x290bf  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid>::op_Implicit(!!T0)
0x290c4  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<valuetype [mscorlib]System.Guid>::set_Value(class [System.Activities]System.Activities.InArgument`1<var<u1>>)
0x290c9  ldloc.s  0xA
0x290cb  stloc.s  6
0x290cd  ldarg.0
0x290ce  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x290d3  ldloc.s  5
0x290d5  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x290da  ldarg.0
0x290db  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x290e0  ldloc.s  6
0x290e2  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x290e7  ldarg.0
0x290e8  ldarg.1
0x290e9  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x290ee  stfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_currentEntitySpecificationEntity
0x290f3  ldarg.1
0x290f4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x290f9  ldarg.0
0x290fa  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::Accept(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.IExpressionVisitor)
0x290ff  ldarg.0
0x29100  ldnull
0x29101  stfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_currentEntitySpecificationEntity
0x29106  newobj   instance void class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x2910b  stloc.s  8
0x2910d  ldloc.s  8
0x2910f  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x29114  dup
0x29115  ldloc.s  4
0x29117  ldstr    asc_3C35A// "(\""
0x2911c  ldarg.1
0x2911d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x29122  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_XamlKey()
0x29127  ldstr    asc_3C360// "\")"
0x2912c  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x29131  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_ExpressionText(string)
0x29136  newobj   instance void class [System.Activities]System.Activities.OutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor(class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>>)
0x2913b  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_To(class [System.Activities]System.Activities.OutArgument`1<var<u1>>)
0x29140  ldloc.s  8
0x29142  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x29147  stloc.s  0xC
0x29149  ldloc.s  0xC
0x2914b  ldc.i4.5
0x2914c  newarr   [mscorlib]System.String
0x29151  dup
0x29152  ldc.i4.0
0x29153  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::LocalEntitiesVariableName
0x29158  stelem.ref
0x29159  dup
0x2915a  ldc.i4.1
0x2915b  ldstr    asc_3C35A// "(\""
0x29160  stelem.ref
0x29161  dup
0x29162  ldc.i4.2
0x29163  ldarg.1
0x29164  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x29169  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_XamlKey()
0x2916e  stelem.ref
0x2916f  dup
0x29170  ldc.i4.3
0x29171  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::TemporaryEntitySuffix
0x29176  stelem.ref
0x29177  dup
0x29178  ldc.i4.4
0x29179  ldstr    asc_3C360// "\")"
0x2917e  stelem.ref
0x2917f  call     string [mscorlib]System.String::Concat(string[])
0x29184  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_ExpressionText(string)
0x29189  ldloc.s  0xC
0x2918b  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::op_Implicit(!!T0)
0x29190  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_Value(class [System.Activities]System.Activities.InArgument`1<var<u1>>)
0x29195  ldloc.s  8
0x29197  stloc.s  7
0x29199  ldarg.0
0x2919a  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2919f  ldloc.1
0x291a0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x291a5  ldarg.0
0x291a6  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x291ab  ldloc.s  7
0x291ad  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x291b2  ldarg.0
0x291b3  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::AddPersistIfNecessary()
0x291b8  ldarg.0
0x291b9  ldloc.2
0x291ba  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x291bf  ldarg.0
0x291c0  ldloc.3
0x291c1  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x291c6  ret
```
