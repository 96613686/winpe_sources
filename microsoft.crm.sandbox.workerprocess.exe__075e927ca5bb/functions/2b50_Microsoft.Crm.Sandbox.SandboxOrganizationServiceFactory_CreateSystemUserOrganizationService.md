# Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::CreateSystemUserOrganizationService

- ea: `0x2b50`
- end: `0x2b5c`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::CreateSystemUserOrganizationService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x29d0`

## pseudocode

```c

```

## disassembly

```asm
0x2b50  ldarg.0
0x2b51  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2b56  call     instance class Microsoft.Crm.Sandbox.SandboxOrganizationService Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Guid userId)
0x2b5b  ret
```
