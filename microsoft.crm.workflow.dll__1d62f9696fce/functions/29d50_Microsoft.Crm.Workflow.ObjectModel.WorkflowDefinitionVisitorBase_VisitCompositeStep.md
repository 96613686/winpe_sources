# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitCompositeStep

- ea: `0x29d50`
- end: `0x29e45`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitCompositeStep`
- size: `245`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x27b70`
- `0x27bd0`
- `0x2c160`
- `0x2c1a0`
- `0x2c260`
- `0x2c2c0`

## callees

- `0x25a90`
- `0x29d50`
- `0x29e50`
- `0x2b7f0`
- `0x2d170`
- `0x2d1b0`
- `0x2d1c0`

## pseudocode

```c

```

## disassembly

```asm
0x29d50  ldarg.1
0x29d51  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x29d56  stloc.0
0x29d57  ldarg.2
0x29d58  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x29d5d  brtrue.s loc_29D6C
0x29d5f  ldloc.0
0x29d60  ldstr    asc_3C24E// ": "
0x29d65  ldarg.2
0x29d66  call     string [mscorlib]System.String::Concat(string, string, string)
0x29d6b  stloc.0
0x29d6c  ldarg.3
0x29d6d  ldloc.0
0x29d6e  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x29d73  ldarg.1
0x29d74  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x29d79  brfalse  loc_29E09
0x29d7e  ldarg.1
0x29d7f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x29d84  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection::get_Count()
0x29d89  ldc.i4.0
0x29d8a  ble.s    loc_29E09
0x29d8c  ldarg.3
0x29d8d  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel>::.ctor()
0x29d92  callvirt instance void Microsoft.Crm.Workflow.Activities.Composite::set_StepLabels(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel> value)
0x29d97  ldc.i4.0
0x29d98  stloc.3
0x29d99  br.s     loc_29DFB
0x29d9b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::.ctor()
0x29da0  stloc.s  4
0x29da2  ldloc.s  4
0x29da4  ldarg.1
0x29da5  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x29daa  ldloc.3
0x29dab  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection::get_Item(int32)
0x29db0  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::get_LabelId()
0x29db5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::set_LabelId(string)
0x29dba  ldloc.s  4
0x29dbc  ldarg.1
0x29dbd  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x29dc2  ldloc.3
0x29dc3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection::get_Item(int32)
0x29dc8  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::get_LanguageCode()
0x29dcd  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::set_LanguageCode(int32)
0x29dd2  ldloc.s  4
0x29dd4  ldarg.1
0x29dd5  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x29dda  ldloc.3
0x29ddb  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection::get_Item(int32)
0x29de0  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::get_Description()
0x29de5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::set_Description(string)
0x29dea  ldarg.3
0x29deb  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel> Microsoft.Crm.Workflow.Activities.Composite::get_StepLabels()
0x29df0  ldloc.s  4
0x29df2  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel>::Add(var<u1>)
0x29df7  ldloc.3
0x29df8  ldc.i4.1
0x29df9  add
0x29dfa  stloc.3
0x29dfb  ldloc.3
0x29dfc  ldarg.1
0x29dfd  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x29e02  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection::get_Count()
0x29e07  blt.s    loc_29D9B
0x29e09  ldarg.0
0x29e0a  ldarg.3
0x29e0b  call     instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ReferenceActivity(class [System.Activities]System.Activities.Activity activity)
0x29e10  stloc.1
0x29e11  ldarg.0
0x29e12  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x29e17  stloc.2
0x29e18  ldarg.0
0x29e19  ldarg.3
0x29e1a  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x29e1f  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x29e24  ldarg.0
0x29e25  ldarg.1
0x29e26  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitChildren(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase step)
0x29e2b  ldarg.0
0x29e2c  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::AddPersistIfNecessary()
0x29e31  ldarg.0
0x29e32  ldloc.2
0x29e33  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x29e38  ldarg.0
0x29e39  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x29e3e  ldloc.1
0x29e3f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x29e44  ret
```
