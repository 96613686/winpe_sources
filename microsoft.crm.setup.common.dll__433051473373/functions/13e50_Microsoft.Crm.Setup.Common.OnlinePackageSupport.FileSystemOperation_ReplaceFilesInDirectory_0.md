# Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::ReplaceFilesInDirectory_0

- ea: `0x13e50`
- end: `0x13f3c`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::ReplaceFilesInDirectory_0`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x13e30`

## callees

- `0x13970`
- `0x13a20`
- `0x13e50`
- `0x13f70`

## string_xrefs

- `0x13e56`: `source directory must exist`
- `0x13e60`: `Replace files in {0} with files from {1}`

## pseudocode

```c

```

## disassembly

```asm
0x13e50  ldarg.0
0x13e51  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x13e56  ldstr    aSourceDirector// "source directory must exist"
0x13e5b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x13e60  ldstr    aReplaceFilesIn// "Replace files in {0} with files from {1"...
0x13e65  ldc.i4.2
0x13e66  newarr   [mscorlib]System.Object
0x13e6b  dup
0x13e6c  ldc.i4.0
0x13e6d  ldarg.0
0x13e6e  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13e73  stelem.ref
0x13e74  dup
0x13e75  ldc.i4.1
0x13e76  ldarg.1
0x13e77  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13e7c  stelem.ref
0x13e7d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x13e82  ldarg.1
0x13e83  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles()
0x13e88  stloc.0
0x13e89  ldc.i4.0
0x13e8a  stloc.1
0x13e8b  br.s     loc_13E9F
0x13e8d  ldloc.0
0x13e8e  ldloc.1
0x13e8f  ldelem.ref
0x13e90  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13e95  ldarg.2
0x13e96  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteFile(string filePath, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13e9b  ldloc.1
0x13e9c  ldc.i4.1
0x13e9d  add
0x13e9e  stloc.1
0x13e9f  ldloc.1
0x13ea0  ldloc.0
0x13ea1  ldlen
0x13ea2  conv.i4
0x13ea3  blt.s    loc_13E8D
0x13ea5  ldarg.0
0x13ea6  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles()
0x13eab  stloc.0
0x13eac  ldc.i4.0
0x13ead  stloc.1
0x13eae  br.s     loc_13EF1
0x13eb0  ldloc.0
0x13eb1  ldloc.1
0x13eb2  ldelem.ref
0x13eb3  dup
0x13eb4  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13eb9  ldarg.0
0x13eba  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13ebf  ldarg.1
0x13ec0  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13ec5  call     string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::GetPathRelativeToTarget(string fullSourcePath, string sourceDirectoryPath, string targetDirectoryPath)
0x13eca  stloc.2
0x13ecb  ldloc.2
0x13ecc  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x13ed1  stloc.3
0x13ed2  ldloc.3
0x13ed3  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x13ed8  brtrue.s loc_13EE1
0x13eda  ldloc.3
0x13edb  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x13ee0  pop
0x13ee1  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13ee6  ldloc.2
0x13ee7  ldarg.2
0x13ee8  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFile(string source, string target, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13eed  ldloc.1
0x13eee  ldc.i4.1
0x13eef  add
0x13ef0  stloc.1
0x13ef1  ldloc.1
0x13ef2  ldloc.0
0x13ef3  ldlen
0x13ef4  conv.i4
0x13ef5  blt.s    loc_13EB0
0x13ef7  leave.s  loc_13F3B
0x13ef9  stloc.s  4
0x13efb  ldstr    aErrorOccuredWh_1// "Error occured while replacing files in "...
0x13f00  ldc.i4.3
0x13f01  newarr   [mscorlib]System.Object
0x13f06  dup
0x13f07  ldc.i4.0
0x13f08  ldarg.0
0x13f09  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13f0e  stelem.ref
0x13f0f  dup
0x13f10  ldc.i4.1
0x13f11  ldarg.1
0x13f12  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x13f17  stelem.ref
0x13f18  dup
0x13f19  ldc.i4.2
0x13f1a  ldloc.s  4
0x13f1c  stelem.ref
0x13f1d  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x13f22  stloc.s  5
0x13f24  ldloc.s  5
0x13f26  ldc.i4.0
0x13f27  newarr   [mscorlib]System.Object
0x13f2c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x13f31  ldloc.s  5
0x13f33  ldloc.s  4
0x13f35  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x13f3a  throw
0x13f3b  ret
```
