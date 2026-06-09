# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::InstallOnlinePackage

- ea: `0x150b0`
- end: `0x1524c`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::InstallOnlinePackage`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x13b00`
- `0x13bc0`
- `0x14770`
- `0x14f30`
- `0x14f60`
- `0x14f70`
- `0x14f80`
- `0x14fa0`
- `0x14fc0`
- `0x14fd0`
- `0x15040`
- `0x15060`
- `0x15070`
- `0x150b0`
- `0x15250`
- `0x15340`
- `0x15500`
- `0x15be0`
- `0x16360`

## string_xrefs

- `0x150b9`: `Begin installing onlinePackage from {0}`
- `0x1516a`: `Restoring old backup directory {0}`
- `0x151a5`: `Caught exception attempting to delete or restore old backup folder: {0}`
- `0x151c3`: `Deleting staging directory {0}`
- `0x151ef`: `MainEngineThread is returning {0:D}`

## pseudocode

```c

```

## disassembly

```asm
0x150b0  ldarg.0
0x150b1  ldarg.1
0x150b2  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::InitializeForInstallation(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList packingList)
0x150b7  ldc.i4.0
0x150b8  stloc.0
0x150b9  ldstr    aBeginInstallin// "Begin installing onlinePackage from {0}"
0x150be  ldc.i4.1
0x150bf  newarr   [mscorlib]System.Object
0x150c4  dup
0x150c5  ldc.i4.0
0x150c6  ldarg.0
0x150c7  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_PrimaryPackageDescriptor()
0x150cc  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::get_PackagePath()
0x150d1  stelem.ref
0x150d2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x150d7  ldarg.0
0x150d8  ldarg.1
0x150d9  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::StagePackage(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList packingList)
0x150de  stloc.1
0x150df  ldarg.0
0x150e0  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::TakeBackup()
0x150e5  ldarg.0
0x150e6  ldloc.1
0x150e7  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::Commit(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor stagedOperations)
0x150ec  ldc.i4.1
0x150ed  stloc.0
0x150ee  ldarg.0
0x150ef  call     instance bool Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_RebootRequired()
0x150f4  brfalse.s loc_15103
0x150f6  ldarg.0
0x150f7  ldc.i4   0xBC2
0x150fc  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_ResultCode(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult value)
0x15101  br.s     loc_1510A
0x15103  ldarg.0
0x15104  ldc.i4.0
0x15105  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_ResultCode(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult value)
0x1510a  leave    loc_15245
0x1510f  stloc.2
0x15110  ldarg.0
0x15111  ldstr    aExceptionOccur// "Exception occured while processing onli"...
0x15116  ldc.i4.1
0x15117  newarr   [mscorlib]System.Object
0x1511c  dup
0x1511d  ldc.i4.0
0x1511e  ldloc.2
0x1511f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x15124  stelem.ref
0x15125  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::Log(string format, object[] args)
0x1512a  rethrow
0x1512c  ldarg.0
0x1512d  call     instance class [mscorlib]System.IO.DirectoryInfo Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_OldBackupDirectory()
0x15132  brfalse  loc_151BB
0x15137  ldloc.0
0x15138  brfalse.s loc_1516A
0x1513a  ldstr    aDeletingOldBac// "Deleting old backup folder {0}"
0x1513f  ldc.i4.1
0x15140  newarr   [mscorlib]System.Object
0x15145  dup
0x15146  ldc.i4.0
0x15147  ldarg.0
0x15148  call     instance class [mscorlib]System.IO.DirectoryInfo Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_OldBackupDirectory()
0x1514d  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x15152  stelem.ref
0x15153  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15158  ldarg.0
0x15159  call     instance class [mscorlib]System.IO.DirectoryInfo Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_OldBackupDirectory()
0x1515e  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x15163  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteDirectory(string directoryPath)
0x15168  br.s     loc_1519B
0x1516a  ldstr    aRestoringOldBa// "Restoring old backup directory {0}"
0x1516f  ldc.i4.1
0x15170  newarr   [mscorlib]System.Object
0x15175  dup
0x15176  ldc.i4.0
0x15177  ldarg.0
0x15178  call     instance class [mscorlib]System.IO.DirectoryInfo Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_OldBackupDirectory()
0x1517d  stelem.ref
0x1517e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15183  ldarg.0
0x15184  call     instance class [mscorlib]System.IO.DirectoryInfo Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_OldBackupDirectory()
0x15189  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x1518e  ldarg.0
0x1518f  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x15194  ldnull
0x15195  ldc.i4.0
0x15196  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::ReplaceDirectoryTree(string source, string target, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler, bool keepOriginal)
0x1519b  ldarg.0
0x1519c  ldnull
0x1519d  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_OldBackupDirectory(class [mscorlib]System.IO.DirectoryInfo value)
0x151a2  leave.s  loc_151BB
0x151a4  stloc.3
0x151a5  ldstr    aCaughtExceptio// "Caught exception attempting to delete o"...
0x151aa  ldc.i4.1
0x151ab  newarr   [mscorlib]System.Object
0x151b0  dup
0x151b1  ldc.i4.0
0x151b2  ldloc.3
0x151b3  stelem.ref
0x151b4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x151b9  leave.s  loc_151BB
0x151bb  ldarg.0
0x151bc  call     instance class [mscorlib]System.IO.DirectoryInfo Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectory()
0x151c1  brfalse.s loc_151EE
0x151c3  ldstr    aDeletingStagin// "Deleting staging directory {0}"
0x151c8  ldc.i4.1
0x151c9  newarr   [mscorlib]System.Object
0x151ce  dup
0x151cf  ldc.i4.0
0x151d0  ldarg.0
0x151d1  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectoryPath()
0x151d6  stelem.ref
0x151d7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x151dc  ldarg.0
0x151dd  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectoryPath()
0x151e2  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteDirectory(string directoryPath)
0x151e7  ldarg.0
0x151e8  ldnull
0x151e9  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_StagingDirectory(class [mscorlib]System.IO.DirectoryInfo value)
0x151ee  ldarg.0
0x151ef  ldstr    aMainenginethre// "MainEngineThread is returning {0:D}"
0x151f4  ldc.i4.1
0x151f5  newarr   [mscorlib]System.Object
0x151fa  dup
0x151fb  ldc.i4.0
0x151fc  ldarg.0
0x151fd  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_ResultCode()
0x15202  box      Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult
0x15207  stelem.ref
0x15208  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::Log(string format, object[] args)
0x1520d  ldarg.0
0x1520e  ldstr    aOnlinepackagem// "OnlinePackageManager result: {0}, value"...
0x15213  ldc.i4.2
0x15214  newarr   [mscorlib]System.Object
0x15219  dup
0x1521a  ldc.i4.0
0x1521b  ldarg.0
0x1521c  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_ResultCode()
0x15221  stloc.s  4
0x15223  ldloca.s 4
0x15225  constrained. Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult
0x1522b  callvirt instance string [mscorlib]System.Object::ToString()
0x15230  stelem.ref
0x15231  dup
0x15232  ldc.i4.1
0x15233  ldarg.0
0x15234  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_ResultCode()
0x15239  box      [mscorlib]System.Int32
0x1523e  stelem.ref
0x1523f  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::Log(string format, object[] args)
0x15244  endfinally
0x15245  ldarg.0
0x15246  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_ResultCode()
0x1524b  ret
```
