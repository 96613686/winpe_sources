# Microsoft.Crm.Sandbox.InternalSandboxEntityDataSourceRetrieverService::.ctor

- ea: `0x4930`
- end: `0x4943`
- name: `Microsoft.Crm.Sandbox.InternalSandboxEntityDataSourceRetrieverService::.ctor`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3300`

## callees

- `0x1ec0`
- `0x2340`

## pseudocode

```c

```

## disassembly

```asm
0x4930  ldarg.0
0x4931  ldarg.1
0x4932  ldarg.2
0x4933  ldarg.3
0x4934  ldarg.s  4
0x4936  ldarg.s  5
0x4938  call     int32 Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::GetDefaultLeaseTime()
0x493d  call     instance void Microsoft.Crm.Sandbox.SandboxCallbackService::.ctor(string assemblyName, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext sdkContext, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter workerCounter, int32 leaseTime)
0x4942  ret
```
