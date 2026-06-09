# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetStepsControlDescriptors

- ea: `0x50e0`
- end: `0x5384`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetStepsControlDescriptors`
- size: `676`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x4fc0`
- `0x50d0`

## callees

- `0x3570`
- `0x4660`
- `0x4790`
- `0x4b60`
- `0x5090`
- `0x50e0`
- `0x57f0`

## string_xrefs

- `0x5215`: `processid`
- `0x5354`: `processid`
- `0x522a`: `traversedpath`
- `0x536e`: `traversedpath`

## pseudocode

```c

```

## disassembly

```asm
0x50e0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetCurrentEntityId()
0x50e5  stloc.0
0x50e6  ldarg.0
0x50e7  ldloc.0
0x50e8  ldarg.1
0x50e9  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::InitializeProcess(valuetype [mscorlib]System.Guid entityId, int32 entityTypeCode)
0x50ee  ldarg.0
0x50ef  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x50f4  brtrue.s loc_50FC
0x50f6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor>::.ctor()
0x50fb  ret
0x50fc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor>::.ctor()
0x5101  stloc.1
0x5102  ldc.i4.0
0x5103  stloc.2
0x5104  ldc.i4.0
0x5105  stloc.3
0x5106  ldc.i4.0
0x5107  stloc.s  4
0x5109  ldarg.1
0x510a  ldarg.0
0x510b  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::get_OrganizationContext()
0x5110  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5115  stloc.s  5
0x5117  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x511c  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserUICulture()
0x5121  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x5126  stloc.s  6
0x5128  ldarg.0
0x5129  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x512e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x5133  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::GetEnumerator()
0x5138  stloc.s  7
0x513a  br       loc_531C
0x513f  ldloc.s  7
0x5141  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Current()
0x5146  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep
0x514b  stloc.s  8
0x514d  ldloc.s  8
0x514f  brfalse  loc_531C
0x5154  ldloc.s  8
0x5156  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep::get_EntityLogicalName()
0x515b  ldloc.s  5
0x515d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x5162  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5167  brtrue   loc_531C
0x516c  ldloc.s  8
0x516e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x5173  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::GetEnumerator()
0x5178  stloc.s  9
0x517a  br       loc_5302
0x517f  ldloc.s  9
0x5181  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Current()
0x5186  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep
0x518b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x5190  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::GetEnumerator()
0x5195  stloc.s  0xA
0x5197  br       loc_52E8
0x519c  ldloc.s  0xA
0x519e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Current()
0x51a3  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep
0x51a8  stloc.s  0xB
0x51aa  ldloc.s  0xB
0x51ac  brfalse  loc_52E8
0x51b1  ldloc.s  0xB
0x51b3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x51b8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::GetEnumerator()
0x51bd  stloc.s  0xC
0x51bf  br       loc_52CE
0x51c4  ldloc.s  0xC
0x51c6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Current()
0x51cb  stloc.s  0xD
0x51cd  ldloc.s  0xD
0x51cf  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::GetControlStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x51d4  stloc.s  0xE
0x51d6  ldloc.s  0xE
0x51d8  brfalse  loc_52CE
0x51dd  ldarg.0
0x51de  ldloc.s  0xE
0x51e0  ldloc.s  8
0x51e2  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep::get_EntityLogicalName()
0x51e7  ldloc.s  6
0x51e9  ldarg.2
0x51ea  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::CreateControlDescriptor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep control, string entityLogicalName, int32 lcid, string idPrefix)
0x51ef  stloc.s  0xF
0x51f1  ldloc.1
0x51f2  ldloc.s  0xF
0x51f4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor>::Add(var<u1>)
0x51f9  ldloc.s  0xE
0x51fb  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_DataFieldName()
0x5200  ldstr    aStageid// "stageid"
0x5205  call     bool [mscorlib]System.String::op_Equality(string, string)
0x520a  brfalse.s loc_520E
0x520c  ldc.i4.1
0x520d  stloc.2
0x520e  ldloc.s  0xE
0x5210  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_DataFieldName()
0x5215  ldstr    aProcessid// "processid"
0x521a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x521f  brfalse.s loc_5223
0x5221  ldc.i4.1
0x5222  stloc.3
0x5223  ldloc.s  0xE
0x5225  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_DataFieldName()
0x522a  ldstr    aTraversedpath// "traversedpath"
0x522f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5234  brfalse.s loc_5239
0x5236  ldc.i4.1
0x5237  stloc.s  4
0x5239  ldloc.s  0xD
0x523b  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x5240  stloc.s  0x10
0x5242  ldloc.s  0x10
0x5244  brfalse  loc_52CE
0x5249  ldloc.s  0x10
0x524b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x5250  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::GetEnumerator()
0x5255  stloc.s  0x11
0x5257  br.s     loc_52B7
0x5259  ldloc.s  0x11
0x525b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Current()
0x5260  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep
0x5265  stloc.s  0x12
0x5267  ldloc.s  0x12
0x5269  brfalse.s loc_52B7
0x526b  ldsfld   string [mscorlib]System.String::Empty
0x5270  stloc.s  0x13
0x5272  ldloc.s  0x12
0x5274  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::get_ValueExpression()
0x5279  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression
0x527e  brfalse.s loc_5293
0x5280  ldloc.s  0x12
0x5282  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::get_ValueExpression()
0x5287  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression
0x528c  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::get_AttributeName()
0x5291  stloc.s  0x13
0x5293  ldloc.s  0x13
0x5295  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x529a  brtrue.s loc_52B7
0x529c  ldarg.0
0x529d  ldloc.s  0x12
0x529f  ldloc.s  8
0x52a1  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep::get_EntityLogicalName()
0x52a6  ldloc.s  0x13
0x52a8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::CreateControlDescriptorForAssignVariableStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep assginVariableStep, string entityLogicalName, string datafieldName)
0x52ad  stloc.s  0xF
0x52af  ldloc.1
0x52b0  ldloc.s  0xF
0x52b2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor>::Add(var<u1>)
0x52b7  ldloc.s  0x11
0x52b9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x52be  brtrue.s loc_5259
0x52c0  leave.s  loc_52CE
0x52c2  ldloc.s  0x11
0x52c4  brfalse.s loc_52CD
0x52c6  ldloc.s  0x11
0x52c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x52cd  endfinally
0x52ce  ldloc.s  0xC
0x52d0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x52d5  brtrue   loc_51C4
0x52da  leave.s  loc_52E8
0x52dc  ldloc.s  0xC
0x52de  brfalse.s loc_52E7
0x52e0  ldloc.s  0xC
0x52e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x52e7  endfinally
0x52e8  ldloc.s  0xA
0x52ea  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x52ef  brtrue   loc_519C
0x52f4  leave.s  loc_5302
0x52f6  ldloc.s  0xA
0x52f8  brfalse.s loc_5301
0x52fa  ldloc.s  0xA
0x52fc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5301  endfinally
0x5302  ldloc.s  9
0x5304  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5309  brtrue   loc_517F
0x530e  leave.s  loc_531C
0x5310  ldloc.s  9
0x5312  brfalse.s loc_531B
0x5314  ldloc.s  9
0x5316  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x531b  endfinally
0x531c  ldloc.s  7
0x531e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5323  brtrue   loc_513F
0x5328  leave.s  loc_5336
0x532a  ldloc.s  7
0x532c  brfalse.s loc_5335
0x532e  ldloc.s  7
0x5330  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5335  endfinally
0x5336  ldloc.2
0x5337  brtrue.s loc_534F
0x5339  ldarg.0
0x533a  ldarg.1
0x533b  ldstr    aStageid// "stageid"
0x5340  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::CreateAdditionalControl(int32 entityTypeCode, string attributeName)
0x5345  stloc.s  0x14
0x5347  ldloc.1
0x5348  ldloc.s  0x14
0x534a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor>::Add(var<u1>)
0x534f  ldloc.3
0x5350  brtrue.s loc_5368
0x5352  ldarg.0
0x5353  ldarg.1
0x5354  ldstr    aProcessid// "processid"
0x5359  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::CreateAdditionalControl(int32 entityTypeCode, string attributeName)
0x535e  stloc.s  0x15
0x5360  ldloc.1
0x5361  ldloc.s  0x15
0x5363  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor>::Add(var<u1>)
0x5368  ldloc.s  4
0x536a  brtrue.s loc_5382
0x536c  ldarg.0
0x536d  ldarg.1
0x536e  ldstr    aTraversedpath// "traversedpath"
0x5373  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::CreateAdditionalControl(int32 entityTypeCode, string attributeName)
0x5378  stloc.s  0x16
0x537a  ldloc.1
0x537b  ldloc.s  0x16
0x537d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor>::Add(var<u1>)
0x5382  ldloc.1
0x5383  ret
```
