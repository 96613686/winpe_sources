# Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::CreateIncidentStep

- ea: `0x18e90`
- end: `0x1911d`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::CreateIncidentStep`
- size: `653`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18d40`
- `0x18dc0`

## callees

- `0x18e90`
- `0x191c0`
- `0x193a0`
- `0x193c0`
- `0x193d0`

## pseudocode

```c

```

## disassembly

```asm
0x18e90  ldarg.0
0x18e91  ldarg.1
0x18e92  ldarg.s  4
0x18e94  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x18e99  ldarg.1
0x18e9a  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x18e9f  stloc.0
0x18ea0  ldarg.2
0x18ea1  ldloc.0
0x18ea2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x18ea7  ldloc.0
0x18ea8  ldstr    aIncident_0// "incident"
0x18ead  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::.ctor(string)
0x18eb2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification)
0x18eb7  ldarg.1
0x18eb8  ldstr    aContact_0// "contact"
0x18ebd  ldarga.s 3
0x18ebf  call     instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_Name()
0x18ec4  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x18ec9  ldarg.1
0x18eca  ldstr    aAccount_0// "account"
0x18ecf  ldarga.s 3
0x18ed1  call     instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_Name()
0x18ed6  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x18edb  stloc.1
0x18edc  ldstr    aContactid// "contactid"
0x18ee1  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x18ee6  stloc.2
0x18ee7  ldloc.1
0x18ee8  ldstr    aAccountid// "accountid"
0x18eed  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x18ef2  stloc.3
0x18ef3  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor()
0x18ef8  stloc.s  4
0x18efa  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor()
0x18eff  stloc.s  5
0x18f01  ldloc.s  4
0x18f03  ldloc.2
0x18f04  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>)
0x18f09  ldloc.s  4
0x18f0b  ldloc.3
0x18f0c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>)
0x18f11  ldarg.1
0x18f12  ldc.i4.0
0x18f13  ldloc.s  4
0x18f15  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::ToArray()
0x18f1a  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x18f1f  stloc.s  6
0x18f21  ldarg.1
0x18f22  ldc.i4.s 0xE
0x18f24  ldc.i4.1
0x18f25  newarr   [mscorlib]System.Object
0x18f2a  dup
0x18f2b  ldc.i4.0
0x18f2c  ldarg.s  5
0x18f2e  stelem.ref
0x18f2f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x18f34  stloc.s  7
0x18f36  ldarg.1
0x18f37  ldc.i4.s 0x16
0x18f39  ldc.i4.1
0x18f3a  newarr   [mscorlib]System.Object
0x18f3f  dup
0x18f40  ldc.i4.0
0x18f41  ldloc.s  7
0x18f43  stelem.ref
0x18f44  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x18f49  stloc.s  8
0x18f4b  ldarg.1
0x18f4c  ldc.i4.s 0xE
0x18f4e  ldc.i4.1
0x18f4f  newarr   [mscorlib]System.Object
0x18f54  dup
0x18f55  ldc.i4.0
0x18f56  ldarga.s 6
0x18f58  call     instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_Name()
0x18f5d  stelem.ref
0x18f5e  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x18f63  stloc.s  9
0x18f65  ldloc.0
0x18f66  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x18f6b  ldstr    aPrimarycontact// "primarycontactid"
0x18f70  ldloc.s  9
0x18f72  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x18f77  ldloc.s  5
0x18f79  ldloc.s  6
0x18f7b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>)
0x18f80  ldloc.0
0x18f81  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x18f86  ldstr    aCustomerid// "customerid"
0x18f8b  ldloc.s  5
0x18f8d  ldc.i4.0
0x18f8e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Item(!!T0)
0x18f93  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x18f98  ldloc.0
0x18f99  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x18f9e  ldstr    aCaseorigincode// "caseorigincode"
0x18fa3  ldloc.s  8
0x18fa5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x18faa  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap>::.ctor()
0x18faf  stloc.s  0xA
0x18fb1  ldloc.s  0xA
0x18fb3  newobj   instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap::.ctor()
0x18fb8  dup
0x18fb9  ldstr    aTitle// "title"
0x18fbe  callvirt instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap::set_AssignedTo(string value)
0x18fc3  dup
0x18fc4  ldstr    aSubject// "subject"
0x18fc9  callvirt instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap::set_AssignedFrom(string value)
0x18fce  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap>::Add(var<u1>)
0x18fd3  ldarg.0
0x18fd4  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_PrimaryEntityName()
0x18fd9  ldstr    aSocialactivity// "socialactivity"
0x18fde  callvirt instance bool [mscorlib]System.String::Equals(string)
0x18fe3  brfalse  loc_190C8
0x18fe8  ldloc.s  0xA
0x18fea  newobj   instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap::.ctor()
0x18fef  dup
0x18ff0  ldstr    aSocialprofilei// "socialprofileid"
0x18ff5  callvirt instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap::set_AssignedTo(string value)
0x18ffa  dup
0x18ffb  ldstr    aPostfromprofil// "postfromprofileid"
0x19000  callvirt instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap::set_AssignedFrom(string value)
0x19005  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap>::Add(var<u1>)
0x1900a  ldloc.s  0xA
0x1900c  newobj   instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap::.ctor()
0x19011  dup
0x19012  ldstr    aSentimentvalue// "sentimentvalue"
0x19017  callvirt instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap::set_AssignedTo(string value)
0x1901c  dup
0x1901d  ldstr    aSentimentvalue// "sentimentvalue"
0x19022  callvirt instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap::set_AssignedFrom(string value)
0x19027  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap>::Add(var<u1>)
0x1902c  ldloc.s  0xA
0x1902e  newobj   instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap::.ctor()
0x19033  dup
0x19034  ldstr    aMessagetypecod// "messagetypecode"
0x19039  callvirt instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap::set_AssignedTo(string value)
0x1903e  dup
0x1903f  ldstr    aPostmessagetyp// "postmessagetype"
0x19044  callvirt instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap::set_AssignedFrom(string value)
0x19049  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap>::Add(var<u1>)
0x1904e  ldarg.1
0x1904f  ldstr    aPostfromprofil// "postfromprofileid"
0x19054  ldstr    aSocialprofile// "socialprofile"
0x19059  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x1905e  stloc.s  0xB
0x19060  ldloc.s  0xB
0x19062  ldstr    aBlocked// "blocked"
0x19067  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x1906c  stloc.s  0xC
0x1906e  ldarg.1
0x1906f  ldc.i4.0
0x19070  ldc.i4.1
0x19071  newarr   [mscorlib]System.Object
0x19076  dup
0x19077  ldc.i4.0
0x19078  ldloc.s  0xC
0x1907a  stelem.ref
0x1907b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x19080  stloc.s  0xD
0x19082  ldloc.0
0x19083  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x19088  ldstr    aBlockedprofile// "blockedprofile"
0x1908d  ldloc.s  0xD
0x1908f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x19094  ldloc.s  0xB
0x19096  ldstr    aInfluencescore// "influencescore"
0x1909b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x190a0  stloc.s  0xE
0x190a2  ldarg.1
0x190a3  ldc.i4.0
0x190a4  ldc.i4.1
0x190a5  newarr   [mscorlib]System.Object
0x190aa  dup
0x190ab  ldc.i4.0
0x190ac  ldloc.s  0xE
0x190ae  stelem.ref
0x190af  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x190b4  stloc.s  0xF
0x190b6  ldloc.0
0x190b7  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x190bc  ldstr    aInfluencescore// "influencescore"
0x190c1  ldloc.s  0xF
0x190c3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x190c8  ldarg.0
0x190c9  ldarg.1
0x190ca  ldloc.s  0xA
0x190cc  ldarg.0
0x190cd  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_PrimaryEntityName()
0x190d2  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::SetAttributeValueStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap> createEntityStepColl, string primaryEntityName)
0x190d7  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::GetEnumerator()
0x190dc  stloc.s  0x10
0x190de  br.s     loc_19102
0x190e0  ldloca.s 0x10
0x190e2  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Current()
0x190e7  stloc.s  0x11
0x190e9  ldloc.0
0x190ea  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x190ef  ldloca.s 0x11
0x190f1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Key()
0x190f6  ldloca.s 0x11
0x190f8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Value()
0x190fd  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x19102  ldloca.s 0x10
0x19104  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::MoveNext()
0x19109  brtrue.s loc_190E0
0x1910b  leave.s  loc_1911B
0x1910d  ldloca.s 0x10
0x1910f  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>
0x19115  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1911a  endfinally
0x1911b  ldloc.0
0x1911c  ret
```
