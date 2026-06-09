# Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteDirectory_0

- ea: `0x13b10`
- end: `0x13bb9`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteDirectory_0`
- size: `169`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x13b00`
- `0x13b10`
- `0x13bc0`

## callees

- `0x13a20`
- `0x13b10`

## string_xrefs

- `0x13b9d`: `Exception caught when attempting to delete directory {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x13b10  ldarg.0
0x13b11  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x13b16  brtrue.s loc_13B19
0x13b18  ret
0x13b19  ldarg.0
0x13b1a  call     string[] [mscorlib]System.IO.Directory::GetFiles(string)
0x13b1f  stloc.0
0x13b20  ldc.i4.0
0x13b21  stloc.1
0x13b22  br.s     loc_13B31
0x13b24  ldloc.0
0x13b25  ldloc.1
0x13b26  ldelem.ref
0x13b27  ldarg.1
0x13b28  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteFile(string filePath, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13b2d  ldloc.1
0x13b2e  ldc.i4.1
0x13b2f  add
0x13b30  stloc.1
0x13b31  ldloc.1
0x13b32  ldloc.0
0x13b33  ldlen
0x13b34  conv.i4
0x13b35  blt.s    loc_13B24
0x13b37  ldarg.0
0x13b38  call     string[] [mscorlib]System.IO.Directory::GetDirectories(string)
0x13b3d  stloc.0
0x13b3e  ldc.i4.0
0x13b3f  stloc.1
0x13b40  br.s     loc_13B4F
0x13b42  ldloc.0
0x13b43  ldloc.1
0x13b44  ldelem.ref
0x13b45  ldarg.1
0x13b46  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteDirectory(string directoryPath, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13b4b  ldloc.1
0x13b4c  ldc.i4.1
0x13b4d  add
0x13b4e  stloc.1
0x13b4f  ldloc.1
0x13b50  ldloc.0
0x13b51  ldlen
0x13b52  conv.i4
0x13b53  blt.s    loc_13B42
0x13b55  nop
0x13b56  ldc.i4.0
0x13b57  stloc.2
0x13b58  br.s     loc_13B8F
0x13b5a  ldarg.0
0x13b5b  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [mscorlib]System.IO.Directory::EnumerateFileSystemEntries(string)
0x13b60  call     T0x2B000009
0x13b65  brfalse.s loc_13B93
0x13b67  ldc.i4.s 0x64
0x13b69  ldloc.2
0x13b6a  mul
0x13b6b  stloc.3
0x13b6c  ldstr    aQueryOfChildIt// "Query of child items returned results -"...
0x13b71  ldc.i4.1
0x13b72  newarr   [mscorlib]System.Object
0x13b77  dup
0x13b78  ldc.i4.0
0x13b79  ldloc.3
0x13b7a  box      [mscorlib]System.Int32
0x13b7f  stelem.ref
0x13b80  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x13b85  ldloc.3
0x13b86  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x13b8b  ldloc.2
0x13b8c  ldc.i4.1
0x13b8d  add
0x13b8e  stloc.2
0x13b8f  ldloc.2
0x13b90  ldc.i4.5
0x13b91  ble.s    loc_13B5A
0x13b93  ldarg.0
0x13b94  call     void [mscorlib]System.IO.Directory::Delete(string)
0x13b99  leave.s  loc_13BB8
0x13b9b  stloc.s  4
0x13b9d  ldstr    aExceptionCaugh_0// "Exception caught when attempting to del"...
0x13ba2  ldc.i4.2
0x13ba3  newarr   [mscorlib]System.Object
0x13ba8  dup
0x13ba9  ldc.i4.0
0x13baa  ldarg.0
0x13bab  stelem.ref
0x13bac  dup
0x13bad  ldc.i4.1
0x13bae  ldloc.s  4
0x13bb0  stelem.ref
0x13bb1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x13bb6  leave.s  loc_13BB8
0x13bb8  ret
```
