# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ReferenceActivityForComposite

- ea: `0x2a230`
- end: `0x2a456`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ReferenceActivityForComposite`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x29e50`

## callees

- `0x2a230`
- `0x2d170`
- `0x2d190`
- `0x2d1b0`
- `0x2d210`
- `0x2d230`
- `0x2d250`
- `0x2d2a0`
- `0x2d2c0`
- `0x2d310`
- `0x2d350`
- `0x2d370`
- `0x2d410`
- `0x2d430`
- `0x2d450`
- `0x2d470`
- `0x2d490`
- `0x2d4b0`
- `0x2e4c0`

## string_xrefs

- `0x2a3fa`: `ProcessId`

## pseudocode

```c

```

## disassembly

```asm
0x2a230  ldarg.3
0x2a231  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a236  ldstr    aVariables// "Variables"
0x2a23b  ldarg.1
0x2a23c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.Activities.Composite::get_Variables()
0x2a241  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a246  ldarg.3
0x2a247  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a24c  ldstr    aActivities// "Activities"
0x2a251  ldarg.1
0x2a252  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x2a257  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a25c  ldarg.1
0x2a25d  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel> Microsoft.Crm.Workflow.Activities.Composite::get_StepLabels()
0x2a262  brfalse.s loc_2A288
0x2a264  ldarg.1
0x2a265  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel> Microsoft.Crm.Workflow.Activities.Composite::get_StepLabels()
0x2a26a  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel>::get_Count()
0x2a26f  ldc.i4.0
0x2a270  ble.s    loc_2A288
0x2a272  ldarg.3
0x2a273  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a278  ldstr    aSteplabels// "StepLabels"
0x2a27d  ldarg.1
0x2a27e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel> Microsoft.Crm.Workflow.Activities.Composite::get_StepLabels()
0x2a283  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a288  ldarg.1
0x2a289  isinst   Microsoft.Crm.Workflow.Activities.StageComposite
0x2a28e  stloc.0
0x2a28f  ldloc.0
0x2a290  brfalse.s loc_2A2F8
0x2a292  ldarg.3
0x2a293  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a298  ldstr    aStageid// "StageId"
0x2a29d  ldloc.0
0x2a29e  callvirt instance string Microsoft.Crm.Workflow.Activities.StageComposite::get_StageId()
0x2a2a3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a2a8  ldarg.3
0x2a2a9  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a2ae  ldstr    aStagecategory// "StageCategory"
0x2a2b3  ldloc.0
0x2a2b4  callvirt instance string Microsoft.Crm.Workflow.Activities.StageComposite::get_StageCategory()
0x2a2b9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a2be  ldarg.3
0x2a2bf  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a2c4  ldstr    aNextstageid// "NextStageId"
0x2a2c9  ldloc.0
0x2a2ca  callvirt instance string Microsoft.Crm.Workflow.Activities.StageComposite::get_NextStageId()
0x2a2cf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a2d4  ldloc.0
0x2a2d5  isinst   Microsoft.Crm.Workflow.Activities.PageComposite
0x2a2da  stloc.1
0x2a2db  ldloc.1
0x2a2dc  brfalse  loc_2A455
0x2a2e1  ldarg.3
0x2a2e2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a2e7  ldstr    aPagelayoutid// "PageLayoutId"
0x2a2ec  ldloc.1
0x2a2ed  callvirt instance string Microsoft.Crm.Workflow.Activities.PageComposite::get_PageLayoutId()
0x2a2f2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a2f7  ret
0x2a2f8  ldarg.2
0x2a2f9  ldtoken  Microsoft.Crm.Workflow.Activities.StepComposite
0x2a2fe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a303  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a308  brfalse.s loc_2A343
0x2a30a  ldarg.1
0x2a30b  castclass Microsoft.Crm.Workflow.Activities.StepComposite
0x2a310  stloc.2
0x2a311  ldarg.3
0x2a312  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a317  ldstr    aProcessstepid// "ProcessStepId"
0x2a31c  ldloc.2
0x2a31d  callvirt instance string Microsoft.Crm.Workflow.Activities.StepComposite::get_ProcessStepId()
0x2a322  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a327  ldarg.3
0x2a328  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a32d  ldstr    aIsprocessrequi// "IsProcessRequired"
0x2a332  ldloc.2
0x2a333  callvirt instance bool Microsoft.Crm.Workflow.Activities.StepComposite::get_IsProcessRequired()
0x2a338  box      [mscorlib]System.Boolean
0x2a33d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a342  ret
0x2a343  ldarg.2
0x2a344  ldtoken  Microsoft.Crm.Workflow.Activities.EntityComposite
0x2a349  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a34e  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a353  brfalse.s loc_2A3A4
0x2a355  ldarg.1
0x2a356  castclass Microsoft.Crm.Workflow.Activities.EntityComposite
0x2a35b  stloc.3
0x2a35c  ldarg.3
0x2a35d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a362  ldstr    aRelationshipna// "RelationshipName"
0x2a367  ldloc.3
0x2a368  callvirt instance string Microsoft.Crm.Workflow.Activities.EntityComposite::get_RelationshipName()
0x2a36d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a372  ldarg.3
0x2a373  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a378  ldstr    aAttributename_0// "AttributeName"
0x2a37d  ldloc.3
0x2a37e  callvirt instance string Microsoft.Crm.Workflow.Activities.EntityComposite::get_AttributeName()
0x2a383  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a388  ldarg.3
0x2a389  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a38e  ldstr    aIsclosedloop// "IsClosedLoop"
0x2a393  ldloc.3
0x2a394  callvirt instance bool Microsoft.Crm.Workflow.Activities.EntityComposite::get_IsClosedLoop()
0x2a399  box      [mscorlib]System.Boolean
0x2a39e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a3a3  ret
0x2a3a4  ldarg.2
0x2a3a5  ldtoken  Microsoft.Crm.Workflow.Activities.ActionComposite
0x2a3aa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a3af  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a3b4  brfalse  loc_2A455
0x2a3b9  ldarg.1
0x2a3ba  castclass Microsoft.Crm.Workflow.Activities.ActionComposite
0x2a3bf  stloc.s  4
0x2a3c1  ldarg.3
0x2a3c2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a3c7  ldstr    aActionid// "ActionId"
0x2a3cc  ldloc.s  4
0x2a3ce  callvirt instance string Microsoft.Crm.Workflow.Activities.ActionComposite::get_ActionId()
0x2a3d3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a3d8  ldarg.3
0x2a3d9  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a3de  ldstr    aActiontype// "ActionType"
0x2a3e3  ldloc.s  4
0x2a3e5  callvirt instance int32 Microsoft.Crm.Workflow.Activities.ActionComposite::get_ActionType()
0x2a3ea  box      [mscorlib]System.Int32
0x2a3ef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a3f4  ldarg.3
0x2a3f5  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a3fa  ldstr    aProcessid_0// "ProcessId"
0x2a3ff  ldloc.s  4
0x2a401  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Activities.ActionComposite::get_ProcessId()
0x2a406  box      [mscorlib]System.Guid
0x2a40b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a410  ldarg.3
0x2a411  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a416  ldstr    aUniquename_0// "UniqueName"
0x2a41b  ldloc.s  4
0x2a41d  callvirt instance string Microsoft.Crm.Workflow.Activities.ActionComposite::get_UniqueName()
0x2a422  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a427  ldarg.3
0x2a428  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a42d  ldstr    aTriggerevents// "TriggerEvents"
0x2a432  ldloc.s  4
0x2a434  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData[] Microsoft.Crm.Workflow.Activities.ActionComposite::get_TriggerEvents()
0x2a439  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a43e  ldarg.3
0x2a43f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a444  ldstr    aActioncontrol// "ActionControl"
0x2a449  ldloc.s  4
0x2a44b  callvirt instance class [System.Activities]System.Activities.Statements.Sequence Microsoft.Crm.Workflow.Activities.ActionComposite::get_ActionControl()
0x2a450  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a455  ret
```
