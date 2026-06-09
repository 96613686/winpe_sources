# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::Commit

- ea: `0x15500`
- end: `0x15603`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::Commit`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x150b0`

## callees

- `0x131f0`
- `0x13210`
- `0x13580`
- `0x14120`
- `0x142e0`
- `0x14f40`
- `0x14f90`
- `0x15020`
- `0x15040`
- `0x15500`
- `0x15990`
- `0x16190`

## string_xrefs

- `0x15500`: `================================= Begin committing staged operations =================================`
- `0x1552b`: `Commit staged file operations`
- `0x15572`: `Error occured while committing staged file operations - {0}`
- `0x155b4`: `================================= Done committing staged operations =================================`
- `0x155d0`: `Error occured during Commit phase - {0}`

## pseudocode

```c

```

## disassembly

```asm
0x15500  ldstr    aBeginCommittin// "================================= Begin"...
0x15505  ldc.i4.1
0x15506  newarr   [mscorlib]System.Object
0x1550b  dup
0x1550c  ldc.i4.0
0x1550d  ldarg.0
0x1550e  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectoryPath()
0x15513  stelem.ref
0x15514  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15519  ldarg.0
0x1551a  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_DeploymentSupportDirectoryPath()
0x1551f  ldarg.0
0x15520  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_PackageName()
0x15525  newobj   instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::.ctor(string preferredRootPath, string nameTag)
0x1552a  stloc.0
0x1552b  ldstr    aCommitStagedFi// "Commit staged file operations"
0x15530  ldc.i4.0
0x15531  newarr   [mscorlib]System.Object
0x15536  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1553b  ldarg.1
0x1553c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_FileSystemOperations()
0x15541  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::GetEnumerator()
0x15546  stloc.1
0x15547  br.s     loc_15556
0x15549  ldloca.s 1
0x1554b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::get_Current()
0x15550  ldloc.0
0x15551  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::Execute(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x15556  ldloca.s 1
0x15558  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::MoveNext()
0x1555d  brtrue.s loc_15549
0x1555f  leave.s  loc_1556F
0x15561  ldloca.s 1
0x15563  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>
0x15569  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1556e  endfinally
0x1556f  leave.s  loc_1558D
0x15571  stloc.2
0x15572  ldstr    aErrorOccuredWh_2// "Error occured while committing staged f"...
0x15577  ldc.i4.1
0x15578  newarr   [mscorlib]System.Object
0x1557d  dup
0x1557e  ldc.i4.0
0x1557f  ldloc.2
0x15580  callvirt instance string [mscorlib]System.Object::ToString()
0x15585  stelem.ref
0x15586  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x1558b  rethrow
0x1558d  ldarg.0
0x1558e  ldarg.1
0x1558f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_RegistryOperations()
0x15594  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::ApplyRegistrySettings(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation> registryOperations)
0x15599  ldloc.0
0x1559a  callvirt instance int32 Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::Commit()
0x1559f  brfalse.s loc_155A8
0x155a1  ldarg.0
0x155a2  ldc.i4.1
0x155a3  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_RebootRequired(bool value)
0x155a8  leave.s  loc_155B4
0x155aa  ldloc.0
0x155ab  brfalse.s loc_155B3
0x155ad  ldloc.0
0x155ae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x155b3  endfinally
0x155b4  ldstr    aDoneCommitting// "================================= Done "...
0x155b9  ldc.i4.1
0x155ba  newarr   [mscorlib]System.Object
0x155bf  dup
0x155c0  ldc.i4.0
0x155c1  ldarg.0
0x155c2  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectoryPath()
0x155c7  stelem.ref
0x155c8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x155cd  leave.s  loc_15602
0x155cf  stloc.3
0x155d0  ldstr    aErrorOccuredDu// "Error occured during Commit phase - {0}"
0x155d5  ldc.i4.1
0x155d6  newarr   [mscorlib]System.Object
0x155db  dup
0x155dc  ldc.i4.0
0x155dd  ldloc.3
0x155de  callvirt instance string [mscorlib]System.Exception::get_Message()
0x155e3  stelem.ref
0x155e4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x155e9  ldstr    aRestoringFromB// "Restoring from backup"
0x155ee  ldc.i4.0
0x155ef  newarr   [mscorlib]System.Object
0x155f4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x155f9  ldarg.0
0x155fa  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::RestoreFromBackup()
0x155ff  pop
0x15600  leave.s  loc_15602
0x15602  ret
```
