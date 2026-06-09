# Microsoft.Crm.Sandbox.SandboxWorkerManager::CleanupOldWorkerProcessFolders

- ea: `0x6ad0`
- end: `0x6d16`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::CleanupOldWorkerProcessFolders`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0xc9f0`

## callees

- `0x6ad0`
- `0xb870`
- `0xcc20`

## string_xrefs

- `0x6c1e`: `AssemblyCache`
- `0x6c40`: `AssemblyCache`
- `0x6b03`: `SandboxWorkerManager.CleanupOldWorkerProcessFolders: Sandbox WorkerProcess directory does not exist: {0}`
- `0x6b23`: `SandboxWorkerManager.CleanupOldWorkerProcessFolders: Sandbox WorkerProcess directory found: {0}`
- `0x6c94`: `SandboxWorkerManager.CleanupOldWorkerProcessFolders: Unable to delete unused folder: {0} due to exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x6ad0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ad5  ldc.i4.s 0x21
0x6ad7  ldstr    aSandboxworkerm_17// "SandboxWorkerManager.CleanupOldWorkerPr"...
0x6adc  ldc.i4.0
0x6add  newarr   [mscorlib]System.Object
0x6ae2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6ae7  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::BasePackagePath()
0x6aec  stloc.0
0x6aed  ldloc.0
0x6aee  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x6af3  stloc.1
0x6af4  ldloc.1
0x6af5  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x6afa  brtrue.s loc_6B1C
0x6afc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6b01  ldc.i4.s 0x21
0x6b03  ldstr    aSandboxworkerm_18// "SandboxWorkerManager.CleanupOldWorkerPr"...
0x6b08  ldc.i4.1
0x6b09  newarr   [mscorlib]System.Object
0x6b0e  dup
0x6b0f  ldc.i4.0
0x6b10  ldloc.0
0x6b11  stelem.ref
0x6b12  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6b17  leave    loc_6D15
0x6b1c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6b21  ldc.i4.s 0x21
0x6b23  ldstr    aSandboxworkerm_19// "SandboxWorkerManager.CleanupOldWorkerPr"...
0x6b28  ldc.i4.1
0x6b29  newarr   [mscorlib]System.Object
0x6b2e  dup
0x6b2f  ldc.i4.0
0x6b30  ldloc.0
0x6b31  stelem.ref
0x6b32  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6b37  ldloc.1
0x6b38  callvirt instance class [mscorlib]System.IO.DirectoryInfo[] [mscorlib]System.IO.DirectoryInfo::GetDirectories()
0x6b3d  stloc.2
0x6b3e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6b43  ldc.i4.s 0x21
0x6b45  ldstr    aSandboxworkerm_20// "SandboxWorkerManager.CleanupOldWorkerPr"...
0x6b4a  ldc.i4.1
0x6b4b  newarr   [mscorlib]System.Object
0x6b50  dup
0x6b51  ldc.i4.0
0x6b52  ldloc.2
0x6b53  ldlen
0x6b54  conv.i4
0x6b55  box      [mscorlib]System.Int32
0x6b5a  stelem.ref
0x6b5b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6b60  ldloc.2
0x6b61  stloc.3
0x6b62  ldc.i4.0
0x6b63  stloc.s  4
0x6b65  br       loc_6CC0
0x6b6a  newobj   instance void <>c__DisplayClass17_0::.ctor()
0x6b6f  stloc.s  5
0x6b71  ldloc.s  5
0x6b73  ldloc.3
0x6b74  ldloc.s  4
0x6b76  ldelem.ref
0x6b77  stfld    class [mscorlib]System.IO.DirectoryInfo <>c__DisplayClass17_0::dirInfo
0x6b7c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6b81  ldc.i4.s 0x21
0x6b83  ldstr    aSandboxworkerm_21// "SandboxWorkerManager.CleanupOldWorkerPr"...
0x6b88  ldc.i4.1
0x6b89  newarr   [mscorlib]System.Object
0x6b8e  dup
0x6b8f  ldc.i4.0
0x6b90  ldloc.s  5
0x6b92  ldfld    class [mscorlib]System.IO.DirectoryInfo <>c__DisplayClass17_0::dirInfo
0x6b97  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x6b9c  stelem.ref
0x6b9d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6ba2  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x6ba7  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Values()
0x6bac  ldloc.s  5
0x6bae  ldftn    instance bool <>c__DisplayClass17_0::<CleanupOldWorkerProcessFolders>b__0(class Microsoft.Crm.Sandbox.SandboxWorkerProcess x)
0x6bb4  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool>::.ctor(object, native int)
0x6bb9  call     T0x2B00000B
0x6bbe  brtrue   loc_6CBA
0x6bc3  ldloc.s  5
0x6bc5  ldfld    class [mscorlib]System.IO.DirectoryInfo <>c__DisplayClass17_0::dirInfo
0x6bca  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.IO.FileSystemInfo::get_CreationTime()
0x6bcf  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x6bd4  stloc.s  6
0x6bd6  ldloca.s 6
0x6bd8  ldc.r8   -15.0
0x6be1  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x6be6  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x6beb  brfalse  loc_6C89
0x6bf0  ldloc.s  5
0x6bf2  ldfld    class [mscorlib]System.IO.DirectoryInfo <>c__DisplayClass17_0::dirInfo
0x6bf7  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x6bfc  ldstr    aMscrmRo// "MSCRM_RO"
0x6c01  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x6c06  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x6c0b  brfalse.s loc_6C78
0x6c0d  ldloc.s  5
0x6c0f  ldfld    class [mscorlib]System.IO.DirectoryInfo <>c__DisplayClass17_0::dirInfo
0x6c14  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x6c19  ldstr    aMscrmRo// "MSCRM_RO"
0x6c1e  ldstr    aAssemblycache// "AssemblyCache"
0x6c23  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x6c28  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x6c2d  brfalse.s loc_6C78
0x6c2f  ldloc.s  5
0x6c31  ldfld    class [mscorlib]System.IO.DirectoryInfo <>c__DisplayClass17_0::dirInfo
0x6c36  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x6c3b  ldstr    aMscrmRo// "MSCRM_RO"
0x6c40  ldstr    aAssemblycache// "AssemblyCache"
0x6c45  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x6c4a  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x6c4f  callvirt instance class [mscorlib]System.IO.DirectoryInfo[] [mscorlib]System.IO.DirectoryInfo::GetDirectories()
0x6c54  stloc.s  7
0x6c56  ldc.i4.0
0x6c57  stloc.s  8
0x6c59  br.s     loc_6C70
0x6c5b  ldloc.s  7
0x6c5d  ldloc.s  8
0x6c5f  ldelem.ref
0x6c60  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x6c65  call     void [mscorlib]System.IO.Directory::Delete(string)
0x6c6a  ldloc.s  8
0x6c6c  ldc.i4.1
0x6c6d  add
0x6c6e  stloc.s  8
0x6c70  ldloc.s  8
0x6c72  ldloc.s  7
0x6c74  ldlen
0x6c75  conv.i4
0x6c76  blt.s    loc_6C5B
0x6c78  ldloc.s  5
0x6c7a  ldfld    class [mscorlib]System.IO.DirectoryInfo <>c__DisplayClass17_0::dirInfo
0x6c7f  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x6c84  call     void Microsoft.Crm.Sandbox.Win32FileUtility::DeleteFolder(string basePath)
0x6c89  leave.s  loc_6CBA
0x6c8b  stloc.s  9
0x6c8d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6c92  ldc.i4.s 0x21
0x6c94  ldstr    aSandboxworkerm_22// "SandboxWorkerManager.CleanupOldWorkerPr"...
0x6c99  ldc.i4.2
0x6c9a  newarr   [mscorlib]System.Object
0x6c9f  dup
0x6ca0  ldc.i4.0
0x6ca1  ldloc.s  5
0x6ca3  ldfld    class [mscorlib]System.IO.DirectoryInfo <>c__DisplayClass17_0::dirInfo
0x6ca8  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x6cad  stelem.ref
0x6cae  dup
0x6caf  ldc.i4.1
0x6cb0  ldloc.s  9
0x6cb2  stelem.ref
0x6cb3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6cb8  leave.s  loc_6CBA
0x6cba  ldloc.s  4
0x6cbc  ldc.i4.1
0x6cbd  add
0x6cbe  stloc.s  4
0x6cc0  ldloc.s  4
0x6cc2  ldloc.3
0x6cc3  ldlen
0x6cc4  conv.i4
0x6cc5  blt      loc_6B6A
0x6cca  ldloc.1
0x6ccb  callvirt instance class [mscorlib]System.IO.DirectoryInfo[] [mscorlib]System.IO.DirectoryInfo::GetDirectories()
0x6cd0  stloc.2
0x6cd1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6cd6  ldc.i4.s 0x21
0x6cd8  ldstr    aSandboxworkerm_23// "SandboxWorkerManager.CleanupOldWorkerPr"...
0x6cdd  ldc.i4.1
0x6cde  newarr   [mscorlib]System.Object
0x6ce3  dup
0x6ce4  ldc.i4.0
0x6ce5  ldloc.2
0x6ce6  ldlen
0x6ce7  conv.i4
0x6ce8  box      [mscorlib]System.Int32
0x6ced  stelem.ref
0x6cee  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6cf3  leave.s  loc_6D15
0x6cf5  stloc.s  0xA
0x6cf7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6cfc  ldc.i4.s 0x21
0x6cfe  ldstr    aSandboxworkerm_24// "SandboxWorkerManager.CleanupOldWorkerPr"...
0x6d03  ldc.i4.1
0x6d04  newarr   [mscorlib]System.Object
0x6d09  dup
0x6d0a  ldc.i4.0
0x6d0b  ldloc.s  0xA
0x6d0d  stelem.ref
0x6d0e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6d13  leave.s  loc_6D15
0x6d15  ret
```
