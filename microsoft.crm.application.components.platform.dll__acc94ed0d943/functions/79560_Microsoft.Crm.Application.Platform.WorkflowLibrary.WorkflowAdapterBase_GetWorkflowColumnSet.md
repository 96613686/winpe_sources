# Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::GetWorkflowColumnSet

- ea: `0x79560`
- end: `0x7965b`
- name: `Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::GetWorkflowColumnSet`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x79520`
- `0x79df0`

## string_xrefs

- `0x795c4`: `triggeroncreate`
- `0x795cd`: `triggerondelete`
- `0x795d6`: `triggeronupdateattributelist`
- `0x795f1`: `asyncautodelete`
- `0x7960c`: `createstage`
- `0x79615`: `updatestage`
- `0x7961e`: `deletestage`

## pseudocode

```c

```

## disassembly

```asm
0x79560  ldc.i4.s 0x1C
0x79562  newarr   [mscorlib]System.String
0x79567  dup
0x79568  ldc.i4.0
0x79569  ldstr    aName// "name"
0x7956e  stelem.ref
0x7956f  dup
0x79570  ldc.i4.1
0x79571  ldstr    aDescription_0// "description"
0x79576  stelem.ref
0x79577  dup
0x79578  ldc.i4.2
0x79579  ldstr    aPrimaryentity// "primaryentity"
0x7957e  stelem.ref
0x7957f  dup
0x79580  ldc.i4.3
0x79581  ldstr    aDescription_0// "description"
0x79586  stelem.ref
0x79587  dup
0x79588  ldc.i4.4
0x79589  ldstr    aOndemand// "ondemand"
0x7958e  stelem.ref
0x7958f  dup
0x79590  ldc.i4.5
0x79591  ldstr    aSubprocess// "subprocess"
0x79596  stelem.ref
0x79597  dup
0x79598  ldc.i4.6
0x79599  ldstr    aType// "type"
0x7959e  stelem.ref
0x7959f  dup
0x795a0  ldc.i4.7
0x795a1  ldstr    aScope// "scope"
0x795a6  stelem.ref
0x795a7  dup
0x795a8  ldc.i4.8
0x795a9  ldstr    aIscrmuiworkflo// "iscrmuiworkflow"
0x795ae  stelem.ref
0x795af  dup
0x795b0  ldc.i4.s 9
0x795b2  ldstr    aXaml// "xaml"
0x795b7  stelem.ref
0x795b8  dup
0x795b9  ldc.i4.s 0xA
0x795bb  ldstr    aFormid// "formid"
0x795c0  stelem.ref
0x795c1  dup
0x795c2  ldc.i4.s 0xB
0x795c4  ldstr    aTriggeroncreat// "triggeroncreate"
0x795c9  stelem.ref
0x795ca  dup
0x795cb  ldc.i4.s 0xC
0x795cd  ldstr    aTriggerondelet// "triggerondelete"
0x795d2  stelem.ref
0x795d3  dup
0x795d4  ldc.i4.s 0xD
0x795d6  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x795db  stelem.ref
0x795dc  dup
0x795dd  ldc.i4.s 0xE
0x795df  ldstr    aCategory// "category"
0x795e4  stelem.ref
0x795e5  dup
0x795e6  ldc.i4.s 0xF
0x795e8  ldstr    aBusinessproces// "businessprocesstype"
0x795ed  stelem.ref
0x795ee  dup
0x795ef  ldc.i4.s 0x10
0x795f1  ldstr    aAsyncautodelet// "asyncautodelete"
0x795f6  stelem.ref
0x795f7  dup
0x795f8  ldc.i4.s 0x11
0x795fa  ldstr    aInputparameter// "inputparameters"
0x795ff  stelem.ref
0x79600  dup
0x79601  ldc.i4.s 0x12
0x79603  ldstr    aSyncworkflowlo// "syncworkflowlogonfailure"
0x79608  stelem.ref
0x79609  dup
0x7960a  ldc.i4.s 0x13
0x7960c  ldstr    aCreatestage// "createstage"
0x79611  stelem.ref
0x79612  dup
0x79613  ldc.i4.s 0x14
0x79615  ldstr    aUpdatestage// "updatestage"
0x7961a  stelem.ref
0x7961b  dup
0x7961c  ldc.i4.s 0x15
0x7961e  ldstr    aDeletestage// "deletestage"
0x79623  stelem.ref
0x79624  dup
0x79625  ldc.i4.s 0x16
0x79627  ldstr    aRunas// "runas"
0x7962c  stelem.ref
0x7962d  dup
0x7962e  ldc.i4.s 0x17
0x79630  ldstr    aUniquename// "uniquename"
0x79635  stelem.ref
0x79636  dup
0x79637  ldc.i4.s 0x18
0x79639  ldstr    aMode// "mode"
0x7963e  stelem.ref
0x7963f  dup
0x79640  ldc.i4.s 0x19
0x79642  ldstr    aSdkmessageid// "sdkmessageid"
0x79647  stelem.ref
0x79648  dup
0x79649  ldc.i4.s 0x1A
0x7964b  ldstr    aIstransacted// "istransacted"
0x79650  stelem.ref
0x79651  dup
0x79652  ldc.i4.s 0x1B
0x79654  ldstr    aRendererobject// "rendererobjecttypecode"
0x79659  stelem.ref
0x7965a  ret
```
