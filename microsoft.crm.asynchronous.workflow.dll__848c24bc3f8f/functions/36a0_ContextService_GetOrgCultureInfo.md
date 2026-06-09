# ContextService::GetOrgCultureInfo

- ea: `0x36a0`
- end: `0x36b7`
- name: `ContextService::GetOrgCultureInfo`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x3650`

## callees

- `0x3660`

## pseudocode

```c

```

## disassembly

```asm
0x36a0  ldarg.0
0x36a1  ldarg.0
0x36a2  ldfld    valuetype [mscorlib]System.Guid ContextService::_instanceId
0x36a7  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration ContextService::GetOrganizationConfiguration(valuetype [mscorlib]System.Guid instanceId)
0x36ac  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationSettings()
0x36b1  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrgCultureInfo()
0x36b6  ret
```
