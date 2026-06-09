# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSetMessageStep

- ea: `0x202c0`
- end: `0x203ca`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSetMessageStep`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1aa80`
- `0x1aaa0`
- `0x1aac0`
- `0x1ab10`
- `0x1ab30`
- `0x1f130`
- `0x1f5b0`
- `0x202c0`
- `0x22a40`

## pseudocode

```c

```

## disassembly

```asm
0x202c0  ldarg.0
0x202c1  ldarg.1
0x202c2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x202c7  ldc.i4.0
0x202c8  call     T0x2B00002A
0x202cd  stloc.0
0x202ce  ldloc.0
0x202cf  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetMessage::get_ControlId()
0x202d4  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x202d9  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x202de  stloc.1
0x202df  ldarg.0
0x202e0  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x202e5  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetMessageStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x202ea  stloc.2
0x202eb  ldloc.2
0x202ec  ldloc.1
0x202ed  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x202f2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetMessageStep::set_ControlId(string)
0x202f7  ldarg.0
0x202f8  ldloc.2
0x202f9  ldloc.0
0x202fa  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::AddLabels(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase stepBase, class Microsoft.Crm.Workflow.ClientActivities.SetMessage activity)
0x202ff  ldloc.0
0x20300  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.ClientActivities.SetMessage::get_Entity()
0x20305  brfalse.s loc_20343
0x20307  ldloc.0
0x20308  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetMessage::get_EntityName()
0x2030d  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x20312  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x20317  stloc.3
0x20318  ldloc.0
0x20319  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.ClientActivities.SetMessage::get_Entity()
0x2031e  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Expression()
0x20323  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>
0x20328  stloc.s  4
0x2032a  ldloc.2
0x2032b  ldarg.0
0x2032c  ldloc.s  4
0x2032e  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_ExpressionText()
0x20333  ldloc.3
0x20334  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x20339  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntity(string entityInfo, string entityName)
0x2033e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetMessageStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x20343  ldloc.0
0x20344  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetMessage::get_Level()
0x20349  brfalse.s loc_20371
0x2034b  ldloc.0
0x2034c  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetMessage::get_Level()
0x20351  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x20356  isinst   class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x2035b  stloc.s  5
0x2035d  ldloc.2
0x2035e  ldloc.s  5
0x20360  brtrue.s loc_20365
0x20362  ldnull
0x20363  br.s     loc_2036C
0x20365  ldloc.s  5
0x20367  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x2036c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetMessageStep::set_Level(string)
0x20371  ldloc.0
0x20372  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ClientActivities.SetMessage::get_Activities()
0x20377  brfalse.s loc_203C8
0x20379  ldloc.0
0x2037a  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ClientActivities.SetMessage::get_Activities()
0x2037f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::GetEnumerator()
0x20384  stloc.s  6
0x20386  br.s     loc_203B1
0x20388  ldloc.s  6
0x2038a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.Activity>::get_Current()
0x2038f  stloc.s  7
0x20391  ldloc.s  7
0x20393  isinst   [System.Activities]System.Activities.Statements.Persist
0x20398  brtrue.s loc_203B1
0x2039a  ldarg.0
0x2039b  ldloc.s  7
0x2039d  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSingleStep(class [System.Activities]System.Activities.Activity activity)
0x203a2  stloc.s  8
0x203a4  ldloc.2
0x203a5  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetMessageStep::get_ActionSteps()
0x203aa  ldloc.s  8
0x203ac  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::Add(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x203b1  ldloc.s  6
0x203b3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x203b8  brtrue.s loc_20388
0x203ba  leave.s  loc_203C8
0x203bc  ldloc.s  6
0x203be  brfalse.s loc_203C7
0x203c0  ldloc.s  6
0x203c2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x203c7  endfinally
0x203c8  ldloc.2
0x203c9  ret
```
