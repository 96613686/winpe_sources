# Microsoft.Crm.Asynchronous.ImportOperationImport::PollForImportJobsToComplete

- ea: `0xd7f0`
- end: `0xd8f0`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImport::PollForImportJobsToComplete`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xbe90`

## callees

- `0xbcb0`
- `0xd610`
- `0xd7f0`
- `0xd8f0`
- `0xd9f0`
- `0xdc50`

## pseudocode

```c

```

## disassembly

```asm
0xd7f0  ldarg.0
0xd7f1  ldfld    class Microsoft.Crm.Asynchronous.ImportSampleData Microsoft.Crm.Asynchronous.ImportOperationImport::_sampleDataOperation
0xd7f6  brfalse.s loc_D7FA
0xd7f8  ldnull
0xd7f9  ret
0xd7fa  ldnull
0xd7fb  stloc.0
0xd7fc  br.s     loc_D84C
0xd7fe  ldarg.0
0xd7ff  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperation::HasJobBeenAbortedOrPaused()
0xd804  stloc.0
0xd805  ldloc.0
0xd806  brtrue.s loc_D828
0xd808  ldarg.0
0xd809  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.ImportOperationImport::_JobsToBeResumed
0xd80e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0xd813  ldc.i4.0
0xd814  ble.s    loc_D81C
0xd816  ldarg.0
0xd817  call     instance void Microsoft.Crm.Asynchronous.ImportOperationImport::TryResumingLockedJobs()
0xd81c  ldc.i4   0x2710
0xd821  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0xd826  br.s     loc_D84C
0xd828  ldloc.0
0xd829  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult::get_ResultCode()
0xd82e  ldc.i4.s 0xA
0xd830  bne.un.s loc_D83A
0xd832  ldarg.0
0xd833  call     instance void Microsoft.Crm.Asynchronous.ImportOperationImport::PauseAllChildJobs()
0xd838  ldloc.0
0xd839  ret
0xd83a  ldloc.0
0xd83b  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult::get_ResultCode()
0xd840  ldc.i4.s 0x20
0xd842  bne.un.s loc_D84C
0xd844  ldarg.0
0xd845  call     instance void Microsoft.Crm.Asynchronous.ImportOperationImport::CancelAllChildJobs()
0xd84a  ldloc.0
0xd84b  ret
0xd84c  ldarg.0
0xd84d  ldarg.1
0xd84e  ldarg.2
0xd84f  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImport::AllJobsSubmittedTillNowHaveCompleted(valuetype [mscorlib]System.Guid importId, valuetype PassPhase passPhase)
0xd854  brfalse.s loc_D7FE
0xd856  ldarg.0
0xd857  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.ImportOperationImport::_failedJobs
0xd85c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0xd861  ldc.i4.0
0xd862  ble      loc_D8EE
0xd867  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xd86c  stloc.1
0xd86d  ldloc.1
0xd86e  ldarg.0
0xd86f  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.ImportOperationImport::_failedJobs
0xd874  ldc.i4.0
0xd875  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0xd87a  stloc.2
0xd87b  ldloca.s 2
0xd87d  ldstr    aD_0// "D"
0xd882  call     instance string [mscorlib]System.Guid::ToString(string)
0xd887  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd88c  pop
0xd88d  ldc.i4.1
0xd88e  stloc.3
0xd88f  br.s     loc_D8C1
0xd891  ldloc.1
0xd892  ldstr    asc_24112// ","
0xd897  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd89c  pop
0xd89d  ldloc.1
0xd89e  ldarg.0
0xd89f  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.ImportOperationImport::_failedJobs
0xd8a4  ldloc.3
0xd8a5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0xd8aa  stloc.2
0xd8ab  ldloca.s 2
0xd8ad  ldstr    aD_0// "D"
0xd8b2  call     instance string [mscorlib]System.Guid::ToString(string)
0xd8b7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd8bc  pop
0xd8bd  ldloc.3
0xd8be  ldc.i4.1
0xd8bf  add
0xd8c0  stloc.3
0xd8c1  ldloc.3
0xd8c2  ldarg.0
0xd8c3  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.ImportOperationImport::_failedJobs
0xd8c8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0xd8cd  blt.s    loc_D891
0xd8cf  ldc.i4   0x80044334
0xd8d4  ldstr    aImportChildJob_0// "Import Child Jobs with ids {0} Failed"
0xd8d9  ldc.i4.1
0xd8da  newarr   [mscorlib]System.Object
0xd8df  dup
0xd8e0  ldc.i4.0
0xd8e1  ldloc.1
0xd8e2  callvirt instance string [mscorlib]System.Object::ToString()
0xd8e7  stelem.ref
0xd8e8  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0xd8ed  ret
0xd8ee  ldnull
0xd8ef  ret
```
