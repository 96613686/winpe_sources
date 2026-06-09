# Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFile_0

- ea: `0x13970`
- end: `0x13a1f`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFile_0`
- size: `175`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x13580`
- `0x13960`
- `0x13bc0`
- `0x13cb0`
- `0x13e50`
- `0x141c0`
- `0x14280`

## callees

- `0x13970`
- `0x14010`
- `0x143d0`

## string_xrefs

- `0x139ee`: `   Scheduling for replacement on next reboot`

## pseudocode

```c

```

## disassembly

```asm
0x13970  ldstr    aMovingFileFrom// "Moving file from {0} to {1}"
0x13975  ldc.i4.2
0x13976  newarr   [mscorlib]System.Object
0x1397b  dup
0x1397c  ldc.i4.0
0x1397d  ldarg.0
0x1397e  stelem.ref
0x1397f  dup
0x13980  ldc.i4.1
0x13981  ldarg.1
0x13982  stelem.ref
0x13983  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x13988  ldarg.0
0x13989  ldarg.1
0x1398a  ldc.i4.s 0xB
0x1398c  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFileEx(string existingFileName, string newFileName, valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.MoveFileExFlags flags)
0x13991  leave    loc_13A1E
0x13996  stloc.0
0x13997  ldloc.0
0x13998  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x1399d  stloc.1
0x1399e  ldstr    aErrorMoving0To// "Error moving {0} to {1}.  {2}: {3}, HRe"...
0x139a3  ldc.i4.5
0x139a4  newarr   [mscorlib]System.Object
0x139a9  dup
0x139aa  ldc.i4.0
0x139ab  ldarg.0
0x139ac  stelem.ref
0x139ad  dup
0x139ae  ldc.i4.1
0x139af  ldarg.1
0x139b0  stelem.ref
0x139b1  dup
0x139b2  ldc.i4.2
0x139b3  ldloc.0
0x139b4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x139b9  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x139be  stelem.ref
0x139bf  dup
0x139c0  ldc.i4.3
0x139c1  ldloc.0
0x139c2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x139c7  stelem.ref
0x139c8  dup
0x139c9  ldc.i4.4
0x139ca  ldloc.1
0x139cb  box      [mscorlib]System.Int32
0x139d0  stelem.ref
0x139d1  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x139d6  stloc.2
0x139d7  ldloc.2
0x139d8  ldc.i4.0
0x139d9  newarr   [mscorlib]System.Object
0x139de  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x139e3  ldarg.2
0x139e4  brfalse.s loc_13A14
0x139e6  ldloc.1
0x139e7  call     bool Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::DoesHResultIndicateLockedFile(int32 hResult)
0x139ec  brfalse.s loc_13A14
0x139ee  ldstr    aSchedulingForR// "   Scheduling for replacement on next r"...
0x139f3  ldc.i4.0
0x139f4  newarr   [mscorlib]System.Object
0x139f9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x139fe  ldarg.2
0x139ff  ldarg.0
0x13a00  ldarg.1
0x13a01  ldnull
0x13a02  ldftn    void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFile(string source, string target)
0x13a08  newobj   instance void class Microsoft.Crm.Setup.Common.OnlinePackageSupport.PopulateHoldingFile`1<string>::.ctor(object, native int)
0x13a0d  callvirt T0x2B000014
0x13a12  br.s     loc_13A1C
0x13a14  ldloc.2
0x13a15  ldloc.0
0x13a16  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x13a1b  throw
0x13a1c  leave.s  loc_13A1E
0x13a1e  ret
```
