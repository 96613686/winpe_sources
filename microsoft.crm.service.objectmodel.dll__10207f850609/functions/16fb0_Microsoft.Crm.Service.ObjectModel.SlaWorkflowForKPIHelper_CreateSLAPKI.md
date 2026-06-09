# Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::CreateSLAPKI

- ea: `0x16fb0`
- end: `0x170d5`
- name: `Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::CreateSLAPKI`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x17860`
- `0x17a80`

## callees

- `0x16fb0`
- `0x17230`
- `0x172d0`

## string_xrefs

- `0x17052`: `computedwarningtime`
- `0x17096`: `computedwarningtime`
- `0x17063`: `computedfailuretime`
- `0x170a7`: `computedfailuretime`

## pseudocode

```c

```

## disassembly

```asm
0x16fb0  ldarg.1
0x16fb1  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x16fb6  stloc.0
0x16fb7  ldloc.0
0x16fb8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16fbd  ldstr    aWebSlaWorkflow_8// "Web.SLA.Workflow.KpiInstanceDescription"
0x16fc2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16fc7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Description(string)
0x16fcc  ldarg.2
0x16fcd  ldloc.0
0x16fce  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x16fd3  ldloc.0
0x16fd4  ldstr    aSlakpiinstance_0// "slakpiinstance"
0x16fd9  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::.ctor(string)
0x16fde  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification)
0x16fe3  ldloc.0
0x16fe4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x16fe9  ldstr    aName// "name"
0x16fee  ldarg.0
0x16fef  ldarg.1
0x16ff0  ldarg.s  6
0x16ff2  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::GetKpiName(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string relatedKpi)
0x16ff7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x16ffc  ldloc.0
0x16ffd  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x17002  ldstr    aRegarding// "regarding"
0x17007  ldarg.0
0x17008  ldarg.1
0x17009  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::GetApplicableEntityId(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x1700e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x17013  ldloc.0
0x17014  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x17019  ldstr    aWarningtime// "warningtime"
0x1701e  ldarg.3
0x1701f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x17024  ldloc.0
0x17025  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x1702a  ldstr    aFailuretime// "failuretime"
0x1702f  ldarg.s  4
0x17031  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x17036  ldarg.s  5
0x17038  brfalse.s loc_17090
0x1703a  ldarg.1
0x1703b  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_MaxValue()
0x17040  box      [mscorlib]System.DateTime
0x17045  ldc.i4.2
0x17046  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x1704b  stloc.1
0x1704c  ldloc.0
0x1704d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x17052  ldstr    aComputedwarnin// "computedwarningtime"
0x17057  ldloc.1
0x17058  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x1705d  ldloc.0
0x1705e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x17063  ldstr    aComputedfailur// "computedfailuretime"
0x17068  ldloc.1
0x17069  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x1706e  ldarg.1
0x1706f  ldc.i4.3
0x17070  box      [mscorlib]System.Int32
0x17075  ldc.i4.s 0xA
0x17077  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x1707c  stloc.2
0x1707d  ldloc.0
0x1707e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x17083  ldstr    aStatus// "status"
0x17088  ldloc.2
0x17089  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x1708e  br.s     loc_170D3
0x17090  ldloc.0
0x17091  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x17096  ldstr    aComputedwarnin// "computedwarningtime"
0x1709b  ldarg.3
0x1709c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x170a1  ldloc.0
0x170a2  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x170a7  ldstr    aComputedfailur// "computedfailuretime"
0x170ac  ldarg.s  4
0x170ae  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x170b3  ldarg.1
0x170b4  ldc.i4.0
0x170b5  box      [mscorlib]System.Int32
0x170ba  ldc.i4.s 0xA
0x170bc  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x170c1  stloc.3
0x170c2  ldloc.0
0x170c3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x170c8  ldstr    aStatus// "status"
0x170cd  ldloc.3
0x170ce  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x170d3  ldloc.0
0x170d4  ret
```
