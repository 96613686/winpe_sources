# Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::ScheduleFileReplacementOnReboot

- ea: `0x141c0`
- end: `0x1427d`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::ScheduleFileReplacementOnReboot`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x13970`
- `0x14110`
- `0x141c0`
- `0x143e0`
- `0x17d00`

## string_xrefs

- `0x141dd`: `    Moved locked file to temp folder for deletion on reboot. Temp filename: {0}`
- `0x14203`: `    scheduled deletion of file from temp folder on reboot`
- `0x14216`: `    Unable to move file to temp folder for delete on reboot: {0}`
- `0x14239`: `    Replaced locked target file`
- `0x1424c`: `    Staging file to temporary holding folder for move after reboot: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x141c0  ldarg.0
0x141c1  ldarg.2
0x141c2  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::CreateTempFilePath(string finalTargetPath)
0x141c7  stloc.0
0x141c8  ldarg.2
0x141c9  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x141ce  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x141d3  brfalse.s loc_14231
0x141d5  ldarg.2
0x141d6  ldloc.0
0x141d7  ldnull
0x141d8  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFile(string source, string target, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x141dd  ldstr    aMovedLockedFil// "    Moved locked file to temp folder fo"...
0x141e2  ldc.i4.1
0x141e3  newarr   [mscorlib]System.Object
0x141e8  dup
0x141e9  ldc.i4.0
0x141ea  ldloc.0
0x141eb  stelem.ref
0x141ec  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x141f1  ldarg.0
0x141f2  call     instance class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_UncommittedFileReplacements()
0x141f7  ldloc.0
0x141f8  ldnull
0x141f9  newobj   instance void DeferredFileReplacementDescriptor::.ctor(string stagedFilePath, string targetFilePath)
0x141fe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor>::Add(var<u1>)
0x14203  ldstr    aScheduledDelet// "    scheduled deletion of file from tem"...
0x14208  ldc.i4.0
0x14209  newarr   [mscorlib]System.Object
0x1420e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x14213  leave.s  loc_14231
0x14215  stloc.1
0x14216  ldstr    aUnableToMoveFi// "    Unable to move file to temp folder "...
0x1421b  ldc.i4.1
0x1421c  newarr   [mscorlib]System.Object
0x14221  dup
0x14222  ldc.i4.0
0x14223  ldloc.1
0x14224  callvirt instance string [mscorlib]System.Exception::get_Message()
0x14229  stelem.ref
0x1422a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x1422f  rethrow
0x14231  ldarg.3
0x14232  ldarg.1
0x14233  ldarg.2
0x14234  callvirt instance void class Microsoft.Crm.Setup.Common.OnlinePackageSupport.PopulateHoldingFile`1<mvar<u1>>::Invoke(var<u1>, !!T0)
0x14239  ldstr    aReplacedLocked// "    Replaced locked target file"
0x1423e  ldc.i4.0
0x1423f  newarr   [mscorlib]System.Object
0x14244  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x14249  leave.s  loc_1427C
0x1424b  pop
0x1424c  ldstr    aStagingFileToT// "    Staging file to temporary holding f"...
0x14251  ldc.i4.1
0x14252  newarr   [mscorlib]System.Object
0x14257  dup
0x14258  ldc.i4.0
0x14259  ldloc.0
0x1425a  stelem.ref
0x1425b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x14260  ldarg.3
0x14261  ldarg.1
0x14262  ldloc.0
0x14263  callvirt instance void class Microsoft.Crm.Setup.Common.OnlinePackageSupport.PopulateHoldingFile`1<mvar<u1>>::Invoke(var<u1>, !!T0)
0x14268  ldarg.0
0x14269  call     instance class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_UncommittedFileReplacements()
0x1426e  ldloc.0
0x1426f  ldarg.2
0x14270  newobj   instance void DeferredFileReplacementDescriptor::.ctor(string stagedFilePath, string targetFilePath)
0x14275  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor>::Add(var<u1>)
0x1427a  leave.s  loc_1427C
0x1427c  ret
```
