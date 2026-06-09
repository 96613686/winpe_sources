# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderDataStep

- ea: `0x44d0`
- end: `0x45e6`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderDataStep`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x4440`

## callees

- `0x1330`
- `0x3570`
- `0x44d0`
- `0x45f0`
- `0x4660`
- `0x4890`
- `0x4fd0`

## pseudocode

```c

```

## disassembly

```asm
0x44d0  ldarg.1
0x44d1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x44d6  brfalse.s loc_44E5
0x44d8  ldarg.1
0x44d9  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x44de  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Count()
0x44e3  brtrue.s loc_44E7
0x44e5  ldnull
0x44e6  ret
0x44e7  ldnull
0x44e8  stloc.0
0x44e9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x44ee  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserUICulture()
0x44f3  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x44f8  stloc.1
0x44f9  ldarg.1
0x44fa  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x44ff  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::GetEnumerator()
0x4504  stloc.2
0x4505  br       loc_45CD
0x450a  ldloc.2
0x450b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Current()
0x4510  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::GetControlStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x4515  stloc.3
0x4516  ldloc.3
0x4517  brfalse  loc_45CD
0x451c  ldloc.3
0x451d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x4522  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x4527  brfalse.s loc_4570
0x4529  ldloc.3
0x452a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x452f  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x4534  stloc.s  5
0x4536  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x453b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x4540  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_BpfActionSupportPUV2()
0x4545  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x454a  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x454f  stloc.s  6
0x4551  ldarg.0
0x4552  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x4557  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x455c  brfalse.s loc_45CD
0x455e  ldloc.s  5
0x4560  brfalse.s loc_456C
0x4562  ldloc.s  5
0x4564  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep::get_ActionType()
0x4569  ldc.i4.1
0x456a  beq.s    loc_45CD
0x456c  ldloc.s  6
0x456e  brfalse.s loc_45CD
0x4570  ldarg.0
0x4571  ldloc.3
0x4572  ldarg.2
0x4573  ldloc.1
0x4574  ldsfld   string [mscorlib]System.String::Empty
0x4579  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::CreateControlDescriptor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep control, string entityLogicalName, int32 lcid, string idPrefix)
0x457e  stloc.s  4
0x4580  ldarg.0
0x4581  ldloc.s  4
0x4583  ldstr    asc_30804// ""
0x4588  call     instance class [System.Web]System.Web.UI.Control Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::CreateInnerControl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor controlDescriptor, string controlIdPrefix)
0x458d  stloc.s  7
0x458f  ldloc.s  7
0x4591  brtrue.s loc_4595
0x4593  leave.s  loc_45CD
0x4595  ldarg.1
0x4596  ldloc.1
0x4597  ldarg.0
0x4598  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::get_OrganizationContext()
0x459d  call     string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetStepName(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep step, int32 lcid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x45a2  stloc.s  8
0x45a4  ldarg.0
0x45a5  ldloc.s  7
0x45a7  ldloc.s  4
0x45a9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_ID()
0x45ae  ldloc.s  8
0x45b0  ldloc.s  8
0x45b2  ldarg.1
0x45b3  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep::get_IsProcessRequired()
0x45b8  ldarg.3
0x45b9  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderStepControl(class [System.Web]System.Web.UI.Control control, string controlID, string name, string description, bool isRequired, int32 stepIndex)
0x45be  stloc.0
0x45bf  leave.s  loc_45CD
0x45c1  ldloc.s  7
0x45c3  brfalse.s loc_45CC
0x45c5  ldloc.s  7
0x45c7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45cc  endfinally
0x45cd  ldloc.2
0x45ce  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x45d3  brtrue   loc_450A
0x45d8  leave.s  loc_45E4
0x45da  ldloc.2
0x45db  brfalse.s loc_45E3
0x45dd  ldloc.2
0x45de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45e3  endfinally
0x45e4  ldloc.0
0x45e5  ret
```
