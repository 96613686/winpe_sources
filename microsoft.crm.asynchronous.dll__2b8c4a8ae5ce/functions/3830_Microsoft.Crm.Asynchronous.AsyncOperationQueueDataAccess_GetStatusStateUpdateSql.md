# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetStatusStateUpdateSql

- ea: `0x3830`
- end: `0x395a`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetStatusStateUpdateSql`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3960`

## callees

- `0x3830`

## string_xrefs

- `0x3837`: `update AsyncOperationBase `
- `0x38c5`: `, CompletedOn = @modifiedOn`
- `0x391d`: `, ModifiedBy = CreatedBy`

## pseudocode

```c

```

## disassembly

```asm
0x3830  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3835  stloc.0
0x3836  ldloc.0
0x3837  ldstr    aUpdateAsyncope_1// "update AsyncOperationBase "
0x383c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3841  pop
0x3842  ldloc.0
0x3843  ldstr    aSet// "set "
0x3848  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x384d  pop
0x384e  ldloc.0
0x384f  ldstr    aStatecodeNewst// "StateCode = @newState"
0x3854  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3859  pop
0x385a  ldloc.0
0x385b  ldstr    aStatuscodeNews// ", StatusCode = @newStatus"
0x3860  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3865  pop
0x3866  ldloc.0
0x3867  ldstr    aErrorcodeError// ", ErrorCode = @errorCode"
0x386c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3871  pop
0x3872  ldloc.0
0x3873  ldstr    aMessageErrorme// ", Message = @errorMessage"
0x3878  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x387d  pop
0x387e  ldarg.s  5
0x3880  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3885  brtrue.s loc_3895
0x3887  ldloc.0
0x3888  ldstr    aFriendlymessag// ", FriendlyMessage = @friendlyMessage"
0x388d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3892  pop
0x3893  br.s     loc_38A7
0x3895  ldarg.s  4
0x3897  ldc.i4.s 0x20
0x3899  beq.s    loc_38A7
0x389b  ldloc.0
0x389c  ldstr    aFriendlymessag_0// ", FriendlyMessage = NULL"
0x38a1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x38a6  pop
0x38a7  ldarg.2
0x38a8  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x38ad  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x38b2  brfalse.s loc_38C0
0x38b4  ldloc.0
0x38b5  ldstr    aPostponeuntilP// ", PostponeUntil = @postponeUntil"
0x38ba  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x38bf  pop
0x38c0  ldarg.1
0x38c1  ldc.i4.3
0x38c2  bne.un.s loc_38E8
0x38c4  ldloc.0
0x38c5  ldstr    aCompletedonMod// ", CompletedOn = @modifiedOn"
0x38ca  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x38cf  pop
0x38d0  ldloc.0
0x38d1  ldstr    aWorkflowstateN// ", WorkflowState = NULL"
0x38d6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x38db  pop
0x38dc  ldloc.0
0x38dd  ldstr    aWorkflowisbloc// ", WorkflowIsBlocked = NULL"
0x38e2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x38e7  pop
0x38e8  ldarg.3
0x38e9  brfalse.s loc_38F7
0x38eb  ldloc.0
0x38ec  ldstr    aDataNull// ", Data = NULL"
0x38f1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x38f6  pop
0x38f7  ldarg.s  6
0x38f9  ldc.r8   0.0
0x3902  ble.un.s loc_3910
0x3904  ldloc.0
0x3905  ldstr    aExecutiontimes// ", ExecutionTimeSpan =  @executionTimeSp"...
0x390a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x390f  pop
0x3910  ldloc.0
0x3911  ldstr    aModifiedonModi// ", ModifiedOn = @modifiedOn"
0x3916  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x391b  pop
0x391c  ldloc.0
0x391d  ldstr    aModifiedbyCrea// ", ModifiedBy = CreatedBy"
0x3922  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3927  pop
0x3928  ldloc.0
0x3929  ldstr    aWhereAsyncoper_0// " where AsyncOperationId = @id"
0x392e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3933  pop
0x3934  ldarg.s  7
0x3936  brfalse.s loc_3953
0x3938  ldc.i4.3
0x3939  stloc.1
0x393a  ldstr    aAndStatecode// " and StateCode <> "
0x393f  ldloc.1
0x3940  box      [mscorlib]System.Int32
0x3945  call     string [mscorlib]System.String::Concat(object, object)
0x394a  stloc.2
0x394b  ldloc.0
0x394c  ldloc.2
0x394d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3952  pop
0x3953  ldloc.0
0x3954  callvirt instance string [mscorlib]System.Object::ToString()
0x3959  ret
```
