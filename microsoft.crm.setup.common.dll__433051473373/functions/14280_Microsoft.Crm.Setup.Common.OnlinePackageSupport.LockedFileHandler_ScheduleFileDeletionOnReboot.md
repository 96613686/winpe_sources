# Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::ScheduleFileDeletionOnReboot

- ea: `0x14280`
- end: `0x142d9`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::ScheduleFileDeletionOnReboot`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x13a20`

## callees

- `0x13970`
- `0x14110`
- `0x14280`
- `0x143e0`
- `0x17d00`

## string_xrefs

- `0x1429d`: `    Moved locked file to temp folder for deletion on reboot: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x14280  ldarg.1
0x14281  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x14286  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x1428b  brfalse.s loc_142C4
0x1428d  ldarg.0
0x1428e  ldarg.1
0x1428f  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::CreateTempFilePath(string finalTargetPath)
0x14294  stloc.0
0x14295  ldarg.1
0x14296  ldloc.0
0x14297  ldnull
0x14298  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFile(string source, string target, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x1429d  ldstr    aMovedLockedFil_0// "    Moved locked file to temp folder fo"...
0x142a2  ldc.i4.1
0x142a3  newarr   [mscorlib]System.Object
0x142a8  dup
0x142a9  ldc.i4.0
0x142aa  ldloc.0
0x142ab  stelem.ref
0x142ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x142b1  ldarg.0
0x142b2  call     instance class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_UncommittedFileReplacements()
0x142b7  ldloc.0
0x142b8  ldnull
0x142b9  newobj   instance void DeferredFileReplacementDescriptor::.ctor(string stagedFilePath, string targetFilePath)
0x142be  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor>::Add(var<u1>)
0x142c3  ret
0x142c4  ldstr    aSchedulefilede// "ScheduleFileDeletionOnReboot - File not"...
0x142c9  ldc.i4.1
0x142ca  newarr   [mscorlib]System.Object
0x142cf  dup
0x142d0  ldc.i4.0
0x142d1  ldarg.1
0x142d2  stelem.ref
0x142d3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x142d8  ret
```
