# Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_RegistryOperations

- ea: `0x13210`
- end: `0x13217`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_RegistryOperations`
- size: `7`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x13230`
- `0x15340`
- `0x15500`
- `0x15990`
- `0x16190`

## pseudocode

```c

```

## disassembly

```asm
0x13210  ldarg.0
0x13211  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::<RegistryOperations>k__BackingField
0x13216  ret
```
