# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::StagePackage

- ea: `0x15340`
- end: `0x15500`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::StagePackage`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x150b0`

## callees

- `0x131a0`
- `0x131f0`
- `0x13210`
- `0x13b00`
- `0x14750`
- `0x14f40`
- `0x15040`
- `0x15060`
- `0x15070`
- `0x15340`
- `0x15610`
- `0x15a10`
- `0x16450`

## string_xrefs

- `0x1547e`: `Deleting staging directory {0}`
- `0x1534d`: `Deleting existing staging directory {0}`
- `0x15371`: `Creating staging directory {0}`
- `0x154b0`: `Error occured deleting staging directory {0} - {1}`

## pseudocode

```c

```

## disassembly

```asm
0x15340  ldarg.0
0x15341  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectoryPath()
0x15346  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x1534b  brfalse.s loc_15371
0x1534d  ldstr    aDeletingExisti// "Deleting existing staging directory {0}"
0x15352  ldc.i4.1
0x15353  newarr   [mscorlib]System.Object
0x15358  dup
0x15359  ldc.i4.0
0x1535a  ldarg.0
0x1535b  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectoryPath()
0x15360  stelem.ref
0x15361  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15366  ldarg.0
0x15367  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectoryPath()
0x1536c  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteDirectory(string directoryPath)
0x15371  ldstr    aCreatingStagin// "Creating staging directory {0}"
0x15376  ldc.i4.1
0x15377  newarr   [mscorlib]System.Object
0x1537c  dup
0x1537d  ldc.i4.0
0x1537e  ldarg.0
0x1537f  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectoryPath()
0x15384  stelem.ref
0x15385  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1538a  ldarg.0
0x1538b  ldarg.0
0x1538c  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectoryPath()
0x15391  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x15396  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_StagingDirectory(class [mscorlib]System.IO.DirectoryInfo value)
0x1539b  ldarg.0
0x1539c  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_PackageName()
0x153a1  newobj   instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::.ctor(string packageName)
0x153a6  stloc.0
0x153a7  ldstr    aBeginStagingFi// "--------------------------------- Begin"...
0x153ac  ldc.i4.1
0x153ad  newarr   [mscorlib]System.Object
0x153b2  dup
0x153b3  ldc.i4.0
0x153b4  ldarg.0
0x153b5  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectoryPath()
0x153ba  stelem.ref
0x153bb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x153c0  ldarg.1
0x153c1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::get_AllPackages()
0x153c6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor>::GetEnumerator()
0x153cb  stloc.1
0x153cc  br.s     loc_153DC
0x153ce  ldloc.1
0x153cf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor>::get_Current()
0x153d4  stloc.2
0x153d5  ldarg.0
0x153d6  ldloc.2
0x153d7  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::StagePackageFiles(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor packageDescriptor)
0x153dc  ldloc.1
0x153dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x153e2  brtrue.s loc_153CE
0x153e4  leave.s  loc_153F0
0x153e6  ldloc.1
0x153e7  brfalse.s loc_153EF
0x153e9  ldloc.1
0x153ea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x153ef  endfinally
0x153f0  ldloc.0
0x153f1  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_FileSystemOperations()
0x153f6  ldarg.0
0x153f7  ldarg.1
0x153f8  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::BuildFileSystemCommitOperationList(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList packingList)
0x153fd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x15402  ldarg.1
0x15403  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::get_AllPackages()
0x15408  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor>::GetEnumerator()
0x1540d  stloc.1
0x1540e  br.s     loc_15428
0x15410  ldloc.1
0x15411  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor>::get_Current()
0x15416  stloc.3
0x15417  ldloc.0
0x15418  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_RegistryOperations()
0x1541d  ldloc.3
0x1541e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::get_RegistryOperations()
0x15423  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x15428  ldloc.1
0x15429  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1542e  brtrue.s loc_15410
0x15430  leave.s  loc_1543C
0x15432  ldloc.1
0x15433  brfalse.s loc_1543B
0x15435  ldloc.1
0x15436  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1543b  endfinally
0x1543c  ldstr    aDoneStagingFil// "--------------------------------- Done "...
0x15441  ldc.i4.1
0x15442  newarr   [mscorlib]System.Object
0x15447  dup
0x15448  ldc.i4.0
0x15449  ldarg.0
0x1544a  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectoryPath()
0x1544f  stelem.ref
0x15450  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15455  leave    loc_154FE
0x1545a  stloc.s  4
0x1545c  ldstr    aErrorEncounter// "Error encountered when staging package:"...
0x15461  ldc.i4.1
0x15462  newarr   [mscorlib]System.Object
0x15467  dup
0x15468  ldc.i4.0
0x15469  ldloc.s  4
0x1546b  callvirt instance string [mscorlib]System.Object::ToString()
0x15470  stelem.ref
0x15471  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x15476  ldarg.0
0x15477  call     instance class [mscorlib]System.IO.DirectoryInfo Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectory()
0x1547c  brfalse.s loc_154DC
0x1547e  ldstr    aDeletingStagin// "Deleting staging directory {0}"
0x15483  ldc.i4.1
0x15484  newarr   [mscorlib]System.Object
0x15489  dup
0x1548a  ldc.i4.0
0x1548b  ldarg.0
0x1548c  call     instance class [mscorlib]System.IO.DirectoryInfo Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectory()
0x15491  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x15496  stelem.ref
0x15497  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1549c  ldarg.0
0x1549d  call     instance class [mscorlib]System.IO.DirectoryInfo Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectory()
0x154a2  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x154a7  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteDirectory(string directoryPath)
0x154ac  leave.s  loc_154D5
0x154ae  stloc.s  5
0x154b0  ldstr    aErrorOccuredDe// "Error occured deleting staging director"...
0x154b5  ldc.i4.2
0x154b6  newarr   [mscorlib]System.Object
0x154bb  dup
0x154bc  ldc.i4.0
0x154bd  ldarg.0
0x154be  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectoryPath()
0x154c3  stelem.ref
0x154c4  dup
0x154c5  ldc.i4.1
0x154c6  ldloc.s  5
0x154c8  callvirt instance string [mscorlib]System.Object::ToString()
0x154cd  stelem.ref
0x154ce  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x154d3  leave.s  loc_154D5
0x154d5  ldarg.0
0x154d6  ldnull
0x154d7  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_StagingDirectory(class [mscorlib]System.IO.DirectoryInfo value)
0x154dc  ldstr    aErrorEncounter// "Error encountered when staging package:"...
0x154e1  ldc.i4.1
0x154e2  newarr   [mscorlib]System.Object
0x154e7  dup
0x154e8  ldc.i4.0
0x154e9  ldloc.s  4
0x154eb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x154f0  stelem.ref
0x154f1  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x154f6  ldloc.s  4
0x154f8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x154fd  throw
0x154fe  ldloc.0
0x154ff  ret
```
