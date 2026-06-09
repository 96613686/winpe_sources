# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::DereferenceCompositeActivity

- ea: `0x23430`
- end: `0x2376d`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::DereferenceCompositeActivity`
- size: `829`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x22f90`

## callees

- `0xf010`
- `0x23430`
- `0x2cfd0`
- `0x2d0b0`
- `0x2d180`
- `0x2d1a0`
- `0x2d1c0`
- `0x2d1f0`
- `0x2d220`
- `0x2d240`
- `0x2d260`
- `0x2d280`
- `0x2d2b0`
- `0x2d2d0`
- `0x2d2f0`
- `0x2d320`
- `0x2d360`
- `0x2d380`
- `0x2d3f0`
- `0x2d420`
- `0x2d440`
- `0x2d460`
- `0x2d480`
- `0x2d4a0`
- `0x2d4c0`
- `0x2e4a0`
- `0x2e4d0`

## string_xrefs

- `0x236a2`: `ProcessId`

## pseudocode

```c

```

## disassembly

```asm
0x23430  newobj   instance void Microsoft.Crm.Workflow.Activities.Composite::.ctor()
0x23435  stloc.0
0x23436  ldarg.1
0x23437  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference::get_AssemblyQualifiedName()
0x2343c  ldtoken  Microsoft.Crm.Workflow.Activities.StageComposite
0x23441  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23446  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x2344b  call     bool Microsoft.Crm.Workflow.Utility.WorkflowUtility::CompareIgnoringVersion(string reference1, string reference2)
0x23450  brfalse.s loc_234B2
0x23452  newobj   instance void Microsoft.Crm.Workflow.Activities.StageComposite::.ctor()
0x23457  dup
0x23458  ldarg.1
0x23459  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2345e  ldstr    aStageid// "StageId"
0x23463  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23468  castclass [mscorlib]System.String
0x2346d  callvirt instance void Microsoft.Crm.Workflow.Activities.StageComposite::set_StageId(string value)
0x23472  dup
0x23473  ldarg.1
0x23474  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x23479  ldstr    aStagecategory// "StageCategory"
0x2347e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23483  castclass [mscorlib]System.String
0x23488  callvirt instance void Microsoft.Crm.Workflow.Activities.StageComposite::set_StageCategory(string value)
0x2348d  ldarg.1
0x2348e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x23493  ldstr    aNextstageid// "NextStageId"
0x23498  ldloca.s 1
0x2349a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x2349f  pop
0x234a0  dup
0x234a1  ldloc.1
0x234a2  castclass [mscorlib]System.String
0x234a7  callvirt instance void Microsoft.Crm.Workflow.Activities.StageComposite::set_NextStageId(string value)
0x234ac  stloc.0
0x234ad  br       loc_23708
0x234b2  ldarg.1
0x234b3  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference::get_AssemblyQualifiedName()
0x234b8  ldtoken  Microsoft.Crm.Workflow.Activities.PageComposite
0x234bd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x234c2  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x234c7  call     bool Microsoft.Crm.Workflow.Utility.WorkflowUtility::CompareIgnoringVersion(string reference1, string reference2)
0x234cc  brfalse.s loc_23545
0x234ce  newobj   instance void Microsoft.Crm.Workflow.Activities.PageComposite::.ctor()
0x234d3  dup
0x234d4  ldarg.1
0x234d5  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x234da  ldstr    aStageid// "StageId"
0x234df  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x234e4  castclass [mscorlib]System.String
0x234e9  callvirt instance void Microsoft.Crm.Workflow.Activities.StageComposite::set_StageId(string value)
0x234ee  dup
0x234ef  ldarg.1
0x234f0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x234f5  ldstr    aStagecategory// "StageCategory"
0x234fa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x234ff  castclass [mscorlib]System.String
0x23504  callvirt instance void Microsoft.Crm.Workflow.Activities.StageComposite::set_StageCategory(string value)
0x23509  dup
0x2350a  ldarg.1
0x2350b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x23510  ldstr    aNextstageid// "NextStageId"
0x23515  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2351a  castclass [mscorlib]System.String
0x2351f  callvirt instance void Microsoft.Crm.Workflow.Activities.StageComposite::set_NextStageId(string value)
0x23524  dup
0x23525  ldarg.1
0x23526  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2352b  ldstr    aPagelayoutid// "PageLayoutId"
0x23530  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23535  castclass [mscorlib]System.String
0x2353a  callvirt instance void Microsoft.Crm.Workflow.Activities.PageComposite::set_PageLayoutId(string value)
0x2353f  stloc.0
0x23540  br       loc_23708
0x23545  ldarg.1
0x23546  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference::get_AssemblyQualifiedName()
0x2354b  ldtoken  Microsoft.Crm.Workflow.Activities.StepComposite
0x23550  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23555  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x2355a  call     bool Microsoft.Crm.Workflow.Utility.WorkflowUtility::CompareIgnoringVersion(string reference1, string reference2)
0x2355f  brfalse.s loc_235A2
0x23561  newobj   instance void Microsoft.Crm.Workflow.Activities.StepComposite::.ctor()
0x23566  dup
0x23567  ldarg.1
0x23568  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2356d  ldstr    aProcessstepid// "ProcessStepId"
0x23572  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23577  castclass [mscorlib]System.String
0x2357c  callvirt instance void Microsoft.Crm.Workflow.Activities.StepComposite::set_ProcessStepId(string value)
0x23581  dup
0x23582  ldarg.1
0x23583  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x23588  ldstr    aIsprocessrequi// "IsProcessRequired"
0x2358d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23592  unbox.any [mscorlib]System.Boolean
0x23597  callvirt instance void Microsoft.Crm.Workflow.Activities.StepComposite::set_IsProcessRequired(bool value)
0x2359c  stloc.0
0x2359d  br       loc_23708
0x235a2  ldarg.1
0x235a3  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference::get_AssemblyQualifiedName()
0x235a8  ldtoken  Microsoft.Crm.Workflow.Activities.EntityComposite
0x235ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x235b2  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x235b7  call     bool Microsoft.Crm.Workflow.Utility.WorkflowUtility::CompareIgnoringVersion(string reference1, string reference2)
0x235bc  brfalse.s loc_2361A
0x235be  newobj   instance void Microsoft.Crm.Workflow.Activities.EntityComposite::.ctor()
0x235c3  dup
0x235c4  ldarg.1
0x235c5  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x235ca  ldstr    aRelationshipna// "RelationshipName"
0x235cf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x235d4  castclass [mscorlib]System.String
0x235d9  callvirt instance void Microsoft.Crm.Workflow.Activities.EntityComposite::set_RelationshipName(string value)
0x235de  dup
0x235df  ldarg.1
0x235e0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x235e5  ldstr    aAttributename_0// "AttributeName"
0x235ea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x235ef  castclass [mscorlib]System.String
0x235f4  callvirt instance void Microsoft.Crm.Workflow.Activities.EntityComposite::set_AttributeName(string value)
0x235f9  dup
0x235fa  ldarg.1
0x235fb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x23600  ldstr    aIsclosedloop// "IsClosedLoop"
0x23605  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2360a  unbox.any [mscorlib]System.Boolean
0x2360f  callvirt instance void Microsoft.Crm.Workflow.Activities.EntityComposite::set_IsClosedLoop(bool value)
0x23614  stloc.0
0x23615  br       loc_23708
0x2361a  ldarg.1
0x2361b  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference::get_AssemblyQualifiedName()
0x23620  ldtoken  Microsoft.Crm.Workflow.BusinessProcessFlowActivities.StageRelationshipCollectionComposite
0x23625  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2362a  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x2362f  call     bool Microsoft.Crm.Workflow.Utility.WorkflowUtility::CompareIgnoringVersion(string reference1, string reference2)
0x23634  brfalse.s loc_23641
0x23636  newobj   instance void Microsoft.Crm.Workflow.BusinessProcessFlowActivities.StageRelationshipCollectionComposite::.ctor()
0x2363b  stloc.0
0x2363c  br       loc_23708
0x23641  ldarg.1
0x23642  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference::get_AssemblyQualifiedName()
0x23647  ldtoken  Microsoft.Crm.Workflow.Activities.ActionComposite
0x2364c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23651  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x23656  call     bool Microsoft.Crm.Workflow.Utility.WorkflowUtility::CompareIgnoringVersion(string reference1, string reference2)
0x2365b  brfalse  loc_23708
0x23660  newobj   instance void Microsoft.Crm.Workflow.Activities.ActionComposite::.ctor()
0x23665  dup
0x23666  ldarg.1
0x23667  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2366c  ldstr    aActionid// "ActionId"
0x23671  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23676  castclass [mscorlib]System.String
0x2367b  callvirt instance void Microsoft.Crm.Workflow.Activities.ActionComposite::set_ActionId(string value)
0x23680  dup
0x23681  ldarg.1
0x23682  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x23687  ldstr    aActiontype// "ActionType"
0x2368c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23691  unbox.any [mscorlib]System.Int32
0x23696  callvirt instance void Microsoft.Crm.Workflow.Activities.ActionComposite::set_ActionType(int32 value)
0x2369b  dup
0x2369c  ldarg.1
0x2369d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x236a2  ldstr    aProcessid_0// "ProcessId"
0x236a7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x236ac  unbox.any [mscorlib]System.Guid
0x236b1  callvirt instance void Microsoft.Crm.Workflow.Activities.ActionComposite::set_ProcessId(valuetype [mscorlib]System.Guid value)
0x236b6  dup
0x236b7  ldarg.1
0x236b8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x236bd  ldstr    aUniquename_0// "UniqueName"
0x236c2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x236c7  castclass [mscorlib]System.String
0x236cc  callvirt instance void Microsoft.Crm.Workflow.Activities.ActionComposite::set_UniqueName(string value)
0x236d1  dup
0x236d2  ldarg.1
0x236d3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x236d8  ldstr    aTriggerevents// "TriggerEvents"
0x236dd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x236e2  castclass class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData[]
0x236e7  callvirt instance void Microsoft.Crm.Workflow.Activities.ActionComposite::set_TriggerEvents(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData[] value)
0x236ec  dup
0x236ed  ldarg.1
0x236ee  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x236f3  ldstr    aActioncontrol// "ActionControl"
0x236f8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x236fd  castclass [System.Activities]System.Activities.Statements.Sequence
0x23702  callvirt instance void Microsoft.Crm.Workflow.Activities.ActionComposite::set_ActionControl(class [System.Activities]System.Activities.Statements.Sequence value)
0x23707  stloc.0
0x23708  ldloc.0
0x23709  ldarg.1
0x2370a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2370f  ldstr    aVariables// "Variables"
0x23714  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23719  isinst   class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>
0x2371e  callvirt instance void Microsoft.Crm.Workflow.Activities.Composite::set_Variables(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> value)
0x23723  ldloc.0
0x23724  ldarg.1
0x23725  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2372a  ldstr    aActivities// "Activities"
0x2372f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23734  isinst   class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>
0x23739  callvirt instance void Microsoft.Crm.Workflow.Activities.Composite::set_Activities(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> value)
0x2373e  ldarg.1
0x2373f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x23744  ldstr    aSteplabels// "StepLabels"
0x23749  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2374e  brfalse.s loc_2376B
0x23750  ldloc.0
0x23751  ldarg.1
0x23752  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x23757  ldstr    aSteplabels// "StepLabels"
0x2375c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23761  castclass class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel>
0x23766  callvirt instance void Microsoft.Crm.Workflow.Activities.Composite::set_StepLabels(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel> value)
0x2376b  ldloc.0
0x2376c  ret
```
