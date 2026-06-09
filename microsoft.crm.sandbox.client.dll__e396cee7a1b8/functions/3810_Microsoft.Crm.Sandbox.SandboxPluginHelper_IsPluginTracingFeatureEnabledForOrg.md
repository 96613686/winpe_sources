# Microsoft.Crm.Sandbox.SandboxPluginHelper::IsPluginTracingFeatureEnabledForOrg

- ea: `0x3810`
- end: `0x381c`
- name: `Microsoft.Crm.Sandbox.SandboxPluginHelper::IsPluginTracingFeatureEnabledForOrg`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x6470`

## callees

- `0x3820`

## pseudocode

```c

```

## disassembly

```asm
0x3810  ldarg.0
0x3811  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x3816  call     bool Microsoft.Crm.Sandbox.SandboxPluginHelper::IsPluginTracingFeatureEnabledForOrg(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext context)
0x381b  ret
```
