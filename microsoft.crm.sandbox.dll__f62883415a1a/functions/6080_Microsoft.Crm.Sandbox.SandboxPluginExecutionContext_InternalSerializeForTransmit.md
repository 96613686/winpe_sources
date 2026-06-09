# Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::InternalSerializeForTransmit

- ea: `0x6080`
- end: `0x609a`
- name: `Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::InternalSerializeForTransmit`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x6070`

## callees

- `0x6080`
- `0x68c0`

## pseudocode

```c

```

## disassembly

```asm
0x6080  ldc.i4.1
0x6081  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x6086  call     instance void [mscorlib]System.Security.PermissionSet::Assert()
0x608b  ldarg.0
0x608c  callvirt instance void Microsoft.Crm.Sandbox.SandboxExecutionContext::SerializeForTransmit()
0x6091  leave.s  loc_6099
0x6093  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x6098  endfinally
0x6099  ret
```
