# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadRelationshipStep

- ea: `0x1f310`
- end: `0x1f39c`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadRelationshipStep`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x2cf20`
- `0x2cf40`
- `0x2cf60`
- `0x2cf80`

## pseudocode

```c

```

## disassembly

```asm
0x1f310  ldarg.0
0x1f311  ldarg.1
0x1f312  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x1f317  ldc.i4.0
0x1f318  call     T0x2B00001F
0x1f31d  dup
0x1f31e  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.StageRelationship::get_RelationshipName()
0x1f323  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x1f328  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x1f32d  stloc.0
0x1f32e  dup
0x1f32f  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.StageRelationship::get_AttributeName()
0x1f334  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x1f339  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x1f33e  stloc.1
0x1f33f  dup
0x1f340  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.StageRelationship::get_SourceStageId()
0x1f345  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x1f34a  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x1f34f  stloc.2
0x1f350  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.StageRelationship::get_TargetStageId()
0x1f355  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x1f35a  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x1f35f  stloc.3
0x1f360  ldarg.0
0x1f361  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1f366  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RelationshipStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x1f36b  dup
0x1f36c  ldloc.0
0x1f36d  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x1f372  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RelationshipStep::set_RelationshipName(string)
0x1f377  dup
0x1f378  ldloc.1
0x1f379  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x1f37e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RelationshipStep::set_AttributeName(string)
0x1f383  dup
0x1f384  ldloc.2
0x1f385  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x1f38a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RelationshipStep::set_SourceStageId(string)
0x1f38f  dup
0x1f390  ldloc.3
0x1f391  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x1f396  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RelationshipStep::set_TargetStageId(string)
0x1f39b  ret
```
