# Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::Dispose

- ea: `0x2b30`
- end: `0x2b46`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::Dispose`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x2ac0`
- `0x2b30`

## pseudocode

```c

```

## disassembly

```asm
0x2b30  ldarg.0
0x2b31  ldfld    bool Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_blocked
0x2b36  brtrue.s loc_2B3E
0x2b38  ldarg.0
0x2b39  call     instance void Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::Cleanup()
0x2b3e  ldarg.0
0x2b3f  ldnull
0x2b40  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_context
0x2b45  ret
```
