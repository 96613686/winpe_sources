# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCompositeStep

- ea: `0x22480`
- end: `0x228e0`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCompositeStep`
- size: `1120`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1f130`

## callees

- `0x1f2e0`
- `0x1f310`
- `0x1f3a0`
- `0x1f400`
- `0x1f480`
- `0x1f4c0`
- `0x1f710`
- `0x1f990`
- `0x1fd50`
- `0x1fe30`
- `0x1ff20`
- `0x1ffb0`
- `0x20030`
- `0x200f0`
- `0x201a0`
- `0x20260`
- `0x202c0`
- `0x203d0`
- `0x20440`
- `0x204b0`
- `0x204f0`
- `0x20620`
- `0x206f0`
- `0x209c0`
- `0x20a40`
- `0x20bc0`
- `0x21790`
- `0x219c0`
- `0x21a20`
- `0x21d50`
- `0x21e60`
- `0x22210`
- `0x223a0`
- `0x22480`
- `0x228e0`

## string_xrefs

- `0x2248b`: `UpdateStep`
- `0x224ab`: `CreateStep`

## pseudocode

```c

```

## disassembly

```asm
0x22480  ldnull
0x22481  stloc.0
0x22482  ldarg.0
0x22483  ldarg.s  4
0x22485  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadVariables(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> variables)
0x2248a  ldarg.1
0x2248b  ldstr    aUpdatestep// "UpdateStep"
0x22490  ldc.i4.4
0x22491  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22496  brfalse.s loc_224AA
0x22498  ldarg.0
0x22499  ldarg.3
0x2249a  castclass [System.Activities]System.Activities.Statements.Sequence
0x2249f  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadUpdateStep(class [System.Activities]System.Activities.Statements.Sequence sequence)
0x224a4  stloc.0
0x224a5  br       loc_228DE
0x224aa  ldarg.1
0x224ab  ldstr    aCreatestep// "CreateStep"
0x224b0  ldc.i4.4
0x224b1  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x224b6  brfalse.s loc_224CB
0x224b8  ldarg.0
0x224b9  ldarg.1
0x224ba  ldarg.3
0x224bb  castclass [System.Activities]System.Activities.Statements.Sequence
0x224c0  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCreateStep(string stepId, class [System.Activities]System.Activities.Statements.Sequence sequence)
0x224c5  stloc.0
0x224c6  br       loc_228DE
0x224cb  ldarg.1
0x224cc  ldstr    aAssignstep// "AssignStep"
0x224d1  ldc.i4.4
0x224d2  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x224d7  brfalse.s loc_224EB
0x224d9  ldarg.0
0x224da  ldarg.3
0x224db  castclass [System.Activities]System.Activities.Statements.Sequence
0x224e0  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadAssignStep(class [System.Activities]System.Activities.Statements.Sequence sequence)
0x224e5  stloc.0
0x224e6  br       loc_228DE
0x224eb  ldarg.1
0x224ec  ldstr    aEntitystep// "EntityStep"
0x224f1  ldc.i4.4
0x224f2  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x224f7  brfalse.s loc_2250C
0x224f9  ldarg.0
0x224fa  ldarg.2
0x224fb  ldarg.3
0x224fc  castclass Microsoft.Crm.Workflow.Activities.Composite
0x22501  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntityStep(string entityLogicalName, class Microsoft.Crm.Workflow.Activities.Composite sequence)
0x22506  stloc.0
0x22507  br       loc_228DE
0x2250c  ldarg.1
0x2250d  ldstr    aRelationshipco// "RelationshipCollectionStep"
0x22512  ldc.i4.4
0x22513  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22518  brfalse.s loc_2252C
0x2251a  ldarg.0
0x2251b  ldarg.3
0x2251c  castclass Microsoft.Crm.Workflow.Activities.Composite
0x22521  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadRelationshipCollectionStep(class Microsoft.Crm.Workflow.Activities.Composite sequence)
0x22526  stloc.0
0x22527  br       loc_228DE
0x2252c  ldarg.1
0x2252d  ldstr    aRelationshipst// "RelationshipStep"
0x22532  ldc.i4.4
0x22533  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22538  brfalse.s loc_2254C
0x2253a  ldarg.0
0x2253b  ldarg.3
0x2253c  castclass [System.Activities]System.Activities.Statements.Sequence
0x22541  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RelationshipStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadRelationshipStep(class [System.Activities]System.Activities.Statements.Sequence sequence)
0x22546  stloc.0
0x22547  br       loc_228DE
0x2254c  ldarg.1
0x2254d  ldstr    aStagestep// "StageStep"
0x22552  ldc.i4.4
0x22553  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22558  brfalse.s loc_2256D
0x2255a  ldarg.0
0x2255b  ldarg.2
0x2255c  ldarg.3
0x2255d  castclass Microsoft.Crm.Workflow.Activities.Composite
0x22562  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStageStep(string stageName, class Microsoft.Crm.Workflow.Activities.Composite sequence)
0x22567  stloc.0
0x22568  br       loc_228DE
0x2256d  ldarg.1
0x2256e  ldstr    aPagestep// "PageStep"
0x22573  ldc.i4.4
0x22574  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22579  brfalse.s loc_2258E
0x2257b  ldarg.0
0x2257c  ldarg.2
0x2257d  ldarg.3
0x2257e  castclass Microsoft.Crm.Workflow.Activities.Composite
0x22583  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadPageStep(string stageName, class Microsoft.Crm.Workflow.Activities.Composite sequence)
0x22588  stloc.0
0x22589  br       loc_228DE
0x2258e  ldarg.1
0x2258f  ldstr    aStepstep// "StepStep"
0x22594  ldc.i4.4
0x22595  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2259a  brfalse.s loc_225AF
0x2259c  ldarg.0
0x2259d  ldarg.2
0x2259e  ldarg.3
0x2259f  castclass Microsoft.Crm.Workflow.Activities.Composite
0x225a4  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStepStep(string stepName, class Microsoft.Crm.Workflow.Activities.Composite sequence)
0x225a9  stloc.0
0x225aa  br       loc_228DE
0x225af  ldarg.1
0x225b0  ldstr    aSendemailstep// "SendEmailStep"
0x225b5  ldc.i4.4
0x225b6  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x225bb  brfalse.s loc_225F5
0x225bd  ldarg.3
0x225be  castclass [System.Activities]System.Activities.Statements.Sequence
0x225c3  stloc.1
0x225c4  ldarg.0
0x225c5  ldloc.1
0x225c6  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x225cb  ldc.i4.0
0x225cc  call     T0x2B000022
0x225d1  brtrue.s loc_225D6
0x225d3  ldc.i4.0
0x225d4  br.s     loc_225D7
0x225d6  ldc.i4.1
0x225d7  brfalse.s loc_225E7
0x225d9  ldarg.0
0x225da  ldarg.1
0x225db  ldloc.1
0x225dc  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSendEmailFromTemplateStep(string stepId, class [System.Activities]System.Activities.Statements.Sequence sequence)
0x225e1  stloc.0
0x225e2  br       loc_228DE
0x225e7  ldarg.0
0x225e8  ldarg.1
0x225e9  ldloc.1
0x225ea  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSendEmailStep(string stepId, class [System.Activities]System.Activities.Statements.Sequence sequence)
0x225ef  stloc.0
0x225f0  br       loc_228DE
0x225f5  ldarg.1
0x225f6  ldstr    aWaitstep// "WaitStep"
0x225fb  ldc.i4.4
0x225fc  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22601  brfalse.s loc_22616
0x22603  ldarg.0
0x22604  ldc.i4.1
0x22605  ldarg.3
0x22606  castclass Microsoft.Crm.Workflow.Activities.ConditionSequence
0x2260b  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadConditionStep(bool wait, class Microsoft.Crm.Workflow.Activities.ConditionSequence sequence)
0x22610  stloc.0
0x22611  br       loc_228DE
0x22616  ldarg.1
0x22617  ldstr    aConditionstep// "ConditionStep"
0x2261c  ldc.i4.4
0x2261d  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22622  brfalse.s loc_22637
0x22624  ldarg.0
0x22625  ldc.i4.0
0x22626  ldarg.3
0x22627  castclass Microsoft.Crm.Workflow.Activities.ConditionSequence
0x2262c  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadConditionStep(bool wait, class Microsoft.Crm.Workflow.Activities.ConditionSequence sequence)
0x22631  stloc.0
0x22632  br       loc_228DE
0x22637  ldarg.1
0x22638  ldstr    aCustomactivity_0// "CustomActivityStep"
0x2263d  ldc.i4.4
0x2263e  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22643  brfalse.s loc_22658
0x22645  ldarg.0
0x22646  ldarg.1
0x22647  ldarg.3
0x22648  castclass Microsoft.Crm.Workflow.Activities.Composite
0x2264d  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCustomActivityStep(string stepId, class Microsoft.Crm.Workflow.Activities.Composite sequence)
0x22652  stloc.0
0x22653  br       loc_228DE
0x22658  ldarg.1
0x22659  ldstr    aInteractionpag_1// "InteractionPageStep"
0x2265e  ldc.i4.4
0x2265f  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22664  brfalse.s loc_22678
0x22666  ldarg.0
0x22667  ldarg.3
0x22668  castclass Microsoft.Crm.Workflow.Activities.InteractionPage
0x2266d  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionPageStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadInteractionPageStep(class Microsoft.Crm.Workflow.Activities.InteractionPage interactionPage)
0x22672  stloc.0
0x22673  br       loc_228DE
0x22678  ldarg.1
0x22679  ldstr    aInteractionste// "InteractionStep"
0x2267e  ldc.i4.4
0x2267f  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22684  brfalse.s loc_22699
0x22686  ldarg.0
0x22687  ldarg.1
0x22688  ldarg.3
0x22689  castclass [System.Activities]System.Activities.Statements.Sequence
0x2268e  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadInteractionStep(string stepId, class [System.Activities]System.Activities.Statements.Sequence interactionSequence)
0x22693  stloc.0
0x22694  br       loc_228DE
0x22699  ldarg.1
0x2269a  ldstr    aQuerystep// "QueryStep"
0x2269f  ldc.i4.4
0x226a0  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x226a5  brfalse.s loc_226B9
0x226a7  ldarg.0
0x226a8  ldarg.3
0x226a9  castclass [System.Activities]System.Activities.Statements.Sequence
0x226ae  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadQueryStep(class [System.Activities]System.Activities.Statements.Sequence querySequence)
0x226b3  stloc.0
0x226b4  br       loc_228DE
0x226b9  ldarg.1
0x226ba  ldstr    aAssignvariable// "AssignVariableStep"
0x226bf  ldc.i4.4
0x226c0  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x226c5  brfalse.s loc_226D9
0x226c7  ldarg.0
0x226c8  ldarg.3
0x226c9  castclass [System.Activities]System.Activities.Statements.Sequence
0x226ce  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadAssignVariableStep(class [System.Activities]System.Activities.Statements.Sequence assignVariableSequence)
0x226d3  stloc.0
0x226d4  br       loc_228DE
0x226d9  ldarg.1
0x226da  ldstr    aAssignoutputar// "AssignOutputArgumentStep"
0x226df  ldc.i4.4
0x226e0  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x226e5  brfalse.s loc_226F9
0x226e7  ldarg.0
0x226e8  ldarg.3
0x226e9  castclass [System.Activities]System.Activities.Statements.Sequence
0x226ee  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadAssignOutputArgumentStep(class [System.Activities]System.Activities.Statements.Sequence assignOutputArgumentSequence)
0x226f3  stloc.0
0x226f4  br       loc_228DE
0x226f9  ldarg.1
0x226fa  ldstr    aChildinteracti// "ChildInteractiveWorkflowStep"
0x226ff  ldc.i4.4
0x22700  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22705  brfalse.s loc_22719
0x22707  ldarg.0
0x22708  ldarg.3
0x22709  castclass [System.Activities]System.Activities.Statements.Sequence
0x2270e  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStartChildInteractiveWorkflowStep(class [System.Activities]System.Activities.Statements.Sequence sequence)
0x22713  stloc.0
0x22714  br       loc_228DE
0x22719  ldarg.1
0x2271a  ldstr    aChildworkflows// "ChildWorkflowStep"
0x2271f  ldc.i4.4
0x22720  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22725  brfalse.s loc_22739
0x22727  ldarg.0
0x22728  ldarg.3
0x22729  castclass [System.Activities]System.Activities.Statements.Sequence
0x2272e  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStartChildWorkflowStep(class [System.Activities]System.Activities.Statements.Sequence sequence)
0x22733  stloc.0
0x22734  br       loc_228DE
0x22739  ldarg.1
0x2273a  ldstr    aStopworkflowst// "StopWorkflowStep"
0x2273f  ldc.i4.4
0x22740  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22745  brfalse.s loc_22759
0x22747  ldarg.0
0x22748  ldarg.3
0x22749  castclass [System.Activities]System.Activities.Statements.Sequence
0x2274e  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStopWorkflowStepSequence(class [System.Activities]System.Activities.Statements.Sequence sequence)
0x22753  stloc.0
0x22754  br       loc_228DE
0x22759  ldarg.1
0x2275a  ldstr    aSetvisibilitys// "SetVisibilityStep"
0x2275f  ldc.i4.4
0x22760  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22765  brfalse.s loc_22779
0x22767  ldarg.0
0x22768  ldarg.3
0x22769  castclass [System.Activities]System.Activities.Statements.Sequence
0x2276e  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetVisibilityStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSetVisibilityStep(class [System.Activities]System.Activities.Statements.Sequence sequence)
0x22773  stloc.0
0x22774  br       loc_228DE
0x22779  ldarg.1
0x2277a  ldstr    aSetattributeva// "SetAttributeValueStep"
0x2277f  ldc.i4.4
0x22780  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22785  brfalse.s loc_22799
0x22787  ldarg.0
0x22788  ldarg.3
0x22789  castclass [System.Activities]System.Activities.Statements.Sequence
0x2278e  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetAttributeValueStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSetAttributeValueStep(class [System.Activities]System.Activities.Statements.Sequence sequence)
0x22793  stloc.0
0x22794  br       loc_228DE
0x22799  ldarg.1
0x2279a  ldstr    aSetfieldrequir// "SetFieldRequiredLevelStep"
0x2279f  ldc.i4.4
0x227a0  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x227a5  brfalse.s loc_227B9
0x227a7  ldarg.0
0x227a8  ldarg.3
0x227a9  castclass [System.Activities]System.Activities.Statements.Sequence
0x227ae  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetFieldRequiredLevelStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSetFieldRequiredLevelStep(class [System.Activities]System.Activities.Statements.Sequence sequence)
0x227b3  stloc.0
0x227b4  br       loc_228DE
0x227b9  ldarg.1
0x227ba  ldstr    aSetdisplaymode// "SetDisplayModeStep"
0x227bf  ldc.i4.4
  ... truncated ...
```
