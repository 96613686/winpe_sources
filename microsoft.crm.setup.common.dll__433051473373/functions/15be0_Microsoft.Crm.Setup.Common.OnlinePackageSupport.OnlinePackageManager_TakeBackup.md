# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::TakeBackup

- ea: `0x15be0`
- end: `0x15d2f`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::TakeBackup`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x150b0`

## callees

- `0x131a0`
- `0x13b00`
- `0x14f30`
- `0x14f40`
- `0x14fa0`
- `0x14fc0`
- `0x14fd0`
- `0x14ff0`
- `0x15be0`
- `0x15d30`
- `0x15d70`

## string_xrefs

- `0x15bf6`: `primaryPackageDescriptor`
- `0x15c87`: `Unable to move existing backup folder in preparation for taking backup`
- `0x15cc3`: `---------------- Backup completed -----------------`
- `0x15cd6`: `Error occured when creating backup prior to installation of online package: {0}`
- `0x15cef`: `Deleting backup directory {0}`
- `0x15d16`: `Exception caught when attempting to delete backup directory: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x15be0  ldarg.0
0x15be1  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x15be6  ldstr    aBackupFolderMu// "backup folder must be specified"
0x15beb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x15bf0  ldarg.0
0x15bf1  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_PrimaryPackageDescriptor()
0x15bf6  ldstr    aPrimarypackage// "primaryPackageDescriptor"
0x15bfb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x15c00  ldarg.0
0x15c01  ldnull
0x15c02  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_OldBackupDirectory(class [mscorlib]System.IO.DirectoryInfo value)
0x15c07  ldarg.0
0x15c08  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x15c0d  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x15c12  brfalse  loc_15C99
0x15c17  ldarg.0
0x15c18  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x15c1d  ldstr    aOld// ".old"
0x15c22  call     string [mscorlib]System.String::Concat(string, string)
0x15c27  stloc.0
0x15c28  ldloc.0
0x15c29  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x15c2e  brfalse.s loc_15C4A
0x15c30  ldstr    aDeleting0// "Deleting {0}"
0x15c35  ldc.i4.1
0x15c36  newarr   [mscorlib]System.Object
0x15c3b  dup
0x15c3c  ldc.i4.0
0x15c3d  ldloc.0
0x15c3e  stelem.ref
0x15c3f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15c44  ldloc.0
0x15c45  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteDirectory(string directoryPath)
0x15c4a  ldstr    aMovingExisting// "Moving existing backup folder {0} to {1"...
0x15c4f  ldc.i4.2
0x15c50  newarr   [mscorlib]System.Object
0x15c55  dup
0x15c56  ldc.i4.0
0x15c57  ldarg.0
0x15c58  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x15c5d  stelem.ref
0x15c5e  dup
0x15c5f  ldc.i4.1
0x15c60  ldarg.0
0x15c61  call     instance class [mscorlib]System.IO.DirectoryInfo Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_OldBackupDirectory()
0x15c66  stelem.ref
0x15c67  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15c6c  ldarg.0
0x15c6d  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x15c72  ldloc.0
0x15c73  call     void [mscorlib]System.IO.Directory::Move(string, string)
0x15c78  ldarg.0
0x15c79  ldloc.0
0x15c7a  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x15c7f  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_OldBackupDirectory(class [mscorlib]System.IO.DirectoryInfo value)
0x15c84  leave.s  loc_15C99
0x15c86  pop
0x15c87  ldstr    aUnableToMoveEx// "Unable to move existing backup folder i"...
0x15c8c  ldc.i4.0
0x15c8d  newarr   [mscorlib]System.Object
0x15c92  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15c97  leave.s  loc_15C99
0x15c99  nop
0x15c9a  ldarg.0
0x15c9b  ldarg.0
0x15c9c  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_PackageName()
0x15ca1  newobj   instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::.ctor(string packageName)
0x15ca6  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_RollbackDescriptor(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor value)
0x15cab  ldarg.0
0x15cac  ldarg.0
0x15cad  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_PrimaryPackageDescriptor()
0x15cb2  ldarg.0
0x15cb3  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x15cb8  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::BackupInstallationPoints(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor packageDescriptor, string backupFolderBase)
0x15cbd  ldarg.0
0x15cbe  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::FlushRollbackDescriptor()
0x15cc3  ldstr    aBackupComplete// "---------------- Backup completed -----"...
0x15cc8  ldc.i4.0
0x15cc9  newarr   [mscorlib]System.Object
0x15cce  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15cd3  leave.s  loc_15D2E
0x15cd5  stloc.1
0x15cd6  ldstr    aErrorOccuredWh_3// "Error occured when creating backup prio"...
0x15cdb  ldc.i4.1
0x15cdc  newarr   [mscorlib]System.Object
0x15ce1  dup
0x15ce2  ldc.i4.0
0x15ce3  ldloc.1
0x15ce4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x15ce9  stelem.ref
0x15cea  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x15cef  ldstr    aDeletingBackup// "Deleting backup directory {0}"
0x15cf4  ldc.i4.1
0x15cf5  newarr   [mscorlib]System.Object
0x15cfa  dup
0x15cfb  ldc.i4.0
0x15cfc  ldarg.0
0x15cfd  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x15d02  stelem.ref
0x15d03  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15d08  ldarg.0
0x15d09  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x15d0e  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteDirectory(string directoryPath)
0x15d13  leave.s  loc_15D2C
0x15d15  stloc.2
0x15d16  ldstr    aExceptionCaugh_1// "Exception caught when attempting to del"...
0x15d1b  ldc.i4.1
0x15d1c  newarr   [mscorlib]System.Object
0x15d21  dup
0x15d22  ldc.i4.0
0x15d23  ldloc.2
0x15d24  stelem.ref
0x15d25  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15d2a  leave.s  loc_15D2C
0x15d2c  rethrow
0x15d2e  ret
```
