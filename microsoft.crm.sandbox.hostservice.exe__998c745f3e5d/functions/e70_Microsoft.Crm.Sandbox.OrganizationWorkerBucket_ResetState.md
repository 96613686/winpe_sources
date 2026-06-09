# Microsoft.Crm.Sandbox.OrganizationWorkerBucket::ResetState

- ea: `0xe70`
- end: `0xec9`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerBucket::ResetState`
- size: `89`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xc20`
- `0x1190`
- `0x1870`
- `0x2040`
- `0x24c0`

## callees

- `0xc60`
- `0xc70`
- `0xc80`
- `0xe40`

## string_xrefs

- `0xe77`: `OrganizationWorkerBucket.ResetState:Thread[{0:d4}] Calling ResetState. Current State is {1}`

## pseudocode

```c

```

## disassembly

```asm
0xe70  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe75  ldc.i4.s 0x21
0xe77  ldstr    aOrganizationwo// "OrganizationWorkerBucket.ResetState:Thr"...
0xe7c  ldc.i4.2
0xe7d  newarr   [mscorlib]System.Object
0xe82  dup
0xe83  ldc.i4.0
0xe84  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xe89  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xe8e  box      [mscorlib]System.Int32
0xe93  stelem.ref
0xe94  dup
0xe95  ldc.i4.1
0xe96  ldarg.0
0xe97  call     instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0xe9c  box      Microsoft.Crm.Sandbox.BucketState
0xea1  stelem.ref
0xea2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xea7  ldarg.0
0xea8  ldnull
0xea9  call     instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::set_WorkerProcess(class Microsoft.Crm.Sandbox.SandboxWorkerProcess value)
0xeae  ldarg.0
0xeaf  ldc.i4.0
0xeb0  stfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerBucket::EnqueuedCount
0xeb5  ldarg.0
0xeb6  ldc.i4.0
0xeb7  call     instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::set_State(valuetype Microsoft.Crm.Sandbox.BucketState value)
0xebc  ldarg.0
0xebd  ldc.i4.0
0xebe  newobj   instance void [mscorlib]System.Threading.AutoResetEvent::.ctor(bool)
0xec3  call     instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::set_EnqueueSyncronization(class [mscorlib]System.Threading.AutoResetEvent value)
0xec8  ret
```
