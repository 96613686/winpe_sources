# Microsoft.Crm.Sandbox.LocalConfigStoreProvider::.ctor

- ea: `0x810`
- end: `0x823`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreProvider::.ctor`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

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
0x810  ldarg.0
0x811  ldarg.1
0x812  ldarg.2
0x813  ldarg.3
0x814  ldarg.s  4
0x816  ldarg.s  5
0x818  call     int32 Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::GetDefaultLeaseTime()
0x81d  call     instance void Microsoft.Crm.Sandbox.SandboxCallbackService::.ctor(string assemblyName, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext sdkContext, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter workerCounter, int32 leaseTime)
0x822  ret
```
