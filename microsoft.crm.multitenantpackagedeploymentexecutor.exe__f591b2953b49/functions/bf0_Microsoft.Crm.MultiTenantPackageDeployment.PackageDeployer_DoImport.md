# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployer::DoImport

- ea: `0xbf0`
- end: `0xc28`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployer::DoImport`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1f10`

## callees

- `0xbf0`
- `0xc70`
- `0xc90`
- `0xca0`
- `0xcc0`
- `0xe20`
- `0x1420`
- `0x1a40`

## pseudocode

```c

```

## disassembly

```asm
0xbf0  ldarg.0
0xbf1  ldarg.1
0xbf2  callvirt instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::DoImport([opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan> timeout)
0xbf7  dup
0xbf8  callvirt instance bool Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::get_TimedOut()
0xbfd  brfalse.s loc_C05
0xbff  ldarg.0
0xc00  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::Cancel()
0xc05  stloc.0
0xc06  leave.s  loc_C26
0xc08  stloc.1
0xc09  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::.ctor()
0xc0e  dup
0xc0f  ldloc.1
0xc10  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::set_Exception(class [mscorlib]System.Exception value)
0xc15  dup
0xc16  ldc.i4.0
0xc17  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::set_Successful(bool value)
0xc1c  stloc.0
0xc1d  leave.s  loc_C26
0xc1f  ldarg.0
0xc20  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::Dispose()
0xc25  endfinally
0xc26  ldloc.0
0xc27  ret
```
