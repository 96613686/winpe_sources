# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSetFieldRequiredLevelStep

- ea: `0x200f0`
- end: `0x2019f`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSetFieldRequiredLevelStep`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1add0`
- `0x1adf0`
- `0x1ae10`
- `0x1ae30`
- `0x1ae50`
- `0x22a40`

## pseudocode

```c

```

## disassembly

```asm
0x200f0  ldarg.0
0x200f1  ldarg.1
0x200f2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x200f7  ldc.i4.0
0x200f8  call     T0x2B000027
0x200fd  dup
0x200fe  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.FieldRequiredLevelTypes> Microsoft.Crm.Workflow.ClientActivities.SetFieldRequiredLevel::get_RequiredLevel()
0x20103  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.FieldRequiredLevelTypes>::get_Expression()
0x20108  castclass class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.FieldRequiredLevelTypes>
0x2010d  stloc.0
0x2010e  dup
0x2010f  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetFieldRequiredLevel::get_ControlId()
0x20114  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x20119  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x2011e  stloc.1
0x2011f  dup
0x20120  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetFieldRequiredLevel::get_ControlType()
0x20125  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x2012a  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x2012f  stloc.2
0x20130  dup
0x20131  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetFieldRequiredLevel::get_EntityName()
0x20136  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x2013b  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x20140  stloc.3
0x20141  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.ClientActivities.SetFieldRequiredLevel::get_Entity()
0x20146  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Expression()
0x2014b  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>
0x20150  stloc.s  4
0x20152  ldarg.0
0x20153  ldloc.s  4
0x20155  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_ExpressionText()
0x2015a  ldloc.3
0x2015b  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x20160  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntity(string entityInfo, string entityName)
0x20165  stloc.s  5
0x20167  ldarg.0
0x20168  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x2016d  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetFieldRequiredLevelStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x20172  dup
0x20173  ldloc.s  5
0x20175  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetFieldRequiredLevelStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x2017a  dup
0x2017b  ldloc.0
0x2017c  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.FieldRequiredLevelTypes>::get_Value()
0x20181  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetFieldRequiredLevelStep::set_RequiredLevel(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.FieldRequiredLevelTypes)
0x20186  dup
0x20187  ldloc.1
0x20188  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x2018d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetFieldRequiredLevelStep::set_ControlId(string)
0x20192  dup
0x20193  ldloc.2
0x20194  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x20199  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetFieldRequiredLevelStep::set_ControlType(string)
0x2019e  ret
```
