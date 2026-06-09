# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadRollupRuleStep

- ea: `0x206f0`
- end: `0x2097c`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadRollupRuleStep`
- size: `652`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1a8b0`
- `0x1a8d0`
- `0x206f0`
- `0x22a40`
- `0x22ce0`

## pseudocode

```c

```

## disassembly

```asm
0x206f0  ldarg.0
0x206f1  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x206f6  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x206fb  stloc.0
0x206fc  ldc.i4.0
0x206fd  stloc.1
0x206fe  ldarg.1
0x206ff  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x20704  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x20709  ldc.i4.3
0x2070a  bge.s    loc_20717
0x2070c  ldstr    aExpectedAtleas// "Expected atleast 3 Sequence activities"
0x20711  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x20716  throw
0x20717  ldarg.1
0x20718  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2071d  ldc.i4.0
0x2071e  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x20723  isinst   [System.Activities]System.Activities.Statements.Sequence
0x20728  stloc.2
0x20729  ldloc.2
0x2072a  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x2072f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::GetEnumerator()
0x20734  stloc.s  4
0x20736  br.s     loc_20776
0x20738  ldloc.s  4
0x2073a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.Variable>::get_Current()
0x2073f  stloc.s  5
0x20741  ldloc.s  5
0x20743  callvirt instance string [System.Activities]System.Activities.Variable::get_Name()
0x20748  ldstr    aHierarchicalre// "HierarchicalRelationshipName"
0x2074d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x20752  brfalse.s loc_20776
0x20754  ldloc.s  5
0x20756  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Variable::get_Default()
0x2075b  isinst   class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x20760  stloc.s  6
0x20762  ldloc.0
0x20763  ldloc.s  6
0x20765  brfalse.s loc_20770
0x20767  ldloc.s  6
0x20769  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x2076e  br.s     loc_20771
0x20770  ldnull
0x20771  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::set_HierarchicalRelationshipName(string)
0x20776  ldloc.s  4
0x20778  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2077d  brtrue.s loc_20738
0x2077f  leave.s  loc_2078D
0x20781  ldloc.s  4
0x20783  brfalse.s loc_2078C
0x20785  ldloc.s  4
0x20787  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2078c  endfinally
0x2078d  ldloc.0
0x2078e  ldarg.0
0x2078f  ldloc.2
0x20790  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x20795  ldtoken  [System.Activities]System.Activities.DynamicActivity
0x2079a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2079f  ldc.i4.0
0x207a0  ldloca.s 1
0x207a2  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x207a7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::set_SourceFilter(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x207ac  ldarg.1
0x207ad  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x207b2  ldc.i4.1
0x207b3  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x207b8  isinst   [System.Activities]System.Activities.Statements.Sequence
0x207bd  stloc.3
0x207be  ldloc.3
0x207bf  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x207c4  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x207c9  ldc.i4.0
0x207ca  ble      loc_20851
0x207cf  ldarg.0
0x207d0  ldloc.3
0x207d1  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x207d6  ldc.i4.0
0x207d7  call     T0x2B00002B
0x207dc  dup
0x207dd  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetAttributeValue::get_EntityName()
0x207e2  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x207e7  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x207ec  stloc.s  7
0x207ee  callvirt instance class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.ClientActivities.SetAttributeValue::get_Entity()
0x207f3  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Expression()
0x207f8  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>
0x207fd  stloc.s  8
0x207ff  ldarg.0
0x20800  ldloc.s  8
0x20802  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_ExpressionText()
0x20807  ldloc.s  7
0x20809  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x2080e  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntity(string entityInfo, string entityName)
0x20813  stloc.s  9
0x20815  ldloc.0
0x20816  ldloc.s  9
0x20818  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked
0x2081d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::set_TargetRelationship(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked)
0x20822  ldloc.3
0x20823  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x20828  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x2082d  ldc.i4.1
0x2082e  ble.s    loc_20851
0x20830  ldc.i4.1
0x20831  stloc.1
0x20832  ldloc.0
0x20833  ldarg.0
0x20834  ldloc.3
0x20835  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2083a  ldtoken  [System.Activities]System.Activities.DynamicActivity
0x2083f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20844  ldc.i4.0
0x20845  ldloca.s 1
0x20847  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x2084c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::set_TargetFilter(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x20851  ldc.i4.0
0x20852  stloc.1
0x20853  ldarg.1
0x20854  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x20859  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x2085e  ldc.i4.4
0x2085f  bne.un   loc_20946
0x20864  ldarg.1
0x20865  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2086a  ldc.i4.2
0x2086b  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x20870  isinst   [System.Activities]System.Activities.Statements.Sequence
0x20875  stloc.s  0xA
0x20877  ldloc.s  0xA
0x20879  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2087e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x20883  ldc.i4.0
0x20884  ble      loc_2090E
0x20889  ldarg.0
0x2088a  ldloc.s  0xA
0x2088c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x20891  ldc.i4.0
0x20892  call     T0x2B00002B
0x20897  dup
0x20898  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetAttributeValue::get_EntityName()
0x2089d  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x208a2  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x208a7  stloc.s  0xB
0x208a9  callvirt instance class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.ClientActivities.SetAttributeValue::get_Entity()
0x208ae  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Expression()
0x208b3  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>
0x208b8  stloc.s  0xC
0x208ba  ldarg.0
0x208bb  ldloc.s  0xC
0x208bd  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_ExpressionText()
0x208c2  ldloc.s  0xB
0x208c4  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x208c9  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntity(string entityInfo, string entityName)
0x208ce  stloc.s  0xD
0x208d0  ldloc.0
0x208d1  ldloc.s  0xD
0x208d3  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked
0x208d8  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::set_TargetRelationshipLinked(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked)
0x208dd  ldloc.s  0xA
0x208df  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x208e4  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x208e9  ldc.i4.1
0x208ea  ble.s    loc_2090E
0x208ec  ldc.i4.1
0x208ed  stloc.1
0x208ee  ldloc.0
0x208ef  ldarg.0
0x208f0  ldloc.s  0xA
0x208f2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x208f7  ldtoken  [System.Activities]System.Activities.DynamicActivity
0x208fc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20901  ldc.i4.0
0x20902  ldloca.s 1
0x20904  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x20909  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::set_TargetLinkedFilter(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x2090e  ldc.i4.0
0x2090f  stloc.1
0x20910  ldloc.0
0x20911  ldarg.0
0x20912  ldarg.1
0x20913  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x20918  ldc.i4.3
0x20919  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x2091e  isinst   [System.Activities]System.Activities.Statements.Sequence
0x20923  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x20928  ldtoken  [System.Activities]System.Activities.DynamicActivity
0x2092d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20932  ldc.i4.0
0x20933  ldloca.s 1
0x20935  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x2093a  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression
0x2093f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::set_Aggregate(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression)
0x20944  br.s     loc_2097A
0x20946  ldloc.0
0x20947  ldarg.0
0x20948  ldarg.1
0x20949  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2094e  ldc.i4.2
0x2094f  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x20954  isinst   [System.Activities]System.Activities.Statements.Sequence
0x20959  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2095e  ldtoken  [System.Activities]System.Activities.DynamicActivity
0x20963  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20968  ldc.i4.0
0x20969  ldloca.s 1
0x2096b  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x20970  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression
0x20975  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::set_Aggregate(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression)
0x2097a  ldloc.0
0x2097b  ret
```
