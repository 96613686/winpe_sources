# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::DoImport

- ea: `0xe20`
- end: `0xe84`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::DoImport`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xbf0`

## callees

- `0xcf0`
- `0xd10`
- `0xd40`
- `0xe90`
- `0x1320`

## pseudocode

```c

```

## disassembly

```asm
0xe20  ldarg.0
0xe21  ldarg.0
0xe22  call     instance string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LocatePackageAssemblyInSourcePath()
0xe27  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::set_FullyQualifiedPathToAssembly(string value)
0xe2c  ldarg.0
0xe2d  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xe32  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::OrganizationId
0xe37  ldarg.0
0xe38  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_TraceCategory()
0xe3d  ldstr    aPackagedeploye_0// "PackageDeployer: Invoking PackageDeploy"...
0xe42  ldc.i4.3
0xe43  newarr   [mscorlib]System.Object
0xe48  dup
0xe49  ldc.i4.0
0xe4a  ldarg.0
0xe4b  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xe50  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageName
0xe55  stelem.ref
0xe56  dup
0xe57  ldc.i4.1
0xe58  ldarg.0
0xe59  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xe5e  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageLocation
0xe63  stelem.ref
0xe64  dup
0xe65  ldc.i4.2
0xe66  ldarg.0
0xe67  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xe6c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::UserId
0xe71  box      [mscorlib]System.Guid
0xe76  stelem.ref
0xe77  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xe7c  ldarg.0
0xe7d  ldarg.1
0xe7e  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::InvokeImport(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan> timeout)
0xe83  ret
```
