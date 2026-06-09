# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::InvokeImport

- ea: `0x720`
- end: `0x7c9`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::InvokeImport`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x6b0`

## callees

- `0x500`
- `0x520`
- `0x540`
- `0x550`
- `0x580`
- `0x720`
- `0x870`
- `0x900`
- `0x930`
- `0xcd0`
- `0xdc0`
- `0xdf0`

## pseudocode

```c

```

## disassembly

```asm
0x720  ldarg.0
0x721  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x726  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageLocation
0x72b  ldstr    aPackagelocatio// "packageLocation"
0x730  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x735  ldarg.0
0x736  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x73b  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageName
0x740  ldstr    aPackagename// "packageName"
0x745  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x74a  ldarg.0
0x74b  call     instance string[] Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::DequeueLog()
0x750  pop
0x751  ldarg.0
0x752  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ResetCompletion()
0x757  ldarg.0
0x758  call     instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::PrepareCoreObjects()
0x75d  call     void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Core::set_CoreData(class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects)
0x762  ldarg.0
0x763  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::InvokePackageDeployer()
0x768  ldarg.0
0x769  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::WaitForCompletion()
0x76e  ldarg.0
0x76f  ldfld    class [mscorlib]System.Exception Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_jobException
0x774  brfalse.s loc_77D
0x776  ldarg.0
0x777  ldfld    class [mscorlib]System.Exception Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_jobException
0x77c  throw
0x77d  leave.s  loc_7AE
0x77f  stloc.0
0x780  ldarg.0
0x781  ldloc.0
0x782  callvirt instance string [mscorlib]System.Object::ToString()
0x787  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x78c  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerImportResult::.ctor()
0x791  dup
0x792  ldloc.0
0x793  callvirt instance void Microsoft.Crm.PackageDeployment.PackageDeployerImportResult::set_Exception(class [mscorlib]System.Exception value)
0x798  dup
0x799  ldarg.0
0x79a  call     instance string[] Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::DequeueLog()
0x79f  callvirt instance void Microsoft.Crm.PackageDeployment.PackageDeployerImportResult::set_Log(string[] value)
0x7a4  dup
0x7a5  ldc.i4.0
0x7a6  callvirt instance void Microsoft.Crm.PackageDeployment.PackageDeployerImportResult::set_Successful(bool value)
0x7ab  stloc.1
0x7ac  leave.s  loc_7C7
0x7ae  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerImportResult::.ctor()
0x7b3  dup
0x7b4  ldarg.0
0x7b5  call     instance string[] Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::DequeueLog()
0x7ba  callvirt instance void Microsoft.Crm.PackageDeployment.PackageDeployerImportResult::set_Log(string[] value)
0x7bf  dup
0x7c0  ldc.i4.1
0x7c1  callvirt instance void Microsoft.Crm.PackageDeployment.PackageDeployerImportResult::set_Successful(bool value)
0x7c6  ret
0x7c7  ldloc.1
0x7c8  ret
```
