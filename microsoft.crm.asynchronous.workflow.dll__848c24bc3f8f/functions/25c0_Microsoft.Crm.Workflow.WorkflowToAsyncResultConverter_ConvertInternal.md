# Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::ConvertInternal

- ea: `0x25c0`
- end: `0x26fa`
- name: `Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::ConvertInternal`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x2590`

## callees

- `0x25c0`
- `0x2700`
- `0x2730`
- `0x2740`
- `0x2750`
- `0x2760`
- `0x2790`

## pseudocode

```c

```

## disassembly

```asm
0x25c0  ldarg.0
0x25c1  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x25c6  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationFailedResult
0x25cb  brfalse.s loc_25E4
0x25cd  ldarg.0
0x25ce  ldarg.0
0x25cf  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x25d4  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationFailedResult
0x25d9  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::Convert(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationFailedResult wfResult)
0x25de  stloc.0
0x25df  leave    loc_26F8
0x25e4  ldarg.0
0x25e5  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x25ea  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationCanceledResult
0x25ef  brfalse.s loc_2608
0x25f1  ldarg.0
0x25f2  ldarg.0
0x25f3  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x25f8  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationCanceledResult
0x25fd  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::Convert(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationCanceledResult wfResult)
0x2602  stloc.0
0x2603  leave    loc_26F8
0x2608  ldarg.0
0x2609  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x260e  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationSucceededResult
0x2613  brfalse.s loc_262C
0x2615  ldarg.0
0x2616  ldarg.0
0x2617  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x261c  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationSucceededResult
0x2621  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::Convert(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationSucceededResult wfResult)
0x2626  stloc.0
0x2627  leave    loc_26F8
0x262c  ldarg.0
0x262d  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x2632  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationPausedResult
0x2637  brfalse.s loc_2650
0x2639  ldarg.0
0x263a  ldarg.0
0x263b  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x2640  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationPausedResult
0x2645  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::Convert(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationPausedResult wfResult)
0x264a  stloc.0
0x264b  leave    loc_26F8
0x2650  ldarg.0
0x2651  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x2656  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowSystemPausedResult
0x265b  brfalse.s loc_2674
0x265d  ldarg.0
0x265e  ldarg.0
0x265f  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x2664  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowSystemPausedResult
0x2669  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSystemPausedResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::Convert(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowSystemPausedResult wfResult)
0x266e  stloc.0
0x266f  leave    loc_26F8
0x2674  ldarg.0
0x2675  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x267a  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationInProgressResult
0x267f  brfalse.s loc_2689
0x2681  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncInProgressResult::.ctor()
0x2686  stloc.0
0x2687  leave.s  loc_26F8
0x2689  ldarg.0
0x268a  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x268f  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationRetryResult
0x2694  brfalse.s loc_26AA
0x2696  ldarg.0
0x2697  ldarg.0
0x2698  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x269d  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationRetryResult
0x26a2  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRetryResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::Convert(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationRetryResult wfResult)
0x26a7  stloc.0
0x26a8  leave.s  loc_26F8
0x26aa  ldarg.0
0x26ab  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x26b0  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRemoveEventResult
0x26b5  brfalse.s loc_26C5
0x26b7  ldarg.0
0x26b8  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x26bd  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRemoveEventResult
0x26c2  stloc.0
0x26c3  leave.s  loc_26F8
0x26c5  ldarg.0
0x26c6  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x26cb  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult
0x26d0  brfalse.s loc_26E0
0x26d2  ldarg.0
0x26d3  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x26d8  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult
0x26dd  stloc.0
0x26de  leave.s  loc_26F8
0x26e0  ldstr    aAsynchronousWo// "Asynchronous Workflow runtime does not "...
0x26e5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x26ea  throw
0x26eb  stloc.1
0x26ec  ldstr    aInvalidTypeCon// "Invalid type conversion."
0x26f1  ldloc.1
0x26f2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string, class [mscorlib]System.Exception)
0x26f7  throw
0x26f8  ldloc.0
0x26f9  ret
```
