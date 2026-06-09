# Microsoft.Crm.Workflow.Services.ActivityServiceBase::TryAcquireLockWithRetry

- ea: `0x14ba0`
- end: `0x14c2a`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::TryAcquireLockWithRetry`
- size: `138`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e7c0`
- `0x2efa0`
- `0x2f000`
- `0x2f0e0`
- `0x2f190`

## callees

- `0xef50`
- `0x14770`
- `0x14ba0`
- `0x14c30`

## string_xrefs

- `0x14bd1`: `Did not acquire lock for {0}:{1}, [attempt {2}].`

## pseudocode

```c

```

## disassembly

```asm
0x14ba0  ldarg.0
0x14ba1  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x14ba6  call     bool Microsoft.Crm.Workflow.Utility.WorkflowUtility::IsAsyncWorkflow(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.IWorkflowContext context)
0x14bab  brtrue.s loc_14BAF
0x14bad  ldnull
0x14bae  ret
0x14baf  ldnull
0x14bb0  stloc.0
0x14bb1  ldc.i4.s 0xF
0x14bb3  stloc.1
0x14bb4  br.s     loc_14C04
0x14bb6  ldarg.0
0x14bb7  ldarg.1
0x14bb8  ldarg.2
0x14bb9  ldloca.s 0
0x14bbb  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::TryAcquireLock(string entityLogicalName, valuetype [mscorlib]System.Guid entityId, [out] class [Microsoft.Crm.Core]Microsoft.Crm.LockHandle& lockHandle)
0x14bc0  brfalse.s loc_14BC4
0x14bc2  ldloc.0
0x14bc3  ret
0x14bc4  ldarg.0
0x14bc5  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x14bca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x14bcf  ldc.i4.s 0x1E
0x14bd1  ldstr    aDidNotAcquireL// "Did not acquire lock for {0}:{1}, [atte"...
0x14bd6  ldc.i4.3
0x14bd7  newarr   [mscorlib]System.Object
0x14bdc  dup
0x14bdd  ldc.i4.0
0x14bde  ldarg.1
0x14bdf  stelem.ref
0x14be0  dup
0x14be1  ldc.i4.1
0x14be2  ldarg.2
0x14be3  box      [mscorlib]System.Guid
0x14be8  stelem.ref
0x14be9  dup
0x14bea  ldc.i4.2
0x14beb  ldc.i4.s 0xA
0x14bed  ldloc.1
0x14bee  sub
0x14bef  box      [mscorlib]System.Int32
0x14bf4  stelem.ref
0x14bf5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14bfa  ldc.i4   0xFA
0x14bff  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x14c04  ldloc.1
0x14c05  dup
0x14c06  ldc.i4.1
0x14c07  sub
0x14c08  stloc.1
0x14c09  ldc.i4.0
0x14c0a  bgt.s    loc_14BB6
0x14c0c  ldstr    aUnableToAcquir// "Unable to acquire lock on entity {0} wi"...
0x14c11  ldc.i4.2
0x14c12  newarr   [mscorlib]System.Object
0x14c17  dup
0x14c18  ldc.i4.0
0x14c19  ldarg.1
0x14c1a  stelem.ref
0x14c1b  dup
0x14c1c  ldc.i4.1
0x14c1d  ldarg.2
0x14c1e  box      [mscorlib]System.Guid
0x14c23  stelem.ref
0x14c24  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmSqlGovernorRequestDeniedException::.ctor(string, object[])
0x14c29  throw
```
