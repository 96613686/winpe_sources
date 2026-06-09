# Microsoft.Crm.Asynchronous.AsyncEvent::get_OrganizationConfiguration

- ea: `0x2e60`
- end: `0x2e67`
- name: `Microsoft.Crm.Asynchronous.AsyncEvent::get_OrganizationConfiguration`
- size: `7`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3170`
- `0x5060`
- `0x50a0`
- `0x54e0`
- `0x8fb0`

## pseudocode

```c

```

## disassembly

```asm
0x2e60  ldarg.0
0x2e61  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AsyncEvent::_organizationConfiguration
0x2e66  ret
```
