# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LocatePackageAssemblyInSourcePath

- ea: `0x1320`
- end: `0x1416`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LocatePackageAssemblyInSourcePath`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xe20`

## callees

- `0xb40`
- `0xb50`
- `0xcf0`
- `0xf60`
- `0x1320`

## string_xrefs

- `0x1385`: `Failed to locate packages in the PackageLocation directory. `

## pseudocode

```c

```

## disassembly

```asm
0x1320  ldarg.0
0x1321  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x1326  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageLocation
0x132b  stloc.0
0x132c  ldloc.0
0x132d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1332  brfalse.s loc_134A
0x1334  ldarg.0
0x1335  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x133a  ldstr    aPackagelocatio_1// "PackageLocation is null or empty."
0x133f  call     string [mscorlib]System.String::Concat(string, string)
0x1344  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerException::.ctor(string message)
0x1349  throw
0x134a  ldloc.0
0x134b  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x1350  brfalse  loc_1400
0x1355  ldstr    aPackagedeploym// "PackageDeployment"
0x135a  newobj   instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::.ctor(string)
0x135f  stloc.1
0x1360  ldloc.0
0x1361  ldnull
0x1362  ldloc.1
0x1363  ldc.i4.0
0x1364  newobj   instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.ImportCustomizationLoader::.ctor(string, string, class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger, bool)
0x1369  stloc.2
0x136a  ldloc.2
0x136b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.IImportExtensions> [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.ImportCustomizationLoader::get_currentPlugins()
0x1370  brfalse.s loc_137F
0x1372  ldloc.2
0x1373  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.IImportExtensions> [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.ImportCustomizationLoader::get_currentPlugins()
0x1378  call     T0x2B000002
0x137d  brtrue.s loc_13A1
0x137f  ldarg.0
0x1380  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1385  ldstr    aFailedToLocate// "Failed to locate packages in the Packag"...
0x138a  ldloc.1
0x138b  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastError()
0x1390  call     string [mscorlib]System.String::Concat(string, string, string)
0x1395  ldloc.1
0x1396  callvirt instance class [mscorlib]System.Exception [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastException()
0x139b  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x13a0  throw
0x13a1  ldloc.2
0x13a2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.IImportExtensions> [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.ImportCustomizationLoader::get_currentPlugins()
0x13a7  call     T0x2B000003
0x13ac  stloc.3
0x13ad  ldarg.0
0x13ae  ldarg.0
0x13af  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x13b4  ldstr    aLocatedPackage// "Located Package: {0}, Name: {1}, Locati"...
0x13b9  call     string [mscorlib]System.String::Concat(string, string)
0x13be  ldloc.3
0x13bf  ldc.i4.0
0x13c0  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.IImportExtensions::GetImportName(bool)
0x13c5  ldloc.3
0x13c6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x13cb  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x13d0  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x13d5  ldloc.3
0x13d6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x13db  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x13e0  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x13e5  call     string [mscorlib]System.String::Format(string, object, object, object)
0x13ea  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x13ef  ldloc.3
0x13f0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x13f5  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x13fa  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x13ff  ret
0x1400  ldarg.0
0x1401  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1406  ldstr    aPackagelocatio_2// "PackageLocation does not exist on disk."
0x140b  call     string [mscorlib]System.String::Concat(string, string)
0x1410  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerException::.ctor(string message)
0x1415  throw
```
