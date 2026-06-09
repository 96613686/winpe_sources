# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::BackupCurrentFilesReferencedInStagingDirectory

- ea: `0x16030`
- end: `0x160dd`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::BackupCurrentFilesReferencedInStagingDirectory`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x15d70`

## callees

- `0x131f0`
- `0x133b0`
- `0x133e0`
- `0x13400`
- `0x13430`
- `0x13f70`
- `0x14fe0`
- `0x156e0`
- `0x15700`
- `0x16030`

## pseudocode

```c

```

## disassembly

```asm
0x16030  ldarg.0
0x16031  ldarg.1
0x16032  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::GetStagingPathForInstallLocation(string installPointLocation)
0x16037  stloc.0
0x16038  ldloc.0
0x16039  ldstr    asc_1953A// "*"
0x1603e  ldc.i4.1
0x1603f  call     string[] [mscorlib]System.IO.Directory::GetFiles(string, string, valuetype [mscorlib]System.IO.SearchOption)
0x16044  stloc.1
0x16045  ldc.i4.0
0x16046  stloc.2
0x16047  br       loc_160D3
0x1604c  ldloc.1
0x1604d  ldloc.2
0x1604e  ldelem.ref
0x1604f  ldloc.0
0x16050  ldarg.1
0x16051  call     string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::GetPathRelativeToTarget(string fullSourcePath, string sourceDirectoryPath, string targetDirectoryPath)
0x16056  stloc.3
0x16057  ldloc.3
0x16058  call     bool [mscorlib]System.IO.File::Exists(string)
0x1605d  brfalse.s loc_160CF
0x1605f  ldarg.0
0x16060  ldloc.3
0x16061  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::GetBackupPathForInstallLocation(string installPointLocation)
0x16066  stloc.s  4
0x16068  ldloc.s  4
0x1606a  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x1606f  stloc.s  5
0x16071  ldloc.s  5
0x16073  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x16078  brtrue.s loc_16082
0x1607a  ldloc.s  5
0x1607c  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x16081  pop
0x16082  ldstr    aBackingUpFileF// "Backing up file from {0} to {1}"
0x16087  ldc.i4.2
0x16088  newarr   [mscorlib]System.Object
0x1608d  dup
0x1608e  ldc.i4.0
0x1608f  ldloc.3
0x16090  stelem.ref
0x16091  dup
0x16092  ldc.i4.1
0x16093  ldloc.s  4
0x16095  stelem.ref
0x16096  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1609b  ldloc.3
0x1609c  ldloc.s  4
0x1609e  ldc.i4.1
0x1609f  call     void [mscorlib]System.IO.File::Copy(string, string, bool)
0x160a4  ldarg.0
0x160a5  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_RollbackDescriptor()
0x160aa  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_FileSystemOperations()
0x160af  newobj   instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::.ctor()
0x160b4  dup
0x160b5  ldc.i4.1
0x160b6  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Operation(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode value)
0x160bb  dup
0x160bc  ldloc.s  4
0x160be  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Source(string value)
0x160c3  dup
0x160c4  ldloc.3
0x160c5  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Target(string value)
0x160ca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::Add(var<u1>)
0x160cf  ldloc.2
0x160d0  ldc.i4.1
0x160d1  add
0x160d2  stloc.2
0x160d3  ldloc.2
0x160d4  ldloc.1
0x160d5  ldlen
0x160d6  conv.i4
0x160d7  blt      loc_1604C
0x160dc  ret
```
