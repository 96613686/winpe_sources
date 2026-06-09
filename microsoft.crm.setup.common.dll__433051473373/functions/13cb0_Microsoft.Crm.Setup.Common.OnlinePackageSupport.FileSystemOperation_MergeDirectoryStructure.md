# Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MergeDirectoryStructure

- ea: `0x13cb0`
- end: `0x13e2d`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MergeDirectoryStructure`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x13580`

## callees

- `0x13970`
- `0x13a20`
- `0x13cb0`
- `0x13f70`

## string_xrefs

- `0x13cb6`: `source directory must exist`
- `0x13cc0`: `Merge directory structure from {0} to {1}`
- `0x13df6`: `Error occured while merging directory structure from {0} to {1}: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x13cb0  ldarg.0
0x13cb1  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x13cb6  ldstr    aSourceDirector// "source directory must exist"
0x13cbb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x13cc0  ldstr    aMergeDirectory// "Merge directory structure from {0} to {"...
0x13cc5  ldc.i4.2
0x13cc6  newarr   [mscorlib]System.Object
0x13ccb  dup
0x13ccc  ldc.i4.0
0x13ccd  ldarg.0
0x13cce  stelem.ref
0x13ccf  dup
0x13cd0  ldc.i4.1
0x13cd1  ldarg.1
0x13cd2  stelem.ref
0x13cd3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x13cd8  ldarg.0
0x13cd9  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x13cde  stloc.0
0x13cdf  ldloc.0
0x13ce0  ldstr    asc_1953A// "*"
0x13ce5  ldc.i4.1
0x13ce6  callvirt instance class [mscorlib]System.IO.DirectoryInfo[] [mscorlib]System.IO.DirectoryInfo::GetDirectories(string, valuetype [mscorlib]System.IO.SearchOption)
0x13ceb  stloc.1
0x13cec  ldc.i4.0
0x13ced  stloc.2
0x13cee  br       loc_13D8A
0x13cf3  ldloc.1
0x13cf4  ldloc.2
0x13cf5  ldelem.ref
0x13cf6  stloc.3
0x13cf7  ldloc.3
0x13cf8  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13cfd  ldarg.0
0x13cfe  ldarg.1
0x13cff  call     string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::GetPathRelativeToTarget(string fullSourcePath, string sourceDirectoryPath, string targetDirectoryPath)
0x13d04  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x13d09  stloc.s  4
0x13d0b  ldloc.s  4
0x13d0d  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x13d12  brfalse.s loc_13D42
0x13d14  ldloc.s  4
0x13d16  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles()
0x13d1b  stloc.s  5
0x13d1d  ldc.i4.0
0x13d1e  stloc.s  6
0x13d20  br.s     loc_13D38
0x13d22  ldloc.s  5
0x13d24  ldloc.s  6
0x13d26  ldelem.ref
0x13d27  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13d2c  ldarg.2
0x13d2d  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteFile(string filePath, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13d32  ldloc.s  6
0x13d34  ldc.i4.1
0x13d35  add
0x13d36  stloc.s  6
0x13d38  ldloc.s  6
0x13d3a  ldloc.s  5
0x13d3c  ldlen
0x13d3d  conv.i4
0x13d3e  blt.s    loc_13D22
0x13d40  br.s     loc_13D49
0x13d42  ldloc.s  4
0x13d44  callvirt instance void [mscorlib]System.IO.DirectoryInfo::Create()
0x13d49  ldloc.3
0x13d4a  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles()
0x13d4f  stloc.s  5
0x13d51  ldc.i4.0
0x13d52  stloc.s  6
0x13d54  br.s     loc_13D7E
0x13d56  ldloc.s  5
0x13d58  ldloc.s  6
0x13d5a  ldelem.ref
0x13d5b  stloc.s  7
0x13d5d  ldloc.s  7
0x13d5f  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13d64  ldloc.s  7
0x13d66  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13d6b  ldarg.0
0x13d6c  ldarg.1
0x13d6d  call     string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::GetPathRelativeToTarget(string fullSourcePath, string sourceDirectoryPath, string targetDirectoryPath)
0x13d72  ldarg.2
0x13d73  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFile(string source, string target, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13d78  ldloc.s  6
0x13d7a  ldc.i4.1
0x13d7b  add
0x13d7c  stloc.s  6
0x13d7e  ldloc.s  6
0x13d80  ldloc.s  5
0x13d82  ldlen
0x13d83  conv.i4
0x13d84  blt.s    loc_13D56
0x13d86  ldloc.2
0x13d87  ldc.i4.1
0x13d88  add
0x13d89  stloc.2
0x13d8a  ldloc.2
0x13d8b  ldloc.1
0x13d8c  ldlen
0x13d8d  conv.i4
0x13d8e  blt      loc_13CF3
0x13d93  ldarg.1
0x13d94  call     string[] [mscorlib]System.IO.Directory::GetFiles(string)
0x13d99  stloc.s  8
0x13d9b  ldc.i4.0
0x13d9c  stloc.2
0x13d9d  br.s     loc_13DAD
0x13d9f  ldloc.s  8
0x13da1  ldloc.2
0x13da2  ldelem.ref
0x13da3  ldarg.2
0x13da4  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteFile(string filePath, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13da9  ldloc.2
0x13daa  ldc.i4.1
0x13dab  add
0x13dac  stloc.2
0x13dad  ldloc.2
0x13dae  ldloc.s  8
0x13db0  ldlen
0x13db1  conv.i4
0x13db2  blt.s    loc_13D9F
0x13db4  ldloc.0
0x13db5  ldstr    asc_1953A// "*"
0x13dba  ldc.i4.0
0x13dbb  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string, valuetype [mscorlib]System.IO.SearchOption)
0x13dc0  stloc.s  5
0x13dc2  ldc.i4.0
0x13dc3  stloc.2
0x13dc4  br.s     loc_13DEB
0x13dc6  ldloc.s  5
0x13dc8  ldloc.2
0x13dc9  ldelem.ref
0x13dca  stloc.s  9
0x13dcc  ldloc.s  9
0x13dce  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13dd3  ldloc.s  9
0x13dd5  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13dda  ldarg.0
0x13ddb  ldarg.1
0x13ddc  call     string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::GetPathRelativeToTarget(string fullSourcePath, string sourceDirectoryPath, string targetDirectoryPath)
0x13de1  ldarg.2
0x13de2  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFile(string source, string target, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13de7  ldloc.2
0x13de8  ldc.i4.1
0x13de9  add
0x13dea  stloc.2
0x13deb  ldloc.2
0x13dec  ldloc.s  5
0x13dee  ldlen
0x13def  conv.i4
0x13df0  blt.s    loc_13DC6
0x13df2  leave.s  loc_13E2C
0x13df4  stloc.s  0xA
0x13df6  ldstr    aErrorOccuredWh_0// "Error occured while merging directory s"...
0x13dfb  ldc.i4.3
0x13dfc  newarr   [mscorlib]System.Object
0x13e01  dup
0x13e02  ldc.i4.0
0x13e03  ldarg.0
0x13e04  stelem.ref
0x13e05  dup
0x13e06  ldc.i4.1
0x13e07  ldarg.1
0x13e08  stelem.ref
0x13e09  dup
0x13e0a  ldc.i4.2
0x13e0b  ldloc.s  0xA
0x13e0d  stelem.ref
0x13e0e  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x13e13  stloc.s  0xB
0x13e15  ldloc.s  0xB
0x13e17  ldc.i4.0
0x13e18  newarr   [mscorlib]System.Object
0x13e1d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x13e22  ldloc.s  0xB
0x13e24  ldloc.s  0xA
0x13e26  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x13e2b  throw
0x13e2c  ret
```
