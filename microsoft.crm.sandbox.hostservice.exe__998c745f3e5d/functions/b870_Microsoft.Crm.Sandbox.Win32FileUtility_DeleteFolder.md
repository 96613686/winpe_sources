# Microsoft.Crm.Sandbox.Win32FileUtility::DeleteFolder

- ea: `0xb870`
- end: `0xb9e6`
- name: `Microsoft.Crm.Sandbox.Win32FileUtility::DeleteFolder`
- size: `374`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140`
- `0x6ad0`
- `0xb870`

## callees

- `0x4ff0`
- `0x5000`
- `0x5010`
- `0x5020`
- `0x5030`
- `0xb870`

## string_xrefs

- `0xb924`: `Win32FileUtility.DeleteFolder: Error removing temp file  {0} : {1}`
- `0xb967`: `Win32FileUtility.DeleteFolder: Error closing file - FindClose : {0}`
- `0xb991`: `Win32FileUtility.DeleteFolder: Error listing directory contents - FindFirstFileW: {0}`
- `0xb9cc`: `Win32FileUtility.DeleteFolder: Error removing empty directory contents - RemoveDirectory {0} : {1}`

## pseudocode

```c

```

## disassembly

```asm
0xb870  ldloca.s 0
0xb872  ldc.i4.m1
0xb873  call     instance void [mscorlib]System.IntPtr::.ctor(int32)
0xb878  ldstr    asc_2000A// "\\\\?\\"
0xb87d  ldarg.0
0xb87e  ldstr    asc_20014// "*"
0xb883  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xb888  call     string [mscorlib]System.String::Concat(string, string)
0xb88d  ldloca.s 1
0xb88f  call     native int Microsoft.Crm.Sandbox.NativeMethods::FindFirstFileW(string lpFileName, [out] valuetype Microsoft.Crm.Sandbox.WIN32_FIND_DATAW& lpFindFileData)
0xb894  stloc.2
0xb895  ldloc.2
0xb896  ldloc.0
0xb897  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0xb89c  brfalse  loc_B97D
0xb8a1  ldstr    asc_20018// "."
0xb8a6  ldloc.1
0xb8a7  ldfld    string Microsoft.Crm.Sandbox.WIN32_FIND_DATAW::cFileName
0xb8ac  call     instance bool [mscorlib]System.String::Equals(string)
0xb8b1  brtrue   loc_B93C
0xb8b6  ldstr    asc_2001C// ".."
0xb8bb  ldloc.1
0xb8bc  ldfld    string Microsoft.Crm.Sandbox.WIN32_FIND_DATAW::cFileName
0xb8c1  call     instance bool [mscorlib]System.String::Equals(string)
0xb8c6  brtrue.s loc_B93C
0xb8c8  ldloc.1
0xb8c9  ldfld    valuetype [mscorlib]System.IO.FileAttributes Microsoft.Crm.Sandbox.WIN32_FIND_DATAW::dwFileAttributes
0xb8ce  box      [mscorlib]System.IO.FileAttributes
0xb8d3  ldc.i4.s 0x10
0xb8d5  box      [mscorlib]System.IO.FileAttributes
0xb8da  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0xb8df  brfalse.s loc_B8F4
0xb8e1  ldarg.0
0xb8e2  ldloc.1
0xb8e3  ldfld    string Microsoft.Crm.Sandbox.WIN32_FIND_DATAW::cFileName
0xb8e8  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xb8ed  call     void Microsoft.Crm.Sandbox.Win32FileUtility::DeleteFolder(string basePath)
0xb8f2  br.s     loc_B93C
0xb8f4  ldstr    asc_2000A// "\\\\?\\"
0xb8f9  ldarg.0
0xb8fa  ldloc.1
0xb8fb  ldfld    string Microsoft.Crm.Sandbox.WIN32_FIND_DATAW::cFileName
0xb900  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xb905  call     string [mscorlib]System.String::Concat(string, string)
0xb90a  call     bool Microsoft.Crm.Sandbox.NativeMethods::DeleteFile(string path)
0xb90f  brtrue.s loc_B93C
0xb911  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0xb916  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0xb91b  stloc.3
0xb91c  ldnull
0xb91d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb922  ldc.i4.s 0x21
0xb924  ldstr    aWin32fileutili// "Win32FileUtility.DeleteFolder: Error re"...
0xb929  ldc.i4.2
0xb92a  newarr   [mscorlib]System.Object
0xb92f  dup
0xb930  ldc.i4.0
0xb931  ldarg.0
0xb932  stelem.ref
0xb933  dup
0xb934  ldc.i4.1
0xb935  ldloc.3
0xb936  stelem.ref
0xb937  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb93c  ldloc.2
0xb93d  ldloca.s 1
0xb93f  call     bool Microsoft.Crm.Sandbox.NativeMethods::FindNextFile(native int hFindFile, [out] valuetype Microsoft.Crm.Sandbox.WIN32_FIND_DATAW& lpFindFileData)
0xb944  brtrue   loc_B8A1
0xb949  leave.s  loc_B9A6
0xb94b  ldloc.2
0xb94c  call     bool Microsoft.Crm.Sandbox.NativeMethods::FindClose(native int hFindFile)
0xb951  brtrue.s loc_B97C
0xb953  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0xb958  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0xb95d  stloc.s  4
0xb95f  ldnull
0xb960  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb965  ldc.i4.s 0x21
0xb967  ldstr    aWin32fileutili_0// "Win32FileUtility.DeleteFolder: Error cl"...
0xb96c  ldc.i4.1
0xb96d  newarr   [mscorlib]System.Object
0xb972  dup
0xb973  ldc.i4.0
0xb974  ldloc.s  4
0xb976  stelem.ref
0xb977  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb97c  endfinally
0xb97d  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0xb982  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0xb987  stloc.s  5
0xb989  ldnull
0xb98a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb98f  ldc.i4.s 0x21
0xb991  ldstr    aWin32fileutili_1// "Win32FileUtility.DeleteFolder: Error li"...
0xb996  ldc.i4.1
0xb997  newarr   [mscorlib]System.Object
0xb99c  dup
0xb99d  ldc.i4.0
0xb99e  ldloc.s  5
0xb9a0  stelem.ref
0xb9a1  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb9a6  ldstr    asc_2000A// "\\\\?\\"
0xb9ab  ldarg.0
0xb9ac  call     string [mscorlib]System.String::Concat(string, string)
0xb9b1  call     bool Microsoft.Crm.Sandbox.NativeMethods::RemoveDirectory(string path)
0xb9b6  brtrue.s loc_B9E5
0xb9b8  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0xb9bd  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0xb9c2  stloc.s  6
0xb9c4  ldnull
0xb9c5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb9ca  ldc.i4.s 0x21
0xb9cc  ldstr    aWin32fileutili_2// "Win32FileUtility.DeleteFolder: Error re"...
0xb9d1  ldc.i4.2
0xb9d2  newarr   [mscorlib]System.Object
0xb9d7  dup
0xb9d8  ldc.i4.0
0xb9d9  ldarg.0
0xb9da  stelem.ref
0xb9db  dup
0xb9dc  ldc.i4.1
0xb9dd  ldloc.s  6
0xb9df  stelem.ref
0xb9e0  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb9e5  ret
```
