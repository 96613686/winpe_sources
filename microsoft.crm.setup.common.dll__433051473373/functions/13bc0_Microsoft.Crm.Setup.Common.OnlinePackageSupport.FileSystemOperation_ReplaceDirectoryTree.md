# Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::ReplaceDirectoryTree

- ea: `0x13bc0`
- end: `0x13ca6`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::ReplaceDirectoryTree`
- size: `230`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x13580`
- `0x150b0`

## callees

- `0x137f0`
- `0x13970`
- `0x13b10`
- `0x13bc0`
- `0x13f40`
- `0x13f70`

## string_xrefs

- `0x13bc6`: `source directory must exist`
- `0x13bd8`: `Deleting directory tree {0}`
- `0x13bf3`: `Replace {0} with contents of {1}.  Files will be {2}.`
- `0x13c0b`: `moved`
- `0x13c6a`: `Exception thrown while moving directory contents from {0} to {1} - {2}.  Restoring files`

## pseudocode

```c

```

## disassembly

```asm
0x13bc0  ldarg.0
0x13bc1  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x13bc6  ldstr    aSourceDirector// "source directory must exist"
0x13bcb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x13bd0  ldarg.1
0x13bd1  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x13bd6  brfalse.s loc_13BF3
0x13bd8  ldstr    aDeletingDirect// "Deleting directory tree {0}"
0x13bdd  ldc.i4.1
0x13bde  newarr   [mscorlib]System.Object
0x13be3  dup
0x13be4  ldc.i4.0
0x13be5  ldarg.1
0x13be6  stelem.ref
0x13be7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x13bec  ldarg.1
0x13bed  ldarg.2
0x13bee  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteDirectory(string directoryPath, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13bf3  ldstr    aReplace0WithCo// "Replace {0} with contents of {1}.  File"...
0x13bf8  ldc.i4.3
0x13bf9  newarr   [mscorlib]System.Object
0x13bfe  dup
0x13bff  ldc.i4.0
0x13c00  ldarg.1
0x13c01  stelem.ref
0x13c02  dup
0x13c03  ldc.i4.1
0x13c04  ldarg.0
0x13c05  stelem.ref
0x13c06  dup
0x13c07  ldc.i4.2
0x13c08  ldarg.3
0x13c09  brtrue.s loc_13C12
0x13c0b  ldstr    aMoved// "moved"
0x13c10  br.s     loc_13C17
0x13c12  ldstr    aCopied// "copied"
0x13c17  stelem.ref
0x13c18  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x13c1d  ldarg.0
0x13c1e  ldstr    asc_1953A// "*"
0x13c23  ldc.i4.1
0x13c24  call     string[] [mscorlib]System.IO.Directory::GetFiles(string, string, valuetype [mscorlib]System.IO.SearchOption)
0x13c29  stloc.0
0x13c2a  ldloc.0
0x13c2b  stloc.1
0x13c2c  ldc.i4.0
0x13c2d  stloc.2
0x13c2e  br.s     loc_13C60
0x13c30  ldloc.1
0x13c31  ldloc.2
0x13c32  ldelem.ref
0x13c33  stloc.3
0x13c34  ldloc.3
0x13c35  ldarg.0
0x13c36  ldarg.1
0x13c37  call     string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::GetPathRelativeToTarget(string fullSourcePath, string sourceDirectoryPath, string targetDirectoryPath)
0x13c3c  stloc.s  4
0x13c3e  ldloc.s  4
0x13c40  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::CreateParentDirectoryIfNotExist(string path)
0x13c45  ldarg.3
0x13c46  brfalse.s loc_13C53
0x13c48  ldloc.3
0x13c49  ldloc.s  4
0x13c4b  ldarg.2
0x13c4c  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::CopyFile(string source, string target, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13c51  br.s     loc_13C5C
0x13c53  ldloc.3
0x13c54  ldloc.s  4
0x13c56  ldarg.2
0x13c57  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFile(string source, string target, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13c5c  ldloc.2
0x13c5d  ldc.i4.1
0x13c5e  add
0x13c5f  stloc.2
0x13c60  ldloc.2
0x13c61  ldloc.1
0x13c62  ldlen
0x13c63  conv.i4
0x13c64  blt.s    loc_13C30
0x13c66  leave.s  loc_13CA5
0x13c68  stloc.s  5
0x13c6a  ldstr    aExceptionThrow_1// "Exception thrown while moving directory"...
0x13c6f  ldc.i4.3
0x13c70  newarr   [mscorlib]System.Object
0x13c75  dup
0x13c76  ldc.i4.0
0x13c77  ldarg.0
0x13c78  stelem.ref
0x13c79  dup
0x13c7a  ldc.i4.1
0x13c7b  ldarg.1
0x13c7c  stelem.ref
0x13c7d  dup
0x13c7e  ldc.i4.2
0x13c7f  ldloc.s  5
0x13c81  callvirt instance string [mscorlib]System.Exception::get_Message()
0x13c86  stelem.ref
0x13c87  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x13c8c  stloc.s  6
0x13c8e  ldloc.s  6
0x13c90  ldc.i4.0
0x13c91  newarr   [mscorlib]System.Object
0x13c96  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x13c9b  ldloc.s  6
0x13c9d  ldloc.s  5
0x13c9f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x13ca4  throw
0x13ca5  ret
```
