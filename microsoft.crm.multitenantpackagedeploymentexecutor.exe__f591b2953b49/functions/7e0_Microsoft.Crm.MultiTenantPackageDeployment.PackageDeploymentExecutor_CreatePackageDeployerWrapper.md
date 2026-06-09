# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutor::CreatePackageDeployerWrapper

- ea: `0x7e0`
- end: `0x804`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutor::CreatePackageDeployerWrapper`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x3a0`

## callees

- `0x40`
- `0x60`
- `0x100`
- `0xd60`
- `0xd80`
- `0x1b20`

## pseudocode

```c

```

## disassembly

```asm
0x7e0  ldarg.0
0x7e1  callvirt instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::get_PDArgs()
0x7e6  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.LivePackageDeployerWrapper::.ctor(class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments arguments)
0x7eb  dup
0x7ec  ldarg.0
0x7ed  callvirt instance bool Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::get_IsInternalCRMAppsInstall()
0x7f2  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::set_IsInternalCRMAppsInstall(bool value)
0x7f7  dup
0x7f8  ldarg.0
0x7f9  callvirt instance bool Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::get_IsSystemConvertedSolutionUpgrade()
0x7fe  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::set_IsSystemConvertedSolutionUpgrade(bool value)
0x803  ret
```
