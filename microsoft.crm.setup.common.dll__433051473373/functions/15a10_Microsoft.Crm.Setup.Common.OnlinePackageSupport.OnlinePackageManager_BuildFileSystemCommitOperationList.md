# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::BuildFileSystemCommitOperationList

- ea: `0x15a10`
- end: `0x15bda`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::BuildFileSystemCommitOperationList`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x15340`

## callees

- `0x133b0`
- `0x133e0`
- `0x13400`
- `0x13430`
- `0x13f70`
- `0x14730`
- `0x149e0`
- `0x14a00`
- `0x14c50`
- `0x14d40`
- `0x156e0`
- `0x15a10`
- `0x16400`
- `0x16470`

## string_xrefs

- `0x15a44`: `Constructing FileSystemOperation for commit of {0}`
- `0x15a66`: `Installation point folder does not exist ({0}).  Skipping backup`

## pseudocode

```c

```

## disassembly

```asm
0x15a10  ldarg.1
0x15a11  callvirt instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::get_PrimaryPackageDescriptor()
0x15a16  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::.ctor()
0x15a1b  stloc.0
0x15a1c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint> Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::get_InstallationPoints()
0x15a21  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint>::GetEnumerator()
0x15a26  stloc.1
0x15a27  br       loc_15BBC
0x15a2c  ldloca.s 1
0x15a2e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint>::get_Current()
0x15a33  stloc.2
0x15a34  ldloc.2
0x15a35  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint::get_Location()
0x15a3a  stloc.3
0x15a3b  ldarg.0
0x15a3c  ldloc.3
0x15a3d  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::GetStagingPathForInstallLocation(string installPointLocation)
0x15a42  stloc.s  4
0x15a44  ldstr    aConstructingFi// "Constructing FileSystemOperation for co"...
0x15a49  ldc.i4.1
0x15a4a  newarr   [mscorlib]System.Object
0x15a4f  dup
0x15a50  ldc.i4.0
0x15a51  ldloc.2
0x15a52  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.NamedDescriptorElement::get_Name()
0x15a57  stelem.ref
0x15a58  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15a5d  ldloc.s  4
0x15a5f  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x15a64  brtrue.s loc_15A7F
0x15a66  ldstr    aInstallationPo// "Installation point folder does not exis"...
0x15a6b  ldc.i4.1
0x15a6c  newarr   [mscorlib]System.Object
0x15a71  dup
0x15a72  ldc.i4.0
0x15a73  ldloc.3
0x15a74  stelem.ref
0x15a75  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15a7a  br       loc_15BBC
0x15a7f  ldloc.2
0x15a80  callvirt instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPointBackupDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint::get_BackupDescriptor()
0x15a85  stloc.s  5
0x15a87  ldloc.3
0x15a88  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x15a8d  pop
0x15a8e  ldloc.s  5
0x15a90  callvirt instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackageBackupType Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPointBackupDescriptor::get_BackupType()
0x15a95  stloc.s  6
0x15a97  ldloc.s  6
0x15a99  ldc.i4.1
0x15a9a  beq.s    loc_15AA9
0x15a9c  ldloc.s  6
0x15a9e  ldc.i4.2
0x15a9f  beq      loc_15B38
0x15aa4  br       loc_15B8D
0x15aa9  ldc.i4.5
0x15aaa  stloc.s  7
0x15aac  ldarg.1
0x15aad  callvirt instance bool Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::get_IsCompletePackage()
0x15ab2  brtrue.s loc_15AB7
0x15ab4  ldc.i4.6
0x15ab5  stloc.s  7
0x15ab7  ldloc.s  4
0x15ab9  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x15abe  callvirt instance class [mscorlib]System.IO.DirectoryInfo[] [mscorlib]System.IO.DirectoryInfo::GetDirectories()
0x15ac3  stloc.s  8
0x15ac5  ldc.i4.0
0x15ac6  stloc.s  9
0x15ac8  br.s     loc_15B0A
0x15aca  ldloc.s  8
0x15acc  ldloc.s  9
0x15ace  ldelem.ref
0x15acf  stloc.s  0xA
0x15ad1  ldloc.0
0x15ad2  newobj   instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::.ctor()
0x15ad7  dup
0x15ad8  ldloc.s  7
0x15ada  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Operation(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode value)
0x15adf  dup
0x15ae0  ldloc.s  0xA
0x15ae2  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x15ae7  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Source(string value)
0x15aec  dup
0x15aed  ldloc.3
0x15aee  ldloc.s  0xA
0x15af0  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x15af5  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x15afa  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Target(string value)
0x15aff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::Add(var<u1>)
0x15b04  ldloc.s  9
0x15b06  ldc.i4.1
0x15b07  add
0x15b08  stloc.s  9
0x15b0a  ldloc.s  9
0x15b0c  ldloc.s  8
0x15b0e  ldlen
0x15b0f  conv.i4
0x15b10  blt.s    loc_15ACA
0x15b12  ldloc.0
0x15b13  newobj   instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::.ctor()
0x15b18  dup
0x15b19  ldc.i4.7
0x15b1a  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Operation(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode value)
0x15b1f  dup
0x15b20  ldloc.s  4
0x15b22  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Source(string value)
0x15b27  dup
0x15b28  ldloc.3
0x15b29  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Target(string value)
0x15b2e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::Add(var<u1>)
0x15b33  br       loc_15BBC
0x15b38  ldloc.s  4
0x15b3a  ldstr    asc_1953A// "*"
0x15b3f  ldc.i4.1
0x15b40  call     string[] [mscorlib]System.IO.Directory::GetFiles(string, string, valuetype [mscorlib]System.IO.SearchOption)
0x15b45  stloc.s  0xB
0x15b47  ldc.i4.0
0x15b48  stloc.s  9
0x15b4a  br.s     loc_15B83
0x15b4c  ldloc.s  0xB
0x15b4e  ldloc.s  9
0x15b50  ldelem.ref
0x15b51  stloc.s  0xC
0x15b53  ldloc.0
0x15b54  newobj   instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::.ctor()
0x15b59  dup
0x15b5a  ldc.i4.2
0x15b5b  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Operation(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode value)
0x15b60  dup
0x15b61  ldloc.s  0xC
0x15b63  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Source(string value)
0x15b68  dup
0x15b69  ldloc.s  0xC
0x15b6b  ldloc.s  4
0x15b6d  ldloc.3
0x15b6e  call     string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::GetPathRelativeToTarget(string fullSourcePath, string sourceDirectoryPath, string targetDirectoryPath)
0x15b73  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Target(string value)
0x15b78  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::Add(var<u1>)
0x15b7d  ldloc.s  9
0x15b7f  ldc.i4.1
0x15b80  add
0x15b81  stloc.s  9
0x15b83  ldloc.s  9
0x15b85  ldloc.s  0xB
0x15b87  ldlen
0x15b88  conv.i4
0x15b89  blt.s    loc_15B4C
0x15b8b  br.s     loc_15BBC
0x15b8d  ldstr    aPackagebackupt// "PackageBackupType.{0} is not supported"
0x15b92  ldc.i4.1
0x15b93  newarr   [mscorlib]System.Object
0x15b98  dup
0x15b99  ldc.i4.0
0x15b9a  ldloc.s  5
0x15b9c  callvirt instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackageBackupType Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPointBackupDescriptor::get_BackupType()
0x15ba1  stloc.s  6
0x15ba3  ldloca.s 6
0x15ba5  constrained. Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackageBackupType
0x15bab  callvirt instance string [mscorlib]System.Object::ToString()
0x15bb0  stelem.ref
0x15bb1  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x15bb6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x15bbb  throw
0x15bbc  ldloca.s 1
0x15bbe  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint>::MoveNext()
0x15bc3  brtrue   loc_15A2C
0x15bc8  leave.s  loc_15BD8
0x15bca  ldloca.s 1
0x15bcc  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint>
0x15bd2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15bd7  endfinally
0x15bd8  ldloc.0
0x15bd9  ret
```
