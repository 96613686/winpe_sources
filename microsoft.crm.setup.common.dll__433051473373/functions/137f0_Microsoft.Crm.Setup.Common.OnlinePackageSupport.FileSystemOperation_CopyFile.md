# Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::CopyFile

- ea: `0x137f0`
- end: `0x138a7`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::CopyFile`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x13580`
- `0x13bc0`

## callees

- `0x137f0`
- `0x143d0`

## string_xrefs

- `0x13810`: `   File is locked (HResult=0x{0:X8}).  Scheduling for replacement on next reboot`
- `0x1383f`: `Error copying {0} to {1}.  {2}: {3}, HResult = 0x{4:X8}`
- `0x1387c`: `Error copying file {0} to {1}: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x137f0  ldarg.0
0x137f1  ldarg.1
0x137f2  ldc.i4.1
0x137f3  call     void [mscorlib]System.IO.File::Copy(string, string, bool)
0x137f8  leave    loc_138A6
0x137fd  stloc.0
0x137fe  ldloc.0
0x137ff  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x13804  stloc.1
0x13805  ldarg.2
0x13806  brfalse.s loc_1383F
0x13808  ldloc.1
0x13809  call     bool Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::DoesHResultIndicateLockedFile(int32 hResult)
0x1380e  brfalse.s loc_1383F
0x13810  ldstr    aFileIsLockedHr// "   File is locked (HResult=0x{0:X8}).  "...
0x13815  ldc.i4.1
0x13816  newarr   [mscorlib]System.Object
0x1381b  dup
0x1381c  ldc.i4.0
0x1381d  ldloc.1
0x1381e  box      [mscorlib]System.Int32
0x13823  stelem.ref
0x13824  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x13829  ldarg.2
0x1382a  ldarg.0
0x1382b  ldarg.1
0x1382c  ldnull
0x1382d  ldftn    void [mscorlib]System.IO.File::Copy(string, string)
0x13833  newobj   instance void class Microsoft.Crm.Setup.Common.OnlinePackageSupport.PopulateHoldingFile`1<string>::.ctor(object, native int)
0x13838  callvirt T0x2B000014
0x1383d  br.s     loc_138A4
0x1383f  ldstr    aErrorCopying0T// "Error copying {0} to {1}.  {2}: {3}, HR"...
0x13844  ldc.i4.5
0x13845  newarr   [mscorlib]System.Object
0x1384a  dup
0x1384b  ldc.i4.0
0x1384c  ldarg.0
0x1384d  stelem.ref
0x1384e  dup
0x1384f  ldc.i4.1
0x13850  ldarg.1
0x13851  stelem.ref
0x13852  dup
0x13853  ldc.i4.2
0x13854  ldloc.0
0x13855  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x1385a  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1385f  stelem.ref
0x13860  dup
0x13861  ldc.i4.3
0x13862  ldloc.0
0x13863  callvirt instance string [mscorlib]System.Exception::get_Message()
0x13868  stelem.ref
0x13869  dup
0x1386a  ldc.i4.4
0x1386b  ldloc.0
0x1386c  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x13871  box      [mscorlib]System.Int32
0x13876  stelem.ref
0x13877  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x1387c  ldstr    aErrorCopyingFi// "Error copying file {0} to {1}: {2}"
0x13881  ldc.i4.3
0x13882  newarr   [mscorlib]System.Object
0x13887  dup
0x13888  ldc.i4.0
0x13889  ldarg.0
0x1388a  stelem.ref
0x1388b  dup
0x1388c  ldc.i4.1
0x1388d  ldarg.1
0x1388e  stelem.ref
0x1388f  dup
0x13890  ldc.i4.2
0x13891  ldloc.0
0x13892  callvirt instance string [mscorlib]System.Exception::get_Message()
0x13897  stelem.ref
0x13898  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x1389d  ldloc.0
0x1389e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x138a3  throw
0x138a4  leave.s  loc_138A6
0x138a6  ret
```
