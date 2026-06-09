# Microsoft.Crm.Workflow.ObjectModel.NullObjectsFactory::BuildStep

- ea: `0x2c300`
- end: `0x2c991`
- name: `Microsoft.Crm.Workflow.ObjectModel.NullObjectsFactory::BuildStep`
- size: `1681`
- prototype: ``
- caller_count: `0`
- callee_count: `41`
- tags: `installer_update, broker_com_uri`

## callees

- `0x290e0`
- `0x29ae0`
- `0x29c00`
- `0x29f40`
- `0x2a260`
- `0x2a660`
- `0x2ace0`
- `0x2ae80`
- `0x2b280`
- `0x2b6a0`
- `0x2c300`
- `0x2cbd0`
- `0x2d0e0`
- `0x2d750`
- `0x2e0b0`
- `0x2e3f0`
- `0x2f210`
- `0x2f800`
- `0x2fd40`
- `0x304f0`
- `0x30910`
- `0x313e0`
- `0x31750`
- `0x31f60`
- `0x34130`
- `0x34400`
- `0x34770`
- `0x34fb0`
- `0x35090`
- `0x35380`
- `0x35750`
- `0x35990`
- `0x37620`
- `0x38120`
- `0x38270`
- `0x3b080`
- `0x3b270`
- `0x3b5f0`
- `0x3b820`
- `0x3db40`
- `0x4f590`

## string_xrefs

- `0x2c6f2`: `CreateStep:#Microsoft.Crm.Workflow.ObjectModel`
- `0x2c71c`: `UpdateStep:#Microsoft.Crm.Workflow.ObjectModel`

## pseudocode

```c

```

## disassembly

```asm
0x2c300  ldstr    aAccount// "account"
0x2c305  ldc.i4.0
0x2c306  newobj   instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::.ctor(string primaryEntityName, int32 category)
0x2c30b  stloc.0
0x2c30c  ldarg.0
0x2c30d  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x2c312  stloc.1
0x2c313  ldloc.1
0x2c314  ldc.i4   0x7C9761F1
0x2c319  bgt.un   loc_2C43C
0x2c31e  ldloc.1
0x2c31f  ldc.i4   0x2FCBDCF4
0x2c324  bgt.un   loc_2C3AD
0x2c329  ldloc.1
0x2c32a  ldc.i4   0x23AC8587
0x2c32f  bgt.un.s loc_2C36F
0x2c331  ldloc.1
0x2c332  ldc.i4   0x16D82BE6
0x2c337  bgt.un.s loc_2C354
0x2c339  ldloc.1
0x2c33a  ldc.i4   0xDBC04B2
0x2c33f  beq      loc_2C7ED
0x2c344  ldloc.1
0x2c345  ldc.i4   0x16D82BE6
0x2c34a  beq      loc_2C730
0x2c34f  br       loc_2C98F
0x2c354  ldloc.1
0x2c355  ldc.i4   0x1BB8B32D
0x2c35a  beq      loc_2C7C3
0x2c35f  ldloc.1
0x2c360  ldc.i4   0x23AC8587
0x2c365  beq      loc_2C75A
0x2c36a  br       loc_2C98F
0x2c36f  ldloc.1
0x2c370  ldc.i4   0x285D33BA
0x2c375  bgt.un.s loc_2C392
0x2c377  ldloc.1
0x2c378  ldc.i4   0x259E7354
0x2c37d  beq      loc_2C802
0x2c382  ldloc.1
0x2c383  ldc.i4   0x285D33BA
0x2c388  beq      loc_2C784
0x2c38d  br       loc_2C98F
0x2c392  ldloc.1
0x2c393  ldc.i4   0x295B937D
0x2c398  beq      loc_2C82C
0x2c39d  ldloc.1
0x2c39e  ldc.i4   0x2FCBDCF4
0x2c3a3  beq      loc_2C5F5
0x2c3a8  br       loc_2C98F
0x2c3ad  ldloc.1
0x2c3ae  ldc.i4   0x6C2BB130
0x2c3b3  bgt.un.s loc_2C3F3
0x2c3b5  ldloc.1
0x2c3b6  ldc.i4   0x53BFABAD
0x2c3bb  bgt.un.s loc_2C3D8
0x2c3bd  ldloc.1
0x2c3be  ldc.i4   0x4F1C5377
0x2c3c3  beq      loc_2C60A
0x2c3c8  ldloc.1
0x2c3c9  ldc.i4   0x53BFABAD
0x2c3ce  beq      loc_2C6B2
0x2c3d3  br       loc_2C98F
0x2c3d8  ldloc.1
0x2c3d9  ldc.i4   0x579FE30E
0x2c3de  beq      loc_2C76F
0x2c3e3  ldloc.1
0x2c3e4  ldc.i4   0x6C2BB130
0x2c3e9  beq      loc_2C577
0x2c3ee  br       loc_2C98F
0x2c3f3  ldloc.1
0x2c3f4  ldc.i4   0x7759FD15
0x2c3f9  bgt.un.s loc_2C416
0x2c3fb  ldloc.1
0x2c3fc  ldc.i4   0x74FBF59F
0x2c401  beq      loc_2C58C
0x2c406  ldloc.1
0x2c407  ldc.i4   0x7759FD15
0x2c40c  beq      loc_2C6C7
0x2c411  br       loc_2C98F
0x2c416  ldloc.1
0x2c417  ldc.i4   0x78AFFBA1
0x2c41c  beq      loc_2C649
0x2c421  ldloc.1
0x2c422  ldc.i4   0x79D06860
0x2c427  beq      loc_2C5B6
0x2c42c  ldloc.1
0x2c42d  ldc.i4   0x7C9761F1
0x2c432  beq      loc_2C69D
0x2c437  br       loc_2C98F
0x2c43c  ldloc.1
0x2c43d  ldc.i4   0xAE2E80E5
0x2c442  bgt.un   loc_2C4D6
0x2c447  ldloc.1
0x2c448  ldc.i4   0x873DE3A0
0x2c44d  bgt.un.s loc_2C48D
0x2c44f  ldloc.1
0x2c450  ldc.i4   0x7D505DD8
0x2c455  bgt.un.s loc_2C472
0x2c457  ldloc.1
0x2c458  ldc.i4   0x7D4AF069
0x2c45d  beq      loc_2C5A1
0x2c462  ldloc.1
0x2c463  ldc.i4   0x7D505DD8
0x2c468  beq      loc_2C688
0x2c46d  br       loc_2C98F
0x2c472  ldloc.1
0x2c473  ldc.i4   0x8563DA27
0x2c478  beq      loc_2C6F1
0x2c47d  ldloc.1
0x2c47e  ldc.i4   0x873DE3A0
0x2c483  beq      loc_2C562
0x2c488  br       loc_2C98F
0x2c48d  ldloc.1
0x2c48e  ldc.i4   0x8A7A3472
0x2c493  bgt.un.s loc_2C4B0
0x2c495  ldloc.1
0x2c496  ldc.i4   0x879B0EC4
0x2c49b  beq      loc_2C65E
0x2c4a0  ldloc.1
0x2c4a1  ldc.i4   0x8A7A3472
0x2c4a6  beq      loc_2C745
0x2c4ab  br       loc_2C98F
0x2c4b0  ldloc.1
0x2c4b1  ldc.i4   0x9E48B14D
0x2c4b6  beq      loc_2C706
0x2c4bb  ldloc.1
0x2c4bc  ldc.i4   0xA55DF8B7
0x2c4c1  beq      loc_2C6DC
0x2c4c6  ldloc.1
0x2c4c7  ldc.i4   0xAE2E80E5
0x2c4cc  beq      loc_2C7D8
0x2c4d1  br       loc_2C98F
0x2c4d6  ldloc.1
0x2c4d7  ldc.i4   0xBB15BD1E
0x2c4dc  bgt.un.s loc_2C51C
0x2c4de  ldloc.1
0x2c4df  ldc.i4   0xB19BBDB2
0x2c4e4  bgt.un.s loc_2C501
0x2c4e6  ldloc.1
0x2c4e7  ldc.i4   0xAF156FB6
0x2c4ec  beq      loc_2C5E0
0x2c4f1  ldloc.1
0x2c4f2  ldc.i4   0xB19BBDB2
0x2c4f7  beq      loc_2C7AE
0x2c4fc  br       loc_2C98F
0x2c501  ldloc.1
0x2c502  ldc.i4   0xB9578B00
0x2c507  beq      loc_2C634
0x2c50c  ldloc.1
0x2c50d  ldc.i4   0xBB15BD1E
0x2c512  beq      loc_2C817
0x2c517  br       loc_2C98F
0x2c51c  ldloc.1
0x2c51d  ldc.i4   0xC4040237
0x2c522  bgt.un.s loc_2C53F
0x2c524  ldloc.1
0x2c525  ldc.i4   0xBEBBC2C2
0x2c52a  beq      loc_2C799
0x2c52f  ldloc.1
0x2c530  ldc.i4   0xC4040237
0x2c535  beq      loc_2C673
0x2c53a  br       loc_2C98F
0x2c53f  ldloc.1
0x2c540  ldc.i4   0xD1A9D08E
0x2c545  beq      loc_2C71B
0x2c54a  ldloc.1
0x2c54b  ldc.i4   0xF7954CEE
0x2c550  beq      loc_2C61F
0x2c555  ldloc.1
0x2c556  ldc.i4   0xF863D3B8
0x2c55b  beq.s    loc_2C5CB
0x2c55d  br       loc_2C98F
0x2c562  ldarg.0
0x2c563  ldstr    aConditionstepM// "ConditionStep:#Microsoft.Crm.Workflow.O"...
0x2c568  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c56d  brtrue   loc_2C841
0x2c572  br       loc_2C98F
0x2c577  ldarg.0
0x2c578  ldstr    aConditionbranc// "ConditionBranchStep:#Microsoft.Crm.Work"...
0x2c57d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c582  brtrue   loc_2C848
0x2c587  br       loc_2C98F
0x2c58c  ldarg.0
0x2c58d  ldstr    aCustomjavascri// "CustomJavascriptStep:#Microsoft.Crm.Wor"...
0x2c592  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c597  brtrue   loc_2C85C
0x2c59c  br       loc_2C98F
0x2c5a1  ldarg.0
0x2c5a2  ldstr    aSetvisibilitys// "SetVisibilityStep:#Microsoft.Crm.Workfl"...
0x2c5a7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c5ac  brtrue   loc_2C863
0x2c5b1  br       loc_2C98F
0x2c5b6  ldarg.0
0x2c5b7  ldstr    aSetfieldrequir// "SetFieldRequiredLevelStep:#Microsoft.Cr"...
0x2c5bc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c5c1  brtrue   loc_2C86A
0x2c5c6  br       loc_2C98F
0x2c5cb  ldarg.0
0x2c5cc  ldstr    aSetattributeva// "SetAttributeValueStep:#Microsoft.Crm.Wo"...
0x2c5d1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c5d6  brtrue   loc_2C871
0x2c5db  br       loc_2C98F
0x2c5e0  ldarg.0
0x2c5e1  ldstr    aSetdisplaymode// "SetDisplayModeStep:#Microsoft.Crm.Workf"...
0x2c5e6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c5eb  brtrue   loc_2C879
0x2c5f0  br       loc_2C98F
0x2c5f5  ldarg.0
0x2c5f6  ldstr    aSetmessagestep// "SetMessageStep:#Microsoft.Crm.Workflow."...
0x2c5fb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c600  brtrue   loc_2C880
0x2c605  br       loc_2C98F
0x2c60a  ldarg.0
0x2c60b  ldstr    aSetdefaultvalu// "SetDefaultValueStep:#Microsoft.Crm.Work"...
0x2c610  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c615  brtrue   loc_2C887
0x2c61a  br       loc_2C98F
0x2c61f  ldarg.0
0x2c620  ldstr    aSetnextstagest// "SetNextStageStep:#Microsoft.Crm.Workflo"...
0x2c625  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c62a  brtrue   loc_2C88F
0x2c62f  br       loc_2C98F
0x2c634  ldarg.0
0x2c635  ldstr    aControlstepMic// "ControlStep:#Microsoft.Crm.Workflow.Obj"...
0x2c63a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c63f  brtrue   loc_2C896
0x2c644  br       loc_2C98F
0x2c649  ldarg.0
0x2c64a  ldstr    aActionstepMicr// "ActionStep:#Microsoft.Crm.Workflow.Obje"...
0x2c64f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c654  brtrue   loc_2C89D
0x2c659  br       loc_2C98F
0x2c65e  ldarg.0
0x2c65f  ldstr    aEntitystepMicr// "EntityStep:#Microsoft.Crm.Workflow.Obje"...
0x2c664  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c669  brtrue   loc_2C8A4
0x2c66e  br       loc_2C98F
0x2c673  ldarg.0
0x2c674  ldstr    aStagestepMicro// "StageStep:#Microsoft.Crm.Workflow.Objec"...
0x2c679  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c67e  brtrue   loc_2C8B0
0x2c683  br       loc_2C98F
0x2c688  ldarg.0
0x2c689  ldstr    aPagestepMicros// "PageStep:#Microsoft.Crm.Workflow.Object"...
0x2c68e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c693  brtrue   loc_2C8BC
0x2c698  br       loc_2C98F
0x2c69d  ldarg.0
0x2c69e  ldstr    aStepstepMicros// "StepStep:#Microsoft.Crm.Workflow.Object"...
0x2c6a3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c6a8  brtrue   loc_2C8C8
0x2c6ad  br       loc_2C98F
0x2c6b2  ldarg.0
0x2c6b3  ldstr    aRelationshipco// "RelationshipCollectionStep:#Microsoft.C"...
0x2c6b8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c6bd  brtrue   loc_2C8D4
0x2c6c2  br       loc_2C98F
0x2c6c7  ldarg.0
0x2c6c8  ldstr    aRelationshipst// "RelationshipStep:#Microsoft.Crm.Workflo"...
0x2c6cd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c6d2  brtrue   loc_2C8DB
0x2c6d7  br       loc_2C98F
0x2c6dc  ldarg.0
0x2c6dd  ldstr    aRolluprulestep// "RollupRuleStep:#Microsoft.Crm.Workflow."...
0x2c6e2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c6e7  brtrue   loc_2C8E2
0x2c6ec  br       loc_2C98F
0x2c6f1  ldarg.0
0x2c6f2  ldstr    aCreatestepMicr// "CreateStep:#Microsoft.Crm.Workflow.Obje"...
0x2c6f7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c6fc  brtrue   loc_2C8E9
0x2c701  br       loc_2C98F
0x2c706  ldarg.0
0x2c707  ldstr    aCustomactivity// "CustomActivityStep:#Microsoft.Crm.Workf"...
0x2c70c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c711  brtrue   loc_2C8F0
0x2c716  br       loc_2C98F
0x2c71b  ldarg.0
0x2c71c  ldstr    aUpdatestepMicr// "UpdateStep:#Microsoft.Crm.Workflow.Obje"...
0x2c721  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c726  brtrue   loc_2C909
0x2c72b  br       loc_2C98F
0x2c730  ldarg.0
0x2c731  ldstr    aAssignstepMicr// "AssignStep:#Microsoft.Crm.Workflow.Obje"...
0x2c736  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c73b  brtrue   loc_2C910
0x2c740  br       loc_2C98F
0x2c745  ldarg.0
0x2c746  ldstr    aChildworkflows// "ChildWorkflowStep:#Microsoft.Crm.Workfl"...
0x2c74b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c750  brtrue   loc_2C917
0x2c755  br       loc_2C98F
0x2c75a  ldarg.0
0x2c75b  ldstr    aSendemailstepM// "SendEmailStep:#Microsoft.Crm.Workflow.O"...
0x2c760  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c765  brtrue   loc_2C91E
0x2c76a  br       loc_2C98F
0x2c76f  ldarg.0
0x2c770  ldstr    aSetstatestepMi// "SetStateStep:#Microsoft.Crm.Workflow.Ob"...
  ... truncated ...
```
