# Microsoft.Crm.Workflow.Services.ActivityServiceBase::ExecuteInTransactedContext

- ea: `0x14b50`
- end: `0x14b9c`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::ExecuteInTransactedContext`
- size: `76`
- prototype: ``
- caller_count: `12`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x15c90`
- `0x15e50`
- `0x160a0`
- `0x16b80`
- `0x19290`
- `0x19420`
- `0x195c0`
- `0x19a70`
- `0x19cd0`
- `0x19ee0`
- `0x1a4a0`
- `0x1a800`

## callees

- `0x9fe0`
- `0xa060`
- `0xa080`
- `0xa090`
- `0x14770`
- `0x14780`
- `0x14b50`
- `0x2e720`

## pseudocode

```c

```

## disassembly

```asm
0x14b50  ldarg.0
0x14b51  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateSdkService()
0x14b56  stloc.0
0x14b57  ldarg.0
0x14b58  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x14b5d  newobj   instance void Microsoft.Crm.Workflow.WorkflowTransactionContext::.ctor(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.IWorkflowContext workflowContext)
0x14b62  stloc.1
0x14b63  ldloc.1
0x14b64  callvirt instance void Microsoft.Crm.Workflow.WorkflowTransactionContext::OnBeginRequest()
0x14b69  leave.s  loc_14B78
0x14b6b  stloc.2
0x14b6c  ldstr    aErrorWhileCall// "Error while calling OnBeginRequest on W"...
0x14b71  ldloc.2
0x14b72  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x14b77  throw
0x14b78  nop
0x14b79  ldarg.1
0x14b7a  ldloc.0
0x14b7b  callvirt instance void ActivityDelegate::Invoke(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x14b80  ldloc.1
0x14b81  callvirt instance void Microsoft.Crm.Workflow.WorkflowTransactionContext::OnEndRequest()
0x14b86  leave.s  loc_14B9B
0x14b88  pop
0x14b89  ldloc.1
0x14b8a  callvirt instance void Microsoft.Crm.Workflow.WorkflowTransactionContext::OnErrorRequest()
0x14b8f  rethrow
0x14b91  ldloc.1
0x14b92  brfalse.s loc_14B9A
0x14b94  ldloc.1
0x14b95  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14b9a  endfinally
0x14b9b  ret
```
