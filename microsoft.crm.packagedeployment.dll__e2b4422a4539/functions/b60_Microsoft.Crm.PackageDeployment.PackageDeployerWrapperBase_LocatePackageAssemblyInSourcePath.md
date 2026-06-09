# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LocatePackageAssemblyInSourcePath

- ea: `0xb60`
- end: `0xc56`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LocatePackageAssemblyInSourcePath`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x6b0`

## callees

- `0x2b0`
- `0x2c0`
- `0x580`
- `0x7f0`
- `0xb60`

## string_xrefs

- `0xbc5`: `Failed to locate packages in the PackageLocation directory. `

## pseudocode

```c

```

## disassembly

```asm
0xb60  ldarg.0
0xb61  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xb66  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageLocation
0xb6b  stloc.0
0xb6c  ldloc.0
0xb6d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb72  brfalse.s loc_B8A
0xb74  ldarg.0
0xb75  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xb7a  ldstr    aPackagelocatio_0// "PackageLocation is null or empty."
0xb7f  call     string [mscorlib]System.String::Concat(string, string)
0xb84  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerException::.ctor(string message)
0xb89  throw
0xb8a  ldloc.0
0xb8b  call     bool [mscorlib]System.IO.Directory::Exists(string)
0xb90  brfalse  loc_C40
0xb95  ldstr    aPackagedeploym// "PackageDeployment"
0xb9a  newobj   instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::.ctor(string)
0xb9f  stloc.1
0xba0  ldloc.0
0xba1  ldnull
0xba2  ldloc.1
0xba3  ldc.i4.0
0xba4  newobj   instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.ImportCustomizationLoader::.ctor(string, string, class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger, bool)
0xba9  stloc.2
0xbaa  ldloc.2
0xbab  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.IImportExtensions> [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.ImportCustomizationLoader::get_currentPlugins()
0xbb0  brfalse.s loc_BBF
0xbb2  ldloc.2
0xbb3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.IImportExtensions> [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.ImportCustomizationLoader::get_currentPlugins()
0xbb8  call     T0x2B000001
0xbbd  brtrue.s loc_BE1
0xbbf  ldarg.0
0xbc0  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xbc5  ldstr    aFailedToLocate// "Failed to locate packages in the Packag"...
0xbca  ldloc.1
0xbcb  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastError()
0xbd0  call     string [mscorlib]System.String::Concat(string, string, string)
0xbd5  ldloc.1
0xbd6  callvirt instance class [mscorlib]System.Exception [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastException()
0xbdb  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerException::.ctor(string message, class [mscorlib]System.Exception innerException)
0xbe0  throw
0xbe1  ldloc.2
0xbe2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.IImportExtensions> [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.ImportCustomizationLoader::get_currentPlugins()
0xbe7  call     T0x2B000002
0xbec  stloc.3
0xbed  ldarg.0
0xbee  ldarg.0
0xbef  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xbf4  ldstr    aLocatedPackage// "Located Package: {0}, Name: {1}, Locati"...
0xbf9  call     string [mscorlib]System.String::Concat(string, string)
0xbfe  ldloc.3
0xbff  ldc.i4.0
0xc00  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.IImportExtensions::GetImportName(bool)
0xc05  ldloc.3
0xc06  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc0b  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xc10  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0xc15  ldloc.3
0xc16  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc1b  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xc20  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0xc25  call     string [mscorlib]System.String::Format(string, object, object, object)
0xc2a  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0xc2f  ldloc.3
0xc30  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc35  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xc3a  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0xc3f  ret
0xc40  ldarg.0
0xc41  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xc46  ldstr    aPackagelocatio_1// "PackageLocation does not exist on disk."
0xc4b  call     string [mscorlib]System.String::Concat(string, string)
0xc50  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerException::.ctor(string message)
0xc55  throw
```
