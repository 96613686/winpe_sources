# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSetVisibilityStep

- ea: `0x20030`
- end: `0x200ef`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSetVisibilityStep`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1ad00`
- `0x1ad20`
- `0x1ad40`
- `0x1ad60`
- `0x1ad80`
- `0x20030`
- `0x22a40`

## pseudocode

```c

```

## disassembly

```asm
0x20030  ldarg.0
0x20031  ldarg.1
0x20032  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x20037  ldc.i4.0
0x20038  call     T0x2B000026
0x2003d  stloc.0
0x2003e  ldloc.0
0x2003f  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetVisibility::get_ControlId()
0x20044  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x20049  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x2004e  stloc.1
0x2004f  ldloc.0
0x20050  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetVisibility::get_ControlType()
0x20055  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x2005a  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x2005f  stloc.2
0x20060  ldloc.0
0x20061  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.ClientActivities.SetVisibility::get_IsVisible()
0x20066  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::get_Expression()
0x2006b  castclass class [System.Activities]System.Activities.Expressions.Literal`1<bool>
0x20070  stloc.3
0x20071  ldarg.0
0x20072  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x20077  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetVisibilityStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x2007c  stloc.s  4
0x2007e  ldloc.s  4
0x20080  ldloc.1
0x20081  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x20086  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetVisibilityStep::set_ControlId(string)
0x2008b  ldloc.s  4
0x2008d  ldloc.2
0x2008e  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x20093  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetVisibilityStep::set_ControlType(string)
0x20098  ldloc.s  4
0x2009a  ldloc.3
0x2009b  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<bool>::get_Value()
0x200a0  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetVisibilityStep::set_IsVisible(bool)
0x200a5  ldloc.0
0x200a6  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.ClientActivities.SetVisibility::get_Entity()
0x200ab  brfalse.s loc_200EC
0x200ad  ldloc.0
0x200ae  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetVisibility::get_EntityName()
0x200b3  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x200b8  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x200bd  stloc.s  5
0x200bf  ldloc.0
0x200c0  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.ClientActivities.SetVisibility::get_Entity()
0x200c5  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Expression()
0x200ca  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>
0x200cf  stloc.s  6
0x200d1  ldloc.s  4
0x200d3  ldarg.0
0x200d4  ldloc.s  6
0x200d6  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_ExpressionText()
0x200db  ldloc.s  5
0x200dd  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x200e2  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntity(string entityInfo, string entityName)
0x200e7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetVisibilityStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x200ec  ldloc.s  4
0x200ee  ret
```
