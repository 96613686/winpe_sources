# Microsoft.Crm.Sandbox.InternalSandboxEntityDataSourceRetrieverService::WrapperRetrieveEntityDataSource

- ea: `0x4950`
- end: `0x496c`
- name: `Microsoft.Crm.Sandbox.InternalSandboxEntityDataSourceRetrieverService::WrapperRetrieveEntityDataSource`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x4950`
- `0x4970`

## pseudocode

```c

```

## disassembly

```asm
0x4950  ldc.i4.1
0x4951  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x4956  call     instance void [mscorlib]System.Security.PermissionSet::Assert()
0x495b  ldarg.0
0x495c  call     instance unsigned int8[] Microsoft.Crm.Sandbox.InternalSandboxEntityDataSourceRetrieverService::InternalRetrieveEntityDataSource()
0x4961  stloc.0
0x4962  leave.s  loc_496A
0x4964  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x4969  endfinally
0x496a  ldloc.0
0x496b  ret
```
