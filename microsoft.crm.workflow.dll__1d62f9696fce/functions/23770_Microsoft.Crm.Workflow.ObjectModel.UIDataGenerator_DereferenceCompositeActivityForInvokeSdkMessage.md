# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::DereferenceCompositeActivityForInvokeSdkMessage

- ea: `0x23770`
- end: `0x238fc`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::DereferenceCompositeActivityForInvokeSdkMessage`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x23920`

## callees

- `0x23770`
- `0x2d0b0`
- `0x2d180`
- `0x2d1a0`
- `0x2d1c0`
- `0x2d1f0`
- `0x2d220`
- `0x2d260`
- `0x2d280`
- `0x2d2b0`
- `0x2d2d0`
- `0x2d2f0`
- `0x2d320`
- `0x2d360`
- `0x2d380`
- `0x2e2f0`

## pseudocode

```c

```

## disassembly

```asm
0x23770  ldarg.1
0x23771  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x23776  stloc.0
0x23777  newobj   instance void Microsoft.Crm.Workflow.Activities.Composite::.ctor()
0x2377c  stloc.1
0x2377d  ldloc.0
0x2377e  ldtoken  Microsoft.Crm.Workflow.Activities.StageComposite
0x23783  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23788  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2378d  brfalse.s loc_237D0
0x2378f  newobj   instance void Microsoft.Crm.Workflow.Activities.StageComposite::.ctor()
0x23794  dup
0x23795  ldarg.1
0x23796  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x2379b  ldstr    aStageid// "StageId"
0x237a0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x237a5  castclass [mscorlib]System.String
0x237aa  callvirt instance void Microsoft.Crm.Workflow.Activities.StageComposite::set_StageId(string value)
0x237af  dup
0x237b0  ldarg.1
0x237b1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x237b6  ldstr    aStagecategory// "StageCategory"
0x237bb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x237c0  castclass [mscorlib]System.String
0x237c5  callvirt instance void Microsoft.Crm.Workflow.Activities.StageComposite::set_StageCategory(string value)
0x237ca  stloc.1
0x237cb  br       loc_23889
0x237d0  ldloc.0
0x237d1  ldtoken  Microsoft.Crm.Workflow.Activities.StepComposite
0x237d6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x237db  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x237e0  brfalse.s loc_23820
0x237e2  newobj   instance void Microsoft.Crm.Workflow.Activities.StepComposite::.ctor()
0x237e7  dup
0x237e8  ldarg.1
0x237e9  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x237ee  ldstr    aProcessstepid// "ProcessStepId"
0x237f3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x237f8  castclass [mscorlib]System.String
0x237fd  callvirt instance void Microsoft.Crm.Workflow.Activities.StepComposite::set_ProcessStepId(string value)
0x23802  dup
0x23803  ldarg.1
0x23804  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x23809  ldstr    aIsprocessrequi// "IsProcessRequired"
0x2380e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23813  unbox.any [mscorlib]System.Boolean
0x23818  callvirt instance void Microsoft.Crm.Workflow.Activities.StepComposite::set_IsProcessRequired(bool value)
0x2381d  stloc.1
0x2381e  br.s     loc_23889
0x23820  ldloc.0
0x23821  ldtoken  Microsoft.Crm.Workflow.Activities.EntityComposite
0x23826  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2382b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x23830  brfalse.s loc_23889
0x23832  newobj   instance void Microsoft.Crm.Workflow.Activities.EntityComposite::.ctor()
0x23837  dup
0x23838  ldarg.1
0x23839  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x2383e  ldstr    aRelationshipna// "RelationshipName"
0x23843  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23848  castclass [mscorlib]System.String
0x2384d  callvirt instance void Microsoft.Crm.Workflow.Activities.EntityComposite::set_RelationshipName(string value)
0x23852  dup
0x23853  ldarg.1
0x23854  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x23859  ldstr    aAttributename_0// "AttributeName"
0x2385e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23863  castclass [mscorlib]System.String
0x23868  callvirt instance void Microsoft.Crm.Workflow.Activities.EntityComposite::set_AttributeName(string value)
0x2386d  dup
0x2386e  ldarg.1
0x2386f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x23874  ldstr    aIsclosedloop// "IsClosedLoop"
0x23879  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2387e  unbox.any [mscorlib]System.Boolean
0x23883  callvirt instance void Microsoft.Crm.Workflow.Activities.EntityComposite::set_IsClosedLoop(bool value)
0x23888  stloc.1
0x23889  ldarg.1
0x2388a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x2388f  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Count()
0x23894  ldc.i4.0
0x23895  ble.s    loc_238FA
0x23897  ldloc.1
0x23898  ldarg.1
0x23899  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x2389e  ldstr    aVariables// "Variables"
0x238a3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x238a8  isinst   class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>
0x238ad  callvirt instance void Microsoft.Crm.Workflow.Activities.Composite::set_Variables(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> value)
0x238b2  ldloc.1
0x238b3  ldarg.1
0x238b4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x238b9  ldstr    aActivities// "Activities"
0x238be  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x238c3  isinst   class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>
0x238c8  callvirt instance void Microsoft.Crm.Workflow.Activities.Composite::set_Activities(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> value)
0x238cd  ldarg.1
0x238ce  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x238d3  ldstr    aSteplabels// "StepLabels"
0x238d8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x238dd  brfalse.s loc_238FA
0x238df  ldloc.1
0x238e0  ldarg.1
0x238e1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x238e6  ldstr    aSteplabels// "StepLabels"
0x238eb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x238f0  castclass class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel>
0x238f5  callvirt instance void Microsoft.Crm.Workflow.Activities.Composite::set_StepLabels(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel> value)
0x238fa  ldloc.1
0x238fb  ret
```
