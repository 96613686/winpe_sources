# Microsoft.Crm.Workflow.Services.ActivityServiceBase::GenerateRuntimeExceptionWrapper

- ea: `0x14ec0`
- end: `0x14ed1`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::GenerateRuntimeExceptionWrapper`
- size: `17`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x15bc0`
- `0x15df0`
- `0x16b10`
- `0x19360`
- `0x19520`
- `0x19e60`
- `0x1a410`
- `0x1a7e0`

## callees

- `0x112f0`
- `0x14ec0`
- `0x14ee0`

## pseudocode

```c

```

## disassembly

```asm
0x14ec0  ldarg.0
0x14ec1  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_IsSynchronousWorkflowRuntime()
0x14ec6  brfalse.s loc_14ECF
0x14ec8  ldarg.1
0x14ec9  newobj   instance void Microsoft.Crm.Workflow.SynchronousRuntime.CrmSynchronousWorkflowRuntimeException::.ctor(class [mscorlib]System.Exception innerException)
0x14ece  ret
0x14ecf  ldarg.1
0x14ed0  ret
```
