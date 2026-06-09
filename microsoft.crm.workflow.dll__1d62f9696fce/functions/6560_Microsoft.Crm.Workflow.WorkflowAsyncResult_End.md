# Microsoft.Crm.Workflow.WorkflowAsyncResult::End

- ea: `0x6560`
- end: `0x660c`
- name: `Microsoft.Crm.Workflow.WorkflowAsyncResult::End`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6360`
- `0x6560`

## string_xrefs

- `0x659f`: `AsyncResult already ended`

## pseudocode

```c

```

## disassembly

```asm
0x6560  ldarg.0
0x6561  brtrue.s loc_656E
0x6563  ldstr    aResult// "result"
0x6568  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x656d  throw
0x656e  ldarg.0
0x656f  isinst   mvar<u1>
0x6574  unbox.any mvar<u1>
0x6579  stloc.0
0x657a  ldloc.0
0x657b  box      mvar<u1>
0x6580  brtrue.s loc_6592
0x6582  ldstr    aInvalidAsyncre// "Invalid AsyncResult"
0x6587  ldstr    aResult// "result"
0x658c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x6591  throw
0x6592  ldloc.0
0x6593  box      mvar<u1>
0x6598  ldfld    bool Microsoft.Crm.Workflow.WorkflowAsyncResult::_endCalled
0x659d  brfalse.s loc_65AA
0x659f  ldstr    aAsyncresultAlr// "AsyncResult already ended"
0x65a4  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x65a9  throw
0x65aa  ldloc.0
0x65ab  box      mvar<u1>
0x65b0  ldc.i4.1
0x65b1  stfld    bool Microsoft.Crm.Workflow.WorkflowAsyncResult::_endCalled
0x65b6  ldloc.0
0x65b7  box      mvar<u1>
0x65bc  ldfld    bool Microsoft.Crm.Workflow.WorkflowAsyncResult::_isCompleted
0x65c1  brtrue.s loc_65D4
0x65c3  ldloc.0
0x65c4  box      mvar<u1>
0x65c9  callvirt instance class [mscorlib]System.Threading.WaitHandle Microsoft.Crm.Workflow.WorkflowAsyncResult::get_AsyncWaitHandle()
0x65ce  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x65d3  pop
0x65d4  ldloc.0
0x65d5  box      mvar<u1>
0x65da  ldfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.Workflow.WorkflowAsyncResult::_manualResetEvent
0x65df  brfalse.s loc_65F1
0x65e1  ldloc.0
0x65e2  box      mvar<u1>
0x65e7  ldfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.Workflow.WorkflowAsyncResult::_manualResetEvent
0x65ec  callvirt instance void [mscorlib]System.Threading.WaitHandle::Close()
0x65f1  ldloc.0
0x65f2  box      mvar<u1>
0x65f7  ldfld    class [mscorlib]System.Exception Microsoft.Crm.Workflow.WorkflowAsyncResult::_exception
0x65fc  brfalse.s loc_660A
0x65fe  ldloc.0
0x65ff  box      mvar<u1>
0x6604  ldfld    class [mscorlib]System.Exception Microsoft.Crm.Workflow.WorkflowAsyncResult::_exception
0x6609  throw
0x660a  ldloc.0
0x660b  ret
```
