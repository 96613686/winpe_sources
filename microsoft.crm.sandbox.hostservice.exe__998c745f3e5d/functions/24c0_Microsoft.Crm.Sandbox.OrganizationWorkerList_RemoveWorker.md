# Microsoft.Crm.Sandbox.OrganizationWorkerList::RemoveWorker

- ea: `0x24c0`
- end: `0x2553`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::RemoveWorker`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x8620`

## callees

- `0xc50`
- `0xe50`
- `0xe70`
- `0x24c0`
- `0x9720`
- `0x9770`

## string_xrefs

- `0x250a`: `OrganizationWorkerList.RemoveWorker: Resetting bucket {0} with this worker process FullId: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x24c0  ldarg.1
0x24c1  brfalse  loc_2552
0x24c6  ldarg.0
0x24c7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x24cc  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::GetEnumerator()
0x24d1  stloc.0
0x24d2  br.s     loc_2539
0x24d4  ldloca.s 0
0x24d6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Current()
0x24db  stloc.1
0x24dc  ldloc.1
0x24dd  brfalse.s loc_2539
0x24df  ldloc.1
0x24e0  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerProcess Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_WorkerProcess()
0x24e5  brfalse.s loc_2539
0x24e7  ldloc.1
0x24e8  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerProcess Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_WorkerProcess()
0x24ed  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0x24f2  ldarg.1
0x24f3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0x24f8  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x24fd  brfalse.s loc_2539
0x24ff  ldnull
0x2500  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2505  ldc.i4.3
0x2506  ldc.i4.s 0x26
0x2508  ldc.i4.0
0x2509  ldc.i4.1
0x250a  ldstr    aOrganizationwo_44// "OrganizationWorkerList.RemoveWorker: Re"...
0x250f  ldc.i4.2
0x2510  newarr   [mscorlib]System.Object
0x2515  dup
0x2516  ldc.i4.0
0x2517  ldloc.1
0x2518  callvirt instance int32 Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_Id()
0x251d  box      [mscorlib]System.Int32
0x2522  stelem.ref
0x2523  dup
0x2524  ldc.i4.1
0x2525  ldarg.1
0x2526  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0x252b  stelem.ref
0x252c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x2531  ldloc.1
0x2532  callvirt instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::ResetState()
0x2537  leave.s  loc_2552
0x2539  ldloca.s 0
0x253b  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::MoveNext()
0x2540  brtrue.s loc_24D4
0x2542  leave.s  loc_2552
0x2544  ldloca.s 0
0x2546  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>
0x254c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2551  endfinally
0x2552  ret
```
