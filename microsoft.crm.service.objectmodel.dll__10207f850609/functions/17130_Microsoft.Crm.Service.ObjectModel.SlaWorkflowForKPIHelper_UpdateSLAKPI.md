# Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::UpdateSLAKPI

- ea: `0x17130`
- end: `0x1722a`
- name: `Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::UpdateSLAKPI`
- size: `250`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x178e0`
- `0x17ab0`

## callees

- `0x17130`

## string_xrefs

- `0x1719c`: `computedwarningtime`
- `0x171c3`: `computedwarningtime`
- `0x171ad`: `computedfailuretime`
- `0x1720b`: `computedfailuretime`

## pseudocode

```c

```

## disassembly

```asm
0x17130  ldarg.2
0x17131  ldarg.s  4
0x17133  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Description(string)
0x17138  ldarg.2
0x17139  ldarg.1
0x1713a  ldarg.3
0x1713b  ldstr    aSlakpiinstance_0// "slakpiinstance"
0x17140  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x17145  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x1714a  ldarg.2
0x1714b  ldstr    aSlakpiinstance_0// "slakpiinstance"
0x17150  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::.ctor(string)
0x17155  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::set_EntitySpec(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification)
0x1715a  ldarg.s  7
0x1715c  ldc.i4.m1
0x1715d  beq.s    loc_17180
0x1715f  ldarg.1
0x17160  ldarg.s  7
0x17162  box      [mscorlib]System.Int32
0x17167  ldc.i4.s 0xA
0x17169  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x1716e  stloc.0
0x1716f  ldarg.2
0x17170  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x17175  ldstr    aStatus// "status"
0x1717a  ldloc.0
0x1717b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x17180  ldarg.s  5
0x17182  brtrue.s loc_171B9
0x17184  ldarg.1
0x17185  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_MaxValue()
0x1718a  box      [mscorlib]System.DateTime
0x1718f  ldc.i4.2
0x17190  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x17195  stloc.1
0x17196  ldarg.2
0x17197  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x1719c  ldstr    aComputedwarnin// "computedwarningtime"
0x171a1  ldloc.1
0x171a2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x171a7  ldarg.2
0x171a8  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x171ad  ldstr    aComputedfailur// "computedfailuretime"
0x171b2  ldloc.1
0x171b3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x171b8  ret
0x171b9  ldarg.s  8
0x171bb  brfalse.s loc_17205
0x171bd  ldarg.2
0x171be  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x171c3  ldstr    aComputedwarnin// "computedwarningtime"
0x171c8  ldarg.s  5
0x171ca  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x171cf  ldarg.2
0x171d0  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x171d5  ldstr    aWarningtime// "warningtime"
0x171da  ldarg.s  5
0x171dc  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x171e1  ldarg.s  9
0x171e3  brfalse.s loc_17205
0x171e5  ldarg.1
0x171e6  ldc.i4.0
0x171e7  box      [mscorlib]System.Int32
0x171ec  ldc.i4.s 0xA
0x171ee  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x171f3  stloc.2
0x171f4  ldarg.2
0x171f5  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x171fa  ldstr    aWarningtimerea// "warningtimereached"
0x171ff  ldloc.2
0x17200  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x17205  ldarg.2
0x17206  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x1720b  ldstr    aComputedfailur// "computedfailuretime"
0x17210  ldarg.s  6
0x17212  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x17217  ldarg.2
0x17218  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x1721d  ldstr    aFailuretime// "failuretime"
0x17222  ldarg.s  6
0x17224  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x17229  ret
```
