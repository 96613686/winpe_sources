# Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::Execute

- ea: `0x13580`
- end: `0x137e2`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::Execute`
- size: `610`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x15500`
- `0x16190`

## callees

- `0x133d0`
- `0x133f0`
- `0x13420`
- `0x13450`
- `0x13580`
- `0x137f0`
- `0x13970`
- `0x13a20`
- `0x13bc0`
- `0x13cb0`
- `0x13e30`
- `0x13f40`

## string_xrefs

- `0x135fa`: `FileCopy source file not found: {0}`
- `0x13641`: `FileMove source file not found: {0}`
- `0x136a1`: `FileDelete target file not found: {0}`
- `0x136d7`: `DirectoryTreeMirror source directory not found: {0}`
- `0x13714`: `DirectoryTreeReplace source directory not found: {0}`
- `0x13751`: `DirectoryStructureMerge source directory not found: {0}`
- `0x1378d`: `DirectoryReplaceFiles source directory not found: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x13580  ldstr    aExecutingFiles// "Executing FileSystemOperation - OpCode:"...
0x13585  ldc.i4.3
0x13586  newarr   [mscorlib]System.Object
0x1358b  dup
0x1358c  ldc.i4.0
0x1358d  ldarg.0
0x1358e  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Operation()
0x13593  stloc.0
0x13594  ldloca.s 0
0x13596  constrained. Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode
0x1359c  callvirt instance string [mscorlib]System.Object::ToString()
0x135a1  stelem.ref
0x135a2  dup
0x135a3  ldc.i4.1
0x135a4  ldarg.0
0x135a5  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x135aa  stelem.ref
0x135ab  dup
0x135ac  ldc.i4.2
0x135ad  ldarg.0
0x135ae  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x135b3  stelem.ref
0x135b4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x135b9  ldarg.0
0x135ba  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::VerifyDescriptorConsistency()
0x135bf  ldarg.0
0x135c0  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Operation()
0x135c5  stloc.0
0x135c6  ldloc.0
0x135c7  ldc.i4.1
0x135c8  sub
0x135c9  switch   loc_135EF, loc_13636, loc_13696, loc_136CC, loc_13709, loc_13746, loc_13782
0x135ea  br       loc_137BE
0x135ef  ldarg.0
0x135f0  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x135f5  call     bool [mscorlib]System.IO.File::Exists(string)
0x135fa  ldstr    aFilecopySource// "FileCopy source file not found: {0}"
0x135ff  ldc.i4.1
0x13600  newarr   [mscorlib]System.Object
0x13605  dup
0x13606  ldc.i4.0
0x13607  ldarg.0
0x13608  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x1360d  stelem.ref
0x1360e  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x13613  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x13618  ldarg.0
0x13619  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x1361e  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::CreateParentDirectoryIfNotExist(string path)
0x13623  ldarg.0
0x13624  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x13629  ldarg.0
0x1362a  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x1362f  ldarg.1
0x13630  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::CopyFile(string source, string target, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13635  ret
0x13636  ldarg.0
0x13637  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x1363c  call     bool [mscorlib]System.IO.File::Exists(string)
0x13641  ldstr    aFilemoveSource// "FileMove source file not found: {0}"
0x13646  ldc.i4.1
0x13647  newarr   [mscorlib]System.Object
0x1364c  dup
0x1364d  ldc.i4.0
0x1364e  ldarg.0
0x1364f  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x13654  stelem.ref
0x13655  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x1365a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1365f  ldarg.0
0x13660  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x13665  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::CreateParentDirectoryIfNotExist(string path)
0x1366a  ldarg.0
0x1366b  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x13670  call     bool [mscorlib]System.IO.File::Exists(string)
0x13675  brfalse.s loc_13683
0x13677  ldarg.0
0x13678  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x1367d  ldarg.1
0x1367e  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteFile(string filePath, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13683  ldarg.0
0x13684  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x13689  ldarg.0
0x1368a  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x1368f  ldarg.1
0x13690  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFile(string source, string target, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13695  ret
0x13696  ldarg.0
0x13697  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x1369c  call     bool [mscorlib]System.IO.File::Exists(string)
0x136a1  ldstr    aFiledeleteTarg// "FileDelete target file not found: {0}"
0x136a6  ldc.i4.1
0x136a7  newarr   [mscorlib]System.Object
0x136ac  dup
0x136ad  ldc.i4.0
0x136ae  ldarg.0
0x136af  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x136b4  stelem.ref
0x136b5  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x136ba  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x136bf  ldarg.0
0x136c0  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x136c5  ldarg.1
0x136c6  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteFile(string filePath, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x136cb  ret
0x136cc  ldarg.0
0x136cd  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x136d2  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x136d7  ldstr    aDirectorytreem// "DirectoryTreeMirror source directory no"...
0x136dc  ldc.i4.1
0x136dd  newarr   [mscorlib]System.Object
0x136e2  dup
0x136e3  ldc.i4.0
0x136e4  ldarg.0
0x136e5  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x136ea  stelem.ref
0x136eb  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x136f0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x136f5  ldarg.0
0x136f6  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x136fb  ldarg.0
0x136fc  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x13701  ldarg.1
0x13702  ldc.i4.1
0x13703  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::ReplaceDirectoryTree(string source, string target, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler, bool keepOriginal)
0x13708  ret
0x13709  ldarg.0
0x1370a  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x1370f  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x13714  ldstr    aDirectorytreer// "DirectoryTreeReplace source directory n"...
0x13719  ldc.i4.1
0x1371a  newarr   [mscorlib]System.Object
0x1371f  dup
0x13720  ldc.i4.0
0x13721  ldarg.0
0x13722  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x13727  stelem.ref
0x13728  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x1372d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x13732  ldarg.0
0x13733  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x13738  ldarg.0
0x13739  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x1373e  ldarg.1
0x1373f  ldc.i4.0
0x13740  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::ReplaceDirectoryTree(string source, string target, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler, bool keepOriginal)
0x13745  ret
0x13746  ldarg.0
0x13747  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x1374c  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x13751  ldstr    aDirectorystruc// "DirectoryStructureMerge source director"...
0x13756  ldc.i4.1
0x13757  newarr   [mscorlib]System.Object
0x1375c  dup
0x1375d  ldc.i4.0
0x1375e  ldarg.0
0x1375f  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x13764  stelem.ref
0x13765  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x1376a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1376f  ldarg.0
0x13770  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x13775  ldarg.0
0x13776  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x1377b  ldarg.1
0x1377c  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MergeDirectoryStructure(string source, string target, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13781  ret
0x13782  ldarg.0
0x13783  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x13788  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x1378d  ldstr    aDirectoryrepla// "DirectoryReplaceFiles source directory "...
0x13792  ldc.i4.1
0x13793  newarr   [mscorlib]System.Object
0x13798  dup
0x13799  ldc.i4.0
0x1379a  ldarg.0
0x1379b  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x137a0  stelem.ref
0x137a1  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x137a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x137ab  ldarg.0
0x137ac  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x137b1  ldarg.0
0x137b2  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x137b7  ldarg.1
0x137b8  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::ReplaceFilesInDirectory(string source, string target, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x137bd  ret
0x137be  ldstr    aFilesystemoper// "FileSystemOperationCode.{0} is not supp"...
0x137c3  ldc.i4.1
0x137c4  newarr   [mscorlib]System.Object
0x137c9  dup
0x137ca  ldc.i4.0
0x137cb  ldarg.0
0x137cc  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Operation()
0x137d1  box      Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode
0x137d6  stelem.ref
0x137d7  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x137dc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x137e1  throw
```
