# Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::CreateOrganizationService_0

- ea: `0x29d0`
- end: `0x29ed`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::CreateOrganizationService_0`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2980`
- `0x2b50`

## callees

- `0x29d0`
- `0x29f0`

## pseudocode

```c

```

## disassembly

```asm
0x29d0  ldc.i4.1
0x29d1  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x29d6  call     instance void [mscorlib]System.Security.PermissionSet::Assert()
0x29db  ldarg.0
0x29dc  ldarg.1
0x29dd  call     instance class Microsoft.Crm.Sandbox.SandboxOrganizationService Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::CreateOrganizationServiceInternal(valuetype [mscorlib]System.Guid userId)
0x29e2  stloc.0
0x29e3  leave.s  loc_29EB
0x29e5  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x29ea  endfinally
0x29eb  ldloc.0
0x29ec  ret
```
