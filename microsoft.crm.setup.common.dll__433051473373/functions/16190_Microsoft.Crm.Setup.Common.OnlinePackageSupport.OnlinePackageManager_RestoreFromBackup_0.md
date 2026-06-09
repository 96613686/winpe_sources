# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::RestoreFromBackup_0

- ea: `0x16190`
- end: `0x1630a`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::RestoreFromBackup_0`
- size: `378`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x15500`
- `0x160e0`

## callees

- `0x131f0`
- `0x13210`
- `0x13580`
- `0x13b00`
- `0x14120`
- `0x142e0`
- `0x14f40`
- `0x14f60`
- `0x14f70`
- `0x14f80`
- `0x14f90`
- `0x14fa0`
- `0x14fe0`
- `0x15020`
- `0x16190`
- `0x166f0`

## string_xrefs

- `0x16196`: `RollbackDescriptor property must be initialized`
- `0x16276`: `Removing backup folder {0} after rollback`
- `0x162b3`: `---------------- Restore completed -----------------`

## pseudocode

```c

```

## disassembly

```asm
0x16190  ldarg.0
0x16191  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_RollbackDescriptor()
0x16196  ldstr    aRollbackdescri_0// "RollbackDescriptor property must be ini"...
0x1619b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x161a0  ldstr    aBeginningResto// "---------------- Beginning restore from"...
0x161a5  ldc.i4.1
0x161a6  newarr   [mscorlib]System.Object
0x161ab  dup
0x161ac  ldc.i4.0
0x161ad  ldarg.0
0x161ae  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x161b3  stelem.ref
0x161b4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x161b9  ldarg.0
0x161ba  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_DeploymentSupportDirectoryPath()
0x161bf  ldarg.0
0x161c0  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_PackageName()
0x161c5  newobj   instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::.ctor(string preferredRootPath, string nameTag)
0x161ca  stloc.0
0x161cb  ldarg.0
0x161cc  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_RollbackDescriptor()
0x161d1  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_FileSystemOperations()
0x161d6  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::GetEnumerator()
0x161db  stloc.1
0x161dc  br.s     loc_161EB
0x161de  ldloca.s 1
0x161e0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::get_Current()
0x161e5  ldloc.0
0x161e6  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::Execute(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x161eb  ldloca.s 1
0x161ed  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::MoveNext()
0x161f2  brtrue.s loc_161DE
0x161f4  leave.s  loc_16204
0x161f6  ldloca.s 1
0x161f8  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>
0x161fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16203  endfinally
0x16204  ldarg.0
0x16205  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_RollbackDescriptor()
0x1620a  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_RegistryOperations()
0x1620f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation>::GetEnumerator()
0x16214  stloc.2
0x16215  br.s     loc_16224
0x16217  ldloca.s 2
0x16219  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation>::get_Current()
0x1621e  callvirt instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::Execute()
0x16223  pop
0x16224  ldloca.s 2
0x16226  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation>::MoveNext()
0x1622b  brtrue.s loc_16217
0x1622d  leave.s  loc_1623D
0x1622f  ldloca.s 2
0x16231  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation>
0x16237  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1623c  endfinally
0x1623d  ldloc.0
0x1623e  callvirt instance int32 Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::Commit()
0x16243  ldc.i4.0
0x16244  ble.s    loc_1624D
0x16246  ldarg.0
0x16247  ldc.i4.1
0x16248  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_RebootRequired(bool value)
0x1624d  leave.s  loc_16259
0x1624f  ldloc.0
0x16250  brfalse.s loc_16258
0x16252  ldloc.0
0x16253  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16258  endfinally
0x16259  ldarg.0
0x1625a  call     instance bool Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_RebootRequired()
0x1625f  brfalse.s loc_1626E
0x16261  ldarg.0
0x16262  ldc.i4   0xBC2
0x16267  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_ResultCode(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult value)
0x1626c  br.s     loc_16275
0x1626e  ldarg.0
0x1626f  ldc.i4.0
0x16270  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_ResultCode(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult value)
0x16275  nop
0x16276  ldstr    aRemovingBackup// "Removing backup folder {0} after rollba"...
0x1627b  ldc.i4.1
0x1627c  newarr   [mscorlib]System.Object
0x16281  dup
0x16282  ldc.i4.0
0x16283  ldarg.0
0x16284  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x16289  stelem.ref
0x1628a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1628f  ldarg.0
0x16290  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x16295  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteDirectory(string directoryPath)
0x1629a  leave.s  loc_162B3
0x1629c  stloc.3
0x1629d  ldstr    aCaughtExceptio_0// "Caught exception thrown when removing b"...
0x162a2  ldc.i4.1
0x162a3  newarr   [mscorlib]System.Object
0x162a8  dup
0x162a9  ldc.i4.0
0x162aa  ldloc.3
0x162ab  stelem.ref
0x162ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x162b1  leave.s  loc_162B3
0x162b3  ldstr    aRestoreComplet// "---------------- Restore completed ----"...
0x162b8  ldc.i4.0
0x162b9  newarr   [mscorlib]System.Object
0x162be  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x162c3  leave.s  loc_16303
0x162c5  stloc.s  4
0x162c7  ldstr    aErrorOccurredW_1// "Error occurred while restoring from bac"...
0x162cc  ldc.i4.1
0x162cd  newarr   [mscorlib]System.Object
0x162d2  dup
0x162d3  ldc.i4.0
0x162d4  ldloc.s  4
0x162d6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x162db  stelem.ref
0x162dc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x162e1  ldstr    aErrorOccurredW_1// "Error occurred while restoring from bac"...
0x162e6  ldc.i4.1
0x162e7  newarr   [mscorlib]System.Object
0x162ec  dup
0x162ed  ldc.i4.0
0x162ee  ldloc.s  4
0x162f0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x162f5  stelem.ref
0x162f6  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x162fb  ldloc.s  4
0x162fd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x16302  throw
0x16303  ldarg.0
0x16304  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_ResultCode()
0x16309  ret
```
