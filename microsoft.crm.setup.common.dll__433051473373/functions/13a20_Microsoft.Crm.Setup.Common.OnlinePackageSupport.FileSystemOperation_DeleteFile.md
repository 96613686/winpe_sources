# Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteFile

- ea: `0x13a20`
- end: `0x13af1`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteFile`
- size: `209`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x13580`
- `0x13b10`
- `0x13cb0`
- `0x13e50`

## callees

- `0x13a20`
- `0x14280`
- `0x143d0`

## string_xrefs

- `0x13a2f`: `DeleteFile - File {0} not found`

## pseudocode

```c

```

## disassembly

```asm
0x13a20  ldarg.0
0x13a21  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x13a26  stloc.0
0x13a27  ldloc.0
0x13a28  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x13a2d  brtrue.s loc_13A44
0x13a2f  ldstr    aDeletefileFile// "DeleteFile - File {0} not found"
0x13a34  ldc.i4.1
0x13a35  newarr   [mscorlib]System.Object
0x13a3a  dup
0x13a3b  ldc.i4.0
0x13a3c  ldarg.0
0x13a3d  stelem.ref
0x13a3e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x13a43  ret
0x13a44  ldloc.0
0x13a45  callvirt instance valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.FileSystemInfo::get_Attributes()
0x13a4a  ldc.i4.1
0x13a4b  and
0x13a4c  ldc.i4.1
0x13a4d  bne.un.s loc_13A5E
0x13a4f  ldloc.0
0x13a50  ldloc.0
0x13a51  callvirt instance valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.FileSystemInfo::get_Attributes()
0x13a56  ldc.i4.s 0xFE
0x13a58  and
0x13a59  callvirt instance void [mscorlib]System.IO.FileSystemInfo::set_Attributes(valuetype [mscorlib]System.IO.FileAttributes)
0x13a5e  nop
0x13a5f  ldloc.0
0x13a60  callvirt instance void [mscorlib]System.IO.FileSystemInfo::Delete()
0x13a65  leave    loc_13AF0
0x13a6a  stloc.1
0x13a6b  ldloc.1
0x13a6c  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x13a71  stloc.2
0x13a72  ldstr    aErrorDeleting0// "Error deleting {0}. {1}: {2}, HResult ="...
0x13a77  ldc.i4.4
0x13a78  newarr   [mscorlib]System.Object
0x13a7d  dup
0x13a7e  ldc.i4.0
0x13a7f  ldarg.0
0x13a80  stelem.ref
0x13a81  dup
0x13a82  ldc.i4.1
0x13a83  ldloc.1
0x13a84  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x13a89  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x13a8e  stelem.ref
0x13a8f  dup
0x13a90  ldc.i4.2
0x13a91  ldloc.1
0x13a92  callvirt instance string [mscorlib]System.Exception::get_Message()
0x13a97  stelem.ref
0x13a98  dup
0x13a99  ldc.i4.3
0x13a9a  ldloc.2
0x13a9b  box      [mscorlib]System.Int32
0x13aa0  stelem.ref
0x13aa1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x13aa6  ldarg.1
0x13aa7  brfalse.s loc_13ACA
0x13aa9  ldloc.2
0x13aaa  call     bool Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::DoesHResultIndicateLockedFile(int32 hResult)
0x13aaf  brfalse.s loc_13ACA
0x13ab1  ldstr    aSchedulingForD// "   Scheduling for deletion on next rebo"...
0x13ab6  ldc.i4.0
0x13ab7  newarr   [mscorlib]System.Object
0x13abc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x13ac1  ldarg.1
0x13ac2  ldarg.0
0x13ac3  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::ScheduleFileDeletionOnReboot(string filePath)
0x13ac8  br.s     loc_13AEE
0x13aca  ldstr    aErrorDeleting0_0// "Error deleting {0} -- {1}"
0x13acf  ldc.i4.2
0x13ad0  newarr   [mscorlib]System.Object
0x13ad5  dup
0x13ad6  ldc.i4.0
0x13ad7  ldarg.0
0x13ad8  stelem.ref
0x13ad9  dup
0x13ada  ldc.i4.1
0x13adb  ldloc.1
0x13adc  callvirt instance string [mscorlib]System.Exception::get_Message()
0x13ae1  stelem.ref
0x13ae2  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x13ae7  ldloc.1
0x13ae8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x13aed  throw
0x13aee  leave.s  loc_13AF0
0x13af0  ret
```
