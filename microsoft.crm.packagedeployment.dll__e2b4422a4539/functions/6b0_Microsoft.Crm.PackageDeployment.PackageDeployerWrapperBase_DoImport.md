# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::DoImport

- ea: `0x6b0`
- end: `0x713`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::DoImport`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x370`

## callees

- `0x580`
- `0x5a0`
- `0x5d0`
- `0x720`
- `0xb60`

## pseudocode

```c

```

## disassembly

```asm
0x6b0  ldarg.0
0x6b1  ldarg.0
0x6b2  call     instance string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LocatePackageAssemblyInSourcePath()
0x6b7  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::set_FullyQualifiedPathToAssembly(string value)
0x6bc  ldarg.0
0x6bd  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x6c2  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.PackageDeployment.PackageDeployerArguments::OrganizationId
0x6c7  ldarg.0
0x6c8  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_TraceCategory()
0x6cd  ldstr    aPackagedeploye_4// "PackageDeployer: Invoking PackageDeploy"...
0x6d2  ldc.i4.3
0x6d3  newarr   [mscorlib]System.Object
0x6d8  dup
0x6d9  ldc.i4.0
0x6da  ldarg.0
0x6db  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x6e0  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageName
0x6e5  stelem.ref
0x6e6  dup
0x6e7  ldc.i4.1
0x6e8  ldarg.0
0x6e9  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x6ee  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageLocation
0x6f3  stelem.ref
0x6f4  dup
0x6f5  ldc.i4.2
0x6f6  ldarg.0
0x6f7  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x6fc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.PackageDeployment.PackageDeployerArguments::UserId
0x701  box      [mscorlib]System.Guid
0x706  stelem.ref
0x707  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x70c  ldarg.0
0x70d  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerImportResult Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::InvokeImport()
0x712  ret
```
