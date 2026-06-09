# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitCreateStep

- ea: `0x26080`
- end: `0x262e5`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitCreateStep`
- size: `613`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x25a90`
- `0x26080`
- `0x2ab00`

## pseudocode

```c

```

## disassembly

```asm
0x26080  newobj   instance void [System.Activities]System.Activities.Statements.Sequence::.ctor()
0x26085  stloc.0
0x26086  ldloc.0
0x26087  ldarg.1
0x26088  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x2608d  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x26092  ldarg.1
0x26093  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x26098  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2609d  brtrue.s loc_260BB
0x2609f  ldloc.0
0x260a0  dup
0x260a1  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x260a6  ldstr    asc_3C24E// ": "
0x260ab  ldarg.1
0x260ac  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x260b1  call     string [mscorlib]System.String::Concat(string, string, string)
0x260b6  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x260bb  newobj   instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.CreateEntity::.ctor()
0x260c0  stloc.1
0x260c1  ldloc.1
0x260c2  ldloc.0
0x260c3  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x260c8  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x260cd  ldarg.0
0x260ce  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x260d3  stloc.2
0x260d4  ldarg.0
0x260d5  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x260da  stloc.3
0x260db  newobj   instance void class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x260e0  stloc.s  4
0x260e2  ldarg.1
0x260e3  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_EntityName()
0x260e8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x260ed  brtrue   loc_2627C
0x260f2  ldarg.0
0x260f3  ldarg.1
0x260f4  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep)
0x260f9  stfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_currentEntitySpecificationEntity
0x260fe  newobj   instance void class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x26103  stloc.s  6
0x26105  ldloc.s  6
0x26107  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x2610c  stloc.s  7
0x2610e  ldloc.s  7
0x26110  ldc.i4.5
0x26111  newarr   [mscorlib]System.String
0x26116  dup
0x26117  ldc.i4.0
0x26118  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::LocalEntitiesVariableName
0x2611d  stelem.ref
0x2611e  dup
0x2611f  ldc.i4.1
0x26120  ldstr    asc_3C35A// "(\""
0x26125  stelem.ref
0x26126  dup
0x26127  ldc.i4.2
0x26128  ldarg.0
0x26129  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_currentEntitySpecificationEntity
0x2612e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_XamlKey()
0x26133  stelem.ref
0x26134  dup
0x26135  ldc.i4.3
0x26136  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::TemporaryEntitySuffix
0x2613b  stelem.ref
0x2613c  dup
0x2613d  ldc.i4.4
0x2613e  ldstr    asc_3C360// "\")"
0x26143  stelem.ref
0x26144  call     string [mscorlib]System.String::Concat(string[])
0x26149  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_ExpressionText(string)
0x2614e  ldloc.s  7
0x26150  newobj   instance void class [System.Activities]System.Activities.OutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor(class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>>)
0x26155  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_To(class [System.Activities]System.Activities.OutArgument`1<var<u1>>)
0x2615a  ldloc.s  6
0x2615c  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x26161  dup
0x26162  ldstr    aNewEntity// "New Entity(\""
0x26167  ldarg.0
0x26168  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_currentEntitySpecificationEntity
0x2616d  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x26172  ldstr    asc_3C360// "\")"
0x26177  call     string [mscorlib]System.String::Concat(string, string, string)
0x2617c  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_ExpressionText(string)
0x26181  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::op_Implicit(!!T0)
0x26186  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_Value(class [System.Activities]System.Activities.InArgument`1<var<u1>>)
0x2618b  ldloc.s  6
0x2618d  stloc.s  5
0x2618f  ldloc.0
0x26190  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x26195  ldloc.s  5
0x26197  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2619c  ldarg.0
0x2619d  ldloc.0
0x2619e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x261a3  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x261a8  ldarg.0
0x261a9  ldloc.0
0x261aa  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x261af  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x261b4  ldloc.1
0x261b5  ldarg.0
0x261b6  ldarg.0
0x261b7  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_currentEntitySpecificationEntity
0x261bc  ldc.i4.1
0x261bd  call     instance class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::GetEntityAsInOutArgument(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase entity, bool temporaryEntity)
0x261c2  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.CreateEntity::set_Entity(class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>)
0x261c7  ldloc.1
0x261c8  ldarg.1
0x261c9  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_EntityName()
0x261ce  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::op_Implicit(!!T0)
0x261d3  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.CreateEntity::set_EntityName(class [System.Activities]System.Activities.InArgument`1<string>)
0x261d8  ldarg.1
0x261d9  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x261de  ldarg.0
0x261df  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::Accept(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.IExpressionVisitor)
0x261e4  newobj   instance void class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x261e9  stloc.s  6
0x261eb  ldloc.s  6
0x261ed  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x261f2  dup
0x261f3  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::LocalEntitiesVariableName
0x261f8  ldstr    asc_3C35A// "(\""
0x261fd  ldarg.0
0x261fe  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_currentEntitySpecificationEntity
0x26203  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_XamlKey()
0x26208  ldstr    asc_3C360// "\")"
0x2620d  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x26212  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_ExpressionText(string)
0x26217  newobj   instance void class [System.Activities]System.Activities.OutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor(class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>>)
0x2621c  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_To(class [System.Activities]System.Activities.OutArgument`1<var<u1>>)
0x26221  ldloc.s  6
0x26223  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x26228  stloc.s  8
0x2622a  ldloc.s  8
0x2622c  ldc.i4.5
0x2622d  newarr   [mscorlib]System.String
0x26232  dup
0x26233  ldc.i4.0
0x26234  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::LocalEntitiesVariableName
0x26239  stelem.ref
0x2623a  dup
0x2623b  ldc.i4.1
0x2623c  ldstr    asc_3C35A// "(\""
0x26241  stelem.ref
0x26242  dup
0x26243  ldc.i4.2
0x26244  ldarg.0
0x26245  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_currentEntitySpecificationEntity
0x2624a  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_XamlKey()
0x2624f  stelem.ref
0x26250  dup
0x26251  ldc.i4.3
0x26252  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::TemporaryEntitySuffix
0x26257  stelem.ref
0x26258  dup
0x26259  ldc.i4.4
0x2625a  ldstr    asc_3C360// "\")"
0x2625f  stelem.ref
0x26260  call     string [mscorlib]System.String::Concat(string[])
0x26265  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_ExpressionText(string)
0x2626a  ldloc.s  8
0x2626c  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::op_Implicit(!!T0)
0x26271  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_Value(class [System.Activities]System.Activities.InArgument`1<var<u1>>)
0x26276  ldloc.s  6
0x26278  stloc.s  4
0x2627a  br.s     loc_262A4
0x2627c  ldarg.0
0x2627d  ldloc.0
0x2627e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x26283  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x26288  ldarg.0
0x26289  ldloc.0
0x2628a  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x2628f  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x26294  ldloc.1
0x26295  ldsfld   string [mscorlib]System.String::Empty
0x2629a  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::op_Implicit(!!T0)
0x2629f  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.CreateEntity::set_EntityName(class [System.Activities]System.Activities.InArgument`1<string>)
0x262a4  ldarg.0
0x262a5  ldnull
0x262a6  stfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_currentEntitySpecificationEntity
0x262ab  ldarg.0
0x262ac  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x262b1  ldloc.1
0x262b2  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x262b7  ldarg.0
0x262b8  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x262bd  ldloc.s  4
0x262bf  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x262c4  ldarg.0
0x262c5  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::AddPersistIfNecessary()
0x262ca  ldarg.0
0x262cb  ldloc.2
0x262cc  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x262d1  ldarg.0
0x262d2  ldloc.3
0x262d3  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x262d8  ldarg.0
0x262d9  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x262de  ldloc.0
0x262df  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x262e4  ret
```
