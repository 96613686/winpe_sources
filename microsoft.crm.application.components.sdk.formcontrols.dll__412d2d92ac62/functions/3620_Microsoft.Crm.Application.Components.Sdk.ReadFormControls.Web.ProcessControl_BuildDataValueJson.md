# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::BuildDataValueJson

- ea: `0x3620`
- end: `0x36da`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::BuildDataValueJson`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x35d0`
- `0x3620`
- `0x36e0`
- `0x3730`
- `0x3780`
- `0x38c0`
- `0x4080`
- `0x4b60`
- `0x4cb0`
- `0x5390`

## pseudocode

```c

```

## disassembly

```asm
0x3620  ldarg.1
0x3621  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetId(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0x3626  stloc.0
0x3627  ldarg.0
0x3628  ldloc.0
0x3629  ldarg.1
0x362a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x362f  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x3634  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::InitializeProcess(valuetype [mscorlib]System.Guid entityId, int32 entityTypeCode)
0x3639  ldc.i4.0
0x363a  stloc.1
0x363b  ldarg.0
0x363c  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::get_IsTurboForm()
0x3641  brtrue.s loc_364D
0x3643  ldarg.0
0x3644  ldloca.s 1
0x3646  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetWarningMessage([out] valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.AppProcessControlWarning& warning)
0x364b  br.s     loc_364E
0x364d  ldnull
0x364e  stloc.2
0x364f  ldarg.0
0x3650  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::get_IsTurboForm()
0x3655  brtrue.s loc_365F
0x3657  ldarg.0
0x3658  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GenerateClientStrings()
0x365d  br.s     loc_3664
0x365f  ldstr    aNull// "null"
0x3664  stloc.3
0x3665  ldarg.0
0x3666  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x366b  brtrue.s loc_3681
0x366d  ldloc.2
0x366e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3673  brtrue.s loc_367F
0x3675  ldarg.0
0x3676  ldloc.3
0x3677  ldloc.2
0x3678  ldloc.1
0x3679  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::FormatWarningJsonString(string processControlStrings, string warning, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.AppProcessControlWarning warningCode)
0x367e  ret
0x367f  ldnull
0x3680  ret
0x3681  newobj   instance void [Microsoft.Crm]Microsoft.Crm.BpfHelper::.ctor()
0x3686  ldarg.0
0x3687  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x368c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.IBpfHelper::StripCustomJavaScript(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x3691  pop
0x3692  ldarg.0
0x3693  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::get_IsTurboForm()
0x3698  brtrue.s loc_36A2
0x369a  ldarg.0
0x369b  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::SerializeProcessForClient()
0x36a0  br.s     loc_36A7
0x36a2  ldstr    aNull// "null"
0x36a7  stloc.s  4
0x36a9  ldarg.0
0x36aa  ldarg.1
0x36ab  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetEntityStages(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity currentEntity)
0x36b0  stloc.s  5
0x36b2  ldarg.0
0x36b3  ldloc.s  4
0x36b5  ldloc.3
0x36b6  ldloc.s  5
0x36b8  ldarg.0
0x36b9  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x36be  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x36c3  stloc.s  6
0x36c5  ldloca.s 6
0x36c7  constrained. [mscorlib]System.Guid
0x36cd  callvirt instance string [mscorlib]System.Object::ToString()
0x36d2  ldloc.2
0x36d3  ldloc.1
0x36d4  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::FormatDataJsonString(string processStages, string processControlStrings, string entityStages, string processId, string warning, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.AppProcessControlWarning warningCode)
0x36d9  ret
```
