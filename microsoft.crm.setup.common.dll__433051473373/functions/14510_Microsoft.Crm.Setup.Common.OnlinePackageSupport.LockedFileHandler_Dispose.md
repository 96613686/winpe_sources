# Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::Dispose

- ea: `0x14510`
- end: `0x1468b`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::Dispose`
- size: `379`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x14010`
- `0x14090`
- `0x140b0`
- `0x140c0`
- `0x140f0`
- `0x14110`
- `0x14510`
- `0x17cc0`

## string_xrefs

- `0x14530`: `Discarding {0} staged but not committed deferred file replacements`
- `0x145d9`: `Temporary holding folder contains {0} files for move after reboot.  Schedule folder deletion on system reboot`
- `0x14607`: `Failure calling MoveFileEx to schedule deletion of temporary holding folder {0} on reboot. HResult = 0x{1:X8}, Exception: {2}`
- `0x14644`: `No files scheduled for move after reboot.  Deleting temporary holding folder {0}`
- `0x1466c`: `Exception thrown when attempting to delete staging folder: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x14510  ldarg.0
0x14511  ldfld    bool Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::_disposed
0x14516  brfalse.s loc_14519
0x14518  ret
0x14519  ldarg.0
0x1451a  ldc.i4.1
0x1451b  stfld    bool Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::_disposed
0x14520  ldarg.0
0x14521  call     instance class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_UncommittedFileReplacements()
0x14526  call     T0x2B000015
0x1452b  brfalse  loc_145D0
0x14530  ldstr    aDiscarding0Sta// "Discarding {0} staged but not committed"...
0x14535  ldc.i4.1
0x14536  newarr   [mscorlib]System.Object
0x1453b  dup
0x1453c  ldc.i4.0
0x1453d  ldarg.0
0x1453e  call     instance class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_UncommittedFileReplacements()
0x14543  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor>::get_Count()
0x14548  box      [mscorlib]System.Int32
0x1454d  stelem.ref
0x1454e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x14553  ldarg.0
0x14554  call     instance class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_UncommittedFileReplacements()
0x14559  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor>::GetEnumerator()
0x1455e  stloc.0
0x1455f  br.s     loc_145B7
0x14561  ldloca.s 0
0x14563  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DeferredFileReplacementDescriptor>::get_Current()
0x14568  stloc.1
0x14569  ldloc.1
0x1456a  callvirt instance string DeferredFileReplacementDescriptor::get_StagedFilePath()
0x1456f  call     void [mscorlib]System.IO.File::Delete(string)
0x14574  leave.s  loc_145B7
0x14576  stloc.2
0x14577  ldstr    aErrorDeletingS// "Error deleting staged file {0}.  {1}: {"...
0x1457c  ldc.i4.4
0x1457d  newarr   [mscorlib]System.Object
0x14582  dup
0x14583  ldc.i4.0
0x14584  ldloc.1
0x14585  callvirt instance string DeferredFileReplacementDescriptor::get_StagedFilePath()
0x1458a  stelem.ref
0x1458b  dup
0x1458c  ldc.i4.1
0x1458d  ldloc.2
0x1458e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x14593  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x14598  stelem.ref
0x14599  dup
0x1459a  ldc.i4.2
0x1459b  ldloc.2
0x1459c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x145a1  stelem.ref
0x145a2  dup
0x145a3  ldc.i4.3
0x145a4  ldloc.2
0x145a5  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x145aa  box      [mscorlib]System.Int32
0x145af  stelem.ref
0x145b0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x145b5  leave.s  loc_145B7
0x145b7  ldloca.s 0
0x145b9  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DeferredFileReplacementDescriptor>::MoveNext()
0x145be  brtrue.s loc_14561
0x145c0  leave.s  loc_145D0
0x145c2  ldloca.s 0
0x145c4  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DeferredFileReplacementDescriptor>
0x145ca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x145cf  endfinally
0x145d0  nop
0x145d1  ldarg.0
0x145d2  call     instance int32 Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_CommittedFileReplacementCount()
0x145d7  brfalse.s loc_14644
0x145d9  ldstr    aTemporaryHoldi// "Temporary holding folder contains {0} f"...
0x145de  ldc.i4.1
0x145df  newarr   [mscorlib]System.Object
0x145e4  dup
0x145e5  ldc.i4.0
0x145e6  ldarg.0
0x145e7  call     instance int32 Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_CommittedFileReplacementCount()
0x145ec  box      [mscorlib]System.Int32
0x145f1  stelem.ref
0x145f2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x145f7  ldarg.0
0x145f8  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_LockedFileTempDirectoryPath()
0x145fd  ldnull
0x145fe  ldc.i4.4
0x145ff  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFileEx(string existingFileName, string newFileName, valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.MoveFileExFlags flags)
0x14604  leave.s  loc_14668
0x14606  stloc.3
0x14607  ldstr    aFailureCalling// "Failure calling MoveFileEx to schedule "...
0x1460c  ldc.i4.3
0x1460d  newarr   [mscorlib]System.Object
0x14612  dup
0x14613  ldc.i4.0
0x14614  ldarg.0
0x14615  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_LockedFileTempDirectoryPath()
0x1461a  stelem.ref
0x1461b  dup
0x1461c  ldc.i4.1
0x1461d  ldloc.3
0x1461e  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x14623  box      [mscorlib]System.Int32
0x14628  stelem.ref
0x14629  dup
0x1462a  ldc.i4.2
0x1462b  ldloc.3
0x1462c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x14631  stelem.ref
0x14632  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x14637  ldc.i4.0
0x14638  newarr   [mscorlib]System.Object
0x1463d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x14642  leave.s  loc_14668
0x14644  ldstr    aNoFilesSchedul_0// "No files scheduled for move after reboo"...
0x14649  ldc.i4.1
0x1464a  newarr   [mscorlib]System.Object
0x1464f  dup
0x14650  ldc.i4.0
0x14651  ldarg.0
0x14652  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_LockedFileTempDirectoryPath()
0x14657  stelem.ref
0x14658  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1465d  ldarg.0
0x1465e  call     instance class [mscorlib]System.IO.DirectoryInfo Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_LockedFileTempDirectory()
0x14663  callvirt instance void [mscorlib]System.IO.FileSystemInfo::Delete()
0x14668  leave.s  loc_14683
0x1466a  stloc.s  4
0x1466c  ldstr    aExceptionThrow_2// "Exception thrown when attempting to del"...
0x14671  ldc.i4.1
0x14672  newarr   [mscorlib]System.Object
0x14677  dup
0x14678  ldc.i4.0
0x14679  ldloc.s  4
0x1467b  stelem.ref
0x1467c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x14681  leave.s  loc_14683
0x14683  ldarg.0
0x14684  ldnull
0x14685  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::set_LockedFileTempDirectory(class [mscorlib]System.IO.DirectoryInfo value)
0x1468a  ret
```
