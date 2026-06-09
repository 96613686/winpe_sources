# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::CreateControlSequence

- ea: `0x2c330`
- end: `0x2c407`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::CreateControlSequence`
- size: `215`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x2c2a0`
- `0x2c2c0`

## callees

- `0x2c330`
- `0x2ce00`
- `0x2ce20`
- `0x2ce40`
- `0x2ce60`
- `0x2ce80`
- `0x2cea0`
- `0x2cec0`
- `0x2cee0`
- `0x2cf00`

## pseudocode

```c

```

## disassembly

```asm
0x2c330  newobj   instance void [System.Activities]System.Activities.Statements.Sequence::.ctor()
0x2c335  stloc.0
0x2c336  ldloc.0
0x2c337  ldarg.1
0x2c338  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x2c33d  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2c342  ldarg.1
0x2c343  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x2c348  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2c34d  brtrue.s loc_2C36B
0x2c34f  ldloc.0
0x2c350  dup
0x2c351  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x2c356  ldstr    asc_3C24E// ": "
0x2c35b  ldarg.1
0x2c35c  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x2c361  call     string [mscorlib]System.String::Concat(string, string, string)
0x2c366  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2c36b  newobj   instance void Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::.ctor()
0x2c370  stloc.1
0x2c371  ldloc.1
0x2c372  ldarg.1
0x2c373  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_ControlId()
0x2c378  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::op_Implicit(!!T0)
0x2c37d  callvirt instance void Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::set_ControlId(class [System.Activities]System.Activities.InArgument`1<string> value)
0x2c382  ldloc.1
0x2c383  ldarg.1
0x2c384  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_ClassId()
0x2c389  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::op_Implicit(!!T0)
0x2c38e  callvirt instance void Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::set_ClassId(class [System.Activities]System.Activities.InArgument`1<string> value)
0x2c393  ldloc.1
0x2c394  ldarg.1
0x2c395  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_DataFieldName()
0x2c39a  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::op_Implicit(!!T0)
0x2c39f  callvirt instance void Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::set_DataFieldName(class [System.Activities]System.Activities.InArgument`1<string> value)
0x2c3a4  ldloc.1
0x2c3a5  ldarg.1
0x2c3a6  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SystemStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_SystemStepType()
0x2c3ab  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<int32>::op_Implicit(!!T0)
0x2c3b0  callvirt instance void Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::set_SystemStepType(class [System.Activities]System.Activities.InArgument`1<int32> value)
0x2c3b5  ldloc.1
0x2c3b6  ldarg.1
0x2c3b7  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_IsSystemControl()
0x2c3bc  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::op_Implicit(!!T0)
0x2c3c1  callvirt instance void Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::set_IsSystemControl(class [System.Activities]System.Activities.InArgument`1<bool> value)
0x2c3c6  ldloc.1
0x2c3c7  ldarg.1
0x2c3c8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_Parameters()
0x2c3cd  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::op_Implicit(!!T0)
0x2c3d2  callvirt instance void Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::set_Parameters(class [System.Activities]System.Activities.InArgument`1<string> value)
0x2c3d7  ldloc.1
0x2c3d8  ldarg.1
0x2c3d9  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_ControlDisplayName()
0x2c3de  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::op_Implicit(!!T0)
0x2c3e3  callvirt instance void Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::set_ControlDisplayName(class [System.Activities]System.Activities.InArgument`1<string> value)
0x2c3e8  ldloc.1
0x2c3e9  ldarg.1
0x2c3ea  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_IsUnbound()
0x2c3ef  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::op_Implicit(!!T0)
0x2c3f4  callvirt instance void Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::set_IsUnbound(class [System.Activities]System.Activities.InArgument`1<bool> value)
0x2c3f9  ldloc.0
0x2c3fa  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2c3ff  ldloc.1
0x2c400  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2c405  ldloc.0
0x2c406  ret
```
