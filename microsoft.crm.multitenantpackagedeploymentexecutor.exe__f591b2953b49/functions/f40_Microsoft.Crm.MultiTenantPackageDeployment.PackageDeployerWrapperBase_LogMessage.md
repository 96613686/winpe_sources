# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogMessage

- ea: `0xf40`
- end: `0xf54`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogMessage`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1b30`

## callees

- `0xf40`
- `0xf60`
- `0xfe0`

## pseudocode

```c

```

## disassembly

```asm
0xf40  ldarg.1
0xf41  ldc.i4.1
0xf42  bne.un.s loc_F4C
0xf44  ldarg.0
0xf45  ldarg.2
0xf46  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0xf4b  ret
0xf4c  ldarg.0
0xf4d  ldarg.2
0xf4e  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0xf53  ret
```
