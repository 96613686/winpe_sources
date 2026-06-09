# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::InvokeImport

- ea: `0xe90`
- end: `0xf35`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::InvokeImport`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0xe20`

## callees

- `0xc50`
- `0xc70`
- `0xc90`
- `0xcc0`
- `0xcf0`
- `0xe90`
- `0xfe0`
- `0x1070`
- `0x10c0`
- `0x14b0`
- `0x15a0`
- `0x15d0`

## pseudocode

```c

```

## disassembly

```asm
0xe90  ldarg.0
0xe91  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xe96  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageLocation
0xe9b  ldstr    aPackagelocatio_0// "packageLocation"
0xea0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xea5  ldarg.0
0xea6  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xeab  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageName
0xeb0  ldstr    aPackagename_0// "packageName"
0xeb5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xeba  ldarg.0
0xebb  call     instance string[] Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::DequeueLog()
0xec0  pop
0xec1  ldarg.0
0xec2  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ResetCompletion()
0xec7  ldarg.0
0xec8  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::PrepareCoreObjects()
0xecd  ldarg.0
0xece  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::InvokePackageDeployer()
0xed3  ldarg.0
0xed4  ldarg.1
0xed5  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::WaitForCompletion(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan> timeout)
0xeda  ldarg.0
0xedb  ldfld    class [mscorlib]System.Exception Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_jobException
0xee0  brfalse.s loc_EE9
0xee2  ldarg.0
0xee3  ldfld    class [mscorlib]System.Exception Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_jobException
0xee8  throw
0xee9  leave.s  loc_F1A
0xeeb  stloc.0
0xeec  ldarg.0
0xeed  ldloc.0
0xeee  callvirt instance string [mscorlib]System.Object::ToString()
0xef3  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0xef8  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::.ctor()
0xefd  dup
0xefe  ldloc.0
0xeff  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::set_Exception(class [mscorlib]System.Exception value)
0xf04  dup
0xf05  ldarg.0
0xf06  call     instance string[] Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::DequeueLog()
0xf0b  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::set_Log(string[] value)
0xf10  dup
0xf11  ldc.i4.0
0xf12  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::set_Successful(bool value)
0xf17  stloc.1
0xf18  leave.s  loc_F33
0xf1a  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::.ctor()
0xf1f  dup
0xf20  ldarg.0
0xf21  call     instance string[] Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::DequeueLog()
0xf26  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::set_Log(string[] value)
0xf2b  dup
0xf2c  ldc.i4.1
0xf2d  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::set_Successful(bool value)
0xf32  ret
0xf33  ldloc.1
0xf34  ret
```
