# Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::get_OrganizationId

- ea: `0xbac0`
- end: `0xbac7`
- name: `Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::get_OrganizationId`
- size: `7`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbb70`
- `0xbb90`
- `0xbbf0`
- `0xcb80`

## pseudocode

```c

```

## disassembly

```asm
0xbac0  ldarg.0
0xbac1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::_organizationId
0xbac6  ret
```
