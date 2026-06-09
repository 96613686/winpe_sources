# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadQueryStep

- ea: `0x21d50`
- end: `0x21e2c`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadQueryStep`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x21d50`
- `0x22ce0`
- `0x2e360`
- `0x2e380`
- `0x2e3c0`
- `0x2e3e0`
- `0x2e400`
- `0x2e420`

## pseudocode

```c

```

## disassembly

```asm
0x21d50  ldc.i4.0
0x21d51  stloc.0
0x21d52  ldarg.0
0x21d53  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x21d58  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x21d5d  stloc.1
0x21d5e  ldarg.0
0x21d5f  ldarg.1
0x21d60  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x21d65  ldc.i4.0
0x21d66  call     T0x2B000033
0x21d6b  stloc.2
0x21d6c  ldloc.2
0x21d6d  brfalse  loc_21E2A
0x21d72  ldloc.2
0x21d73  callvirt instance class [System.Activities]System.Activities.InArgument`1<int32> Microsoft.Crm.Workflow.Activities.QueryData::get_FetchCount()
0x21d78  brfalse.s loc_21D95
0x21d7a  ldloc.1
0x21d7b  ldloc.2
0x21d7c  callvirt instance class [System.Activities]System.Activities.InArgument`1<int32> Microsoft.Crm.Workflow.Activities.QueryData::get_FetchCount()
0x21d81  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<int32>::get_Expression()
0x21d86  castclass class [System.Activities]System.Activities.Expressions.Literal`1<int32>
0x21d8b  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<int32>::get_Value()
0x21d90  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::set_FetchCount(int32)
0x21d95  ldloc.2
0x21d96  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.QueryData::get_FetchXml()
0x21d9b  brfalse.s loc_21DBC
0x21d9d  ldloc.1
0x21d9e  ldarg.0
0x21d9f  ldarg.1
0x21da0  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x21da5  ldtoken  Microsoft.Crm.Workflow.Activities.QueryData
0x21daa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21daf  ldc.i4.0
0x21db0  ldloca.s 0
0x21db2  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x21db7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::set_FetchExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x21dbc  ldloc.2
0x21dbd  callvirt instance string Microsoft.Crm.Workflow.Activities.QueryData::get_OriginalFetchXml()
0x21dc2  brfalse.s loc_21DD0
0x21dc4  ldloc.1
0x21dc5  ldloc.2
0x21dc6  callvirt instance string Microsoft.Crm.Workflow.Activities.QueryData::get_OriginalFetchXml()
0x21dcb  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::set_OriginalFetchXml(string)
0x21dd0  ldloc.2
0x21dd1  callvirt instance string Microsoft.Crm.Workflow.Activities.QueryData::get_OriginalLayoutXml()
0x21dd6  brfalse.s loc_21DE4
0x21dd8  ldloc.1
0x21dd9  ldloc.2
0x21dda  callvirt instance string Microsoft.Crm.Workflow.Activities.QueryData::get_OriginalLayoutXml()
0x21ddf  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::set_OriginalLayoutXml(string)
0x21de4  ldloc.2
0x21de5  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.QueryData::get_EntityName()
0x21dea  brfalse.s loc_21E07
0x21dec  ldloc.1
0x21ded  ldloc.2
0x21dee  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.QueryData::get_EntityName()
0x21df3  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x21df8  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x21dfd  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x21e02  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::set_EntityName(string)
0x21e07  ldloc.2
0x21e08  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.QueryData::get_DynamicQueryAttributeList()
0x21e0d  brfalse.s loc_21E2A
0x21e0f  ldloc.1
0x21e10  ldloc.2
0x21e11  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.QueryData::get_DynamicQueryAttributeList()
0x21e16  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x21e1b  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x21e20  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x21e25  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::set_AttributeList(string)
0x21e2a  ldloc.1
0x21e2b  ret
```
