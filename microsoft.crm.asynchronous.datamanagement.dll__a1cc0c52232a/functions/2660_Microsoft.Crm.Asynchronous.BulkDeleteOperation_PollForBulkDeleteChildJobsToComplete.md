# Microsoft.Crm.Asynchronous.BulkDeleteOperation::PollForBulkDeleteChildJobsToComplete

- ea: `0x2660`
- end: `0x275c`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::PollForBulkDeleteChildJobsToComplete`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1f350`

## callees

- `0x2150`
- `0x23d0`
- `0x2660`
- `0x2760`
- `0x2a70`

## pseudocode

```c

```

## disassembly

```asm
0x2660  br.s     loc_26A2
0x2662  ldarg.0
0x2663  ldarg.0
0x2664  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.BulkDeleteOperation::_asyncEvent
0x2669  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.BulkDeleteOperation::HasJobBeenAbortedOrPaused(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0x266e  stloc.0
0x266f  ldloc.0
0x2670  brtrue.s loc_267E
0x2672  ldc.i4   0x2710
0x2677  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x267c  br.s     loc_26A2
0x267e  ldloc.0
0x267f  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult::get_ResultCode()
0x2684  ldc.i4.s 0xA
0x2686  bne.un.s loc_2690
0x2688  ldarg.0
0x2689  call     instance void Microsoft.Crm.Asynchronous.BulkDeleteOperation::PauseAllChildJobs()
0x268e  ldloc.0
0x268f  ret
0x2690  ldloc.0
0x2691  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult::get_ResultCode()
0x2696  ldc.i4.s 0x20
0x2698  bne.un.s loc_26A2
0x269a  ldarg.0
0x269b  call     instance void Microsoft.Crm.Asynchronous.BulkDeleteOperation::CancelAllChildJobs()
0x26a0  ldloc.0
0x26a1  ret
0x26a2  ldarg.0
0x26a3  call     instance bool Microsoft.Crm.Asynchronous.BulkDeleteOperation::AllJobsSubmittedTillNowHaveCompleted()
0x26a8  brfalse.s loc_2662
0x26aa  ldarg.0
0x26ab  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_failedJobs
0x26b0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x26b5  ldc.i4.0
0x26b6  ble      loc_2742
0x26bb  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x26c0  stloc.1
0x26c1  ldloc.1
0x26c2  ldarg.0
0x26c3  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_failedJobs
0x26c8  ldc.i4.0
0x26c9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0x26ce  stloc.2
0x26cf  ldloca.s 2
0x26d1  ldstr    aD_0// "D"
0x26d6  call     instance string [mscorlib]System.Guid::ToString(string)
0x26db  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x26e0  pop
0x26e1  ldc.i4.1
0x26e2  stloc.3
0x26e3  br.s     loc_2715
0x26e5  ldloc.1
0x26e6  ldstr    asc_24112// ","
0x26eb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x26f0  pop
0x26f1  ldloc.1
0x26f2  ldarg.0
0x26f3  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_failedJobs
0x26f8  ldloc.3
0x26f9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0x26fe  stloc.2
0x26ff  ldloca.s 2
0x2701  ldstr    aD_0// "D"
0x2706  call     instance string [mscorlib]System.Guid::ToString(string)
0x270b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2710  pop
0x2711  ldloc.3
0x2712  ldc.i4.1
0x2713  add
0x2714  stloc.3
0x2715  ldloc.3
0x2716  ldarg.0
0x2717  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_failedJobs
0x271c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x2721  blt.s    loc_26E5
0x2723  ldc.i4   0x80048459
0x2728  ldstr    aJobsWithIds0Fa// "Jobs with Ids {0} failed"
0x272d  ldc.i4.1
0x272e  newarr   [mscorlib]System.Object
0x2733  dup
0x2734  ldc.i4.0
0x2735  ldloc.1
0x2736  callvirt instance string [mscorlib]System.Object::ToString()
0x273b  stelem.ref
0x273c  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0x2741  ret
0x2742  ldarg.0
0x2743  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_cancelledJobs
0x2748  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x274d  ldc.i4.0
0x274e  ble.s    loc_2756
0x2750  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult::.ctor()
0x2755  ret
0x2756  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x275b  ret
```
