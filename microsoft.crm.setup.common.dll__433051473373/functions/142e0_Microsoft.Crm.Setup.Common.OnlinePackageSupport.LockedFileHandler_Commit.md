# Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::Commit

- ea: `0x142e0`
- end: `0x143ce`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::Commit`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x15500`
- `0x16190`

## callees

- `0x140f0`
- `0x14100`
- `0x14110`
- `0x142e0`
- `0x144b0`
- `0x17cc0`
- `0x17ce0`

## string_xrefs

- `0x142f0`: `Committing scheduled replacement or removal of {0} locked files on next reboot`
- `0x14336`: `    Scheduling deletion of temp file: {0}`
- `0x143b7`: `No files scheduled for replacement on next reboot`

## pseudocode

```c

```

## disassembly

```asm
0x142e0  ldarg.0
0x142e1  call     instance class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_UncommittedFileReplacements()
0x142e6  call     T0x2B000015
0x142eb  brfalse  loc_143B7
0x142f0  ldstr    aCommittingSche// "Committing scheduled replacement or rem"...
0x142f5  ldc.i4.1
0x142f6  newarr   [mscorlib]System.Object
0x142fb  dup
0x142fc  ldc.i4.0
0x142fd  ldarg.0
0x142fe  call     instance class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_UncommittedFileReplacements()
0x14303  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor>::get_Count()
0x14308  box      [mscorlib]System.Int32
0x1430d  stelem.ref
0x1430e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x14313  ldarg.0
0x14314  call     instance class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_UncommittedFileReplacements()
0x14319  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor>::GetEnumerator()
0x1431e  stloc.0
0x1431f  br.s     loc_14391
0x14321  ldloca.s 0
0x14323  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DeferredFileReplacementDescriptor>::get_Current()
0x14328  stloc.1
0x14329  ldloc.1
0x1432a  callvirt instance string DeferredFileReplacementDescriptor::get_TargetFilePath()
0x1432f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x14334  brfalse.s loc_14351
0x14336  ldstr    aSchedulingDele// "    Scheduling deletion of temp file: {"...
0x1433b  ldc.i4.1
0x1433c  newarr   [mscorlib]System.Object
0x14341  dup
0x14342  ldc.i4.0
0x14343  ldloc.1
0x14344  callvirt instance string DeferredFileReplacementDescriptor::get_StagedFilePath()
0x14349  stelem.ref
0x1434a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1434f  br.s     loc_1437B
0x14351  ldstr    aStagedFile01Ta// "    Staged file: {0}{1}                "...
0x14356  ldc.i4.3
0x14357  newarr   [mscorlib]System.Object
0x1435c  dup
0x1435d  ldc.i4.0
0x1435e  ldloc.1
0x1435f  callvirt instance string DeferredFileReplacementDescriptor::get_StagedFilePath()
0x14364  stelem.ref
0x14365  dup
0x14366  ldc.i4.1
0x14367  call     string [mscorlib]System.Environment::get_NewLine()
0x1436c  stelem.ref
0x1436d  dup
0x1436e  ldc.i4.2
0x1436f  ldloc.1
0x14370  callvirt instance string DeferredFileReplacementDescriptor::get_TargetFilePath()
0x14375  stelem.ref
0x14376  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x1437b  ldloc.1
0x1437c  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::ScheduleReplacementOnReboot(class DeferredFileReplacementDescriptor moveDescriptor)
0x14381  ldarg.0
0x14382  call     instance int32 Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_CommittedFileReplacementCount()
0x14387  stloc.2
0x14388  ldarg.0
0x14389  ldloc.2
0x1438a  ldc.i4.1
0x1438b  add
0x1438c  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::set_CommittedFileReplacementCount(int32 value)
0x14391  ldloca.s 0
0x14393  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DeferredFileReplacementDescriptor>::MoveNext()
0x14398  brtrue.s loc_14321
0x1439a  leave.s  loc_143AA
0x1439c  ldloca.s 0
0x1439e  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DeferredFileReplacementDescriptor>
0x143a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x143a9  endfinally
0x143aa  ldarg.0
0x143ab  call     instance class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_UncommittedFileReplacements()
0x143b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor>::Clear()
0x143b5  br.s     loc_143C7
0x143b7  ldstr    aNoFilesSchedul// "No files scheduled for replacement on n"...
0x143bc  ldc.i4.0
0x143bd  newarr   [mscorlib]System.Object
0x143c2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x143c7  ldarg.0
0x143c8  call     instance int32 Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_CommittedFileReplacementCount()
0x143cd  ret
```
