# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::BackupInstallationPoints

- ea: `0x15d70`
- end: `0x15ede`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::BackupInstallationPoints`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x15be0`

## callees

- `0x14730`
- `0x149e0`
- `0x14a00`
- `0x14c50`
- `0x14c70`
- `0x14d40`
- `0x15d70`
- `0x15ee0`
- `0x16030`

## string_xrefs

- `0x15d7b`: `Expected to find at least one installPointElement`
- `0x15dc8`: `Installation point folder does not exist ({0}).  Skipping backup`
- `0x15dac`: `Preparing for backup of InstallPoint {0}`
- `0x15e3d`: `Skipping backup of install point per package definition`
- `0x15e4f`: `Making full directory backup copy from {0} to {1}`
- `0x15e75`: `Making backup copy of files under {0} which will be replaced during package installation`

## pseudocode

```c

```

## disassembly

```asm
0x15d70  ldarg.1
0x15d71  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint> Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::get_InstallationPoints()
0x15d76  call     T0x2B000019
0x15d7b  ldstr    aExpectedToFind// "Expected to find at least one installPo"...
0x15d80  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x15d85  ldarg.1
0x15d86  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint> Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::get_InstallationPoints()
0x15d8b  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint>::GetEnumerator()
0x15d90  stloc.0
0x15d91  br       loc_15EC1
0x15d96  ldloca.s 0
0x15d98  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint>::get_Current()
0x15d9d  stloc.1
0x15d9e  ldloc.1
0x15d9f  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.NamedDescriptorElement::get_Name()
0x15da4  stloc.2
0x15da5  ldloc.1
0x15da6  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint::get_Location()
0x15dab  stloc.3
0x15dac  ldstr    aPreparingForBa// "Preparing for backup of InstallPoint {0"...
0x15db1  ldc.i4.1
0x15db2  newarr   [mscorlib]System.Object
0x15db7  dup
0x15db8  ldc.i4.0
0x15db9  ldloc.2
0x15dba  stelem.ref
0x15dbb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15dc0  ldloc.3
0x15dc1  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x15dc6  brtrue.s loc_15DE1
0x15dc8  ldstr    aInstallationPo// "Installation point folder does not exis"...
0x15dcd  ldc.i4.1
0x15dce  newarr   [mscorlib]System.Object
0x15dd3  dup
0x15dd4  ldc.i4.0
0x15dd5  ldloc.3
0x15dd6  stelem.ref
0x15dd7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15ddc  br       loc_15EC1
0x15de1  ldloc.1
0x15de2  callvirt instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPointBackupDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint::get_BackupDescriptor()
0x15de7  stloc.s  4
0x15de9  ldloc.s  4
0x15deb  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DirectoryDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPointBackupDescriptor::get_ExcludedDirectories()
0x15df0  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DirectoryDescriptor, string> <>c::<>9__70_0
0x15df5  dup
0x15df6  brtrue.s loc_15E0F
0x15df8  pop
0x15df9  ldsfld   class <>c <>c::<>9
0x15dfe  ldftn    instance string <>c::<BackupInstallationPoints>b__70_0(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DirectoryDescriptor element)
0x15e04  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DirectoryDescriptor, string>::.ctor(object, native int)
0x15e09  dup
0x15e0a  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DirectoryDescriptor, string> <>c::<>9__70_0
0x15e0f  call     T0x2B00001D
0x15e14  stloc.s  5
0x15e16  ldarg.2
0x15e17  ldloc.2
0x15e18  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x15e1d  stloc.s  6
0x15e1f  ldloc.s  4
0x15e21  callvirt instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackageBackupType Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPointBackupDescriptor::get_BackupType()
0x15e26  stloc.s  7
0x15e28  ldloc.s  7
0x15e2a  switch   loc_15E3D, loc_15E4F, loc_15E75
0x15e3b  br.s     loc_15E92
0x15e3d  ldstr    aSkippingBackup// "Skipping backup of install point per pa"...
0x15e42  ldc.i4.0
0x15e43  newarr   [mscorlib]System.Object
0x15e48  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15e4d  br.s     loc_15EC1
0x15e4f  ldstr    aMakingFullDire// "Making full directory backup copy from "...
0x15e54  ldc.i4.2
0x15e55  newarr   [mscorlib]System.Object
0x15e5a  dup
0x15e5b  ldc.i4.0
0x15e5c  ldloc.3
0x15e5d  stelem.ref
0x15e5e  dup
0x15e5f  ldc.i4.1
0x15e60  ldloc.s  6
0x15e62  stelem.ref
0x15e63  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15e68  ldarg.0
0x15e69  ldloc.3
0x15e6a  ldloc.s  6
0x15e6c  ldloc.s  5
0x15e6e  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::BackupDirectoryTree(string sourceDirectoryPath, string backupDirectoryPath, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> subdirectoryNamesToExclude)
0x15e73  br.s     loc_15EC1
0x15e75  ldstr    aMakingBackupCo// "Making backup copy of files under {0} w"...
0x15e7a  ldc.i4.1
0x15e7b  newarr   [mscorlib]System.Object
0x15e80  dup
0x15e81  ldc.i4.0
0x15e82  ldloc.3
0x15e83  stelem.ref
0x15e84  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15e89  ldarg.0
0x15e8a  ldloc.3
0x15e8b  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::BackupCurrentFilesReferencedInStagingDirectory(string installationPoint)
0x15e90  br.s     loc_15EC1
0x15e92  ldstr    aPackagebackupt// "PackageBackupType.{0} is not supported"
0x15e97  ldc.i4.1
0x15e98  newarr   [mscorlib]System.Object
0x15e9d  dup
0x15e9e  ldc.i4.0
0x15e9f  ldloc.s  4
0x15ea1  callvirt instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackageBackupType Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPointBackupDescriptor::get_BackupType()
0x15ea6  stloc.s  7
0x15ea8  ldloca.s 7
0x15eaa  constrained. Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackageBackupType
0x15eb0  callvirt instance string [mscorlib]System.Object::ToString()
0x15eb5  stelem.ref
0x15eb6  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x15ebb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x15ec0  throw
0x15ec1  ldloca.s 0
0x15ec3  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint>::MoveNext()
0x15ec8  brtrue   loc_15D96
0x15ecd  leave.s  loc_15EDD
0x15ecf  ldloca.s 0
0x15ed1  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint>
0x15ed7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15edc  endfinally
0x15edd  ret
```
