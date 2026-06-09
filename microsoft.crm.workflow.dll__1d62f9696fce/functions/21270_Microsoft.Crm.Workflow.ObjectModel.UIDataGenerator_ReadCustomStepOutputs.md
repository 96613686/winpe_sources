# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCustomStepOutputs

- ea: `0x21270`
- end: `0x214a1`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCustomStepOutputs`
- size: `561`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x20a40`
- `0x20bc0`

## callees

- `0x21270`
- `0x214b0`

## pseudocode

```c

```

## disassembly

```asm
0x21270  ldarg.3
0x21271  ldstr    aInvokesdkmessa_0// "InvokeSdkMessage"
0x21276  ldc.i4.4
0x21277  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2127c  stloc.0
0x2127d  ldarg.1
0x2127e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Outputs()
0x21283  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase>::get_Values()
0x21288  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase>::GetEnumerator()
0x2128d  stloc.1
0x2128e  br       loc_213AE
0x21293  ldloca.s 1
0x21295  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase>::get_Current()
0x2129a  stloc.2
0x2129b  ldarg.1
0x2129c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x212a1  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_IsNet4()
0x212a6  brtrue.s loc_212BA
0x212a8  ldloc.2
0x212a9  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_DependencyPropertyName()
0x212ae  ldstr    aOut// "Out"
0x212b3  call     string [mscorlib]System.String::Concat(string, string)
0x212b8  br.s     loc_212C0
0x212ba  ldloc.2
0x212bb  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_DependencyPropertyName()
0x212c0  stloc.3
0x212c1  ldloc.0
0x212c2  brtrue.s loc_212F5
0x212c4  ldarg.2
0x212c5  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomReference::get_Arguments()
0x212ca  ldloc.3
0x212cb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::ContainsKey(var<u1>)
0x212d0  brfalse.s loc_212F2
0x212d2  ldarg.0
0x212d3  ldarg.2
0x212d4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomReference::get_Arguments()
0x212d9  ldloc.3
0x212da  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x212df  ldloc.2
0x212e0  ldarg.1
0x212e1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x212e6  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_IsNet4()
0x212eb  call     instance bool Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ArgumentSignatureMatches(class [System.Activities]System.Activities.Argument argument, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase output, bool isNet4)
0x212f0  br.s     loc_21307
0x212f2  ldc.i4.0
0x212f3  br.s     loc_21307
0x212f5  ldarg.s  4
0x212f7  brfalse.s loc_21306
0x212f9  ldarg.s  4
0x212fb  ldloc.3
0x212fc  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x21301  ldc.i4.0
0x21302  ceq
0x21304  br.s     loc_21307
0x21306  ldc.i4.0
0x21307  brfalse  loc_213AE
0x2130c  ldarg.0
0x2130d  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x21312  ldarg.1
0x21313  ldloc.2
0x21314  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_DependencyPropertyName()
0x21319  ldloc.2
0x2131a  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_WorkflowAttributeType()
0x2131f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ActivityPropertyExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase, string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x21324  stloc.s  4
0x21326  ldarg.0
0x21327  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x2132c  ldarg.3
0x2132d  ldloc.2
0x2132e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_DependencyPropertyName()
0x21333  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::LocalParameterVariableName
0x21338  call     string [mscorlib]System.String::Concat(string, string, string)
0x2133d  ldloc.s  4
0x2133f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x21344  ldloc.2
0x21345  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x2134a  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup
0x2134f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21354  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x21359  brtrue.s loc_21372
0x2135b  ldloc.2
0x2135c  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x21361  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x21366  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2136b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x21370  brfalse.s loc_213AE
0x21372  ldarg.1
0x21373  ldarg.3
0x21374  ldloc.2
0x21375  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_EntityNames()
0x2137a  ldc.i4.0
0x2137b  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::get_Item(!!T0)
0x21380  ldloc.2
0x21381  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_DependencyPropertyName()
0x21386  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase, string, string, string)
0x2138b  stloc.s  5
0x2138d  ldloc.s  5
0x2138f  ldarg.0
0x21390  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x21395  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::set_Workflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x2139a  ldarg.0
0x2139b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_createdEntities
0x213a0  ldloc.s  5
0x213a2  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_ParameterName()
0x213a7  ldloc.s  5
0x213a9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep>::Add(var<u1>, !!T0)
0x213ae  ldloca.s 1
0x213b0  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase>::MoveNext()
0x213b5  brtrue   loc_21293
0x213ba  leave.s  loc_213CA
0x213bc  ldloca.s 1
0x213be  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase>
0x213c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x213c9  endfinally
0x213ca  ldarg.2
0x213cb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomReference::get_Arguments()
0x213d0  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::GetEnumerator()
0x213d5  stloc.s  6
0x213d7  br       loc_21484
0x213dc  ldloca.s 6
0x213de  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>::get_Current()
0x213e3  stloc.s  7
0x213e5  ldloca.s 7
0x213e7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x213ec  brfalse  loc_21484
0x213f1  ldloca.s 7
0x213f3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x213f8  callvirt instance valuetype [System.Activities]System.Activities.ArgumentDirection [System.Activities]System.Activities.Argument::get_Direction()
0x213fd  ldc.i4.2
0x213fe  beq.s    loc_2140F
0x21400  ldloca.s 7
0x21402  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x21407  callvirt instance valuetype [System.Activities]System.Activities.ArgumentDirection [System.Activities]System.Activities.Argument::get_Direction()
0x2140c  ldc.i4.1
0x2140d  bne.un.s loc_21484
0x2140f  ldarg.1
0x21410  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Outputs()
0x21415  ldloca.s 7
0x21417  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x2141c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase>::ContainsKey(var<u1>)
0x21421  brtrue.s loc_21484
0x21423  ldarg.3
0x21424  ldloca.s 7
0x21426  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x2142b  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::LocalParameterVariableName
0x21430  call     string [mscorlib]System.String::Concat(string, string, string)
0x21435  stloc.s  8
0x21437  ldloc.0
0x21438  brfalse.s loc_21460
0x2143a  ldarg.0
0x2143b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x21440  ldloc.s  8
0x21442  ldarg.0
0x21443  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x21448  ldloc.s  8
0x2144a  ldc.i4.1
0x2144b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep::.ctor(string, bool)
0x21450  ldloc.s  8
0x21452  ldc.i4.s 0xE
0x21454  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ActivityPropertyExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase, string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x21459  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2145e  br.s     loc_21484
0x21460  ldarg.0
0x21461  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x21466  ldloc.s  8
0x21468  ldarg.0
0x21469  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x2146e  ldloc.s  8
0x21470  ldc.i4.1
0x21471  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep::.ctor(string, bool)
0x21476  ldloc.s  8
0x21478  ldc.i4.s 0xE
0x2147a  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ActivityPropertyExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase, string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x2147f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x21484  ldloca.s 6
0x21486  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>::MoveNext()
0x2148b  brtrue   loc_213DC
0x21490  leave.s  loc_214A0
0x21492  ldloca.s 6
0x21494  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>
0x2149a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2149f  endfinally
0x214a0  ret
```
