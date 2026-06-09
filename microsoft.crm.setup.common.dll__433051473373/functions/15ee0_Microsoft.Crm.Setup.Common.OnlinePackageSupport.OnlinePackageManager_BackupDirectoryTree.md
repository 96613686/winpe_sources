# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::BackupDirectoryTree

- ea: `0x15ee0`
- end: `0x1602e`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::BackupDirectoryTree`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x15d70`

## callees

- `0x131f0`
- `0x133b0`
- `0x133e0`
- `0x13400`
- `0x13430`
- `0x138b0`
- `0x14fe0`
- `0x15ee0`
- `0x17d70`

## pseudocode

```c

```

## disassembly

```asm
0x15ee0  ldarg.1
0x15ee1  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x15ee6  stloc.0
0x15ee7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.DirectoryInfo>::.ctor()
0x15eec  stloc.1
0x15eed  ldarg.3
0x15eee  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x15ef3  stloc.2
0x15ef4  br.s     loc_15F0A
0x15ef6  ldloc.2
0x15ef7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x15efc  stloc.3
0x15efd  ldloc.1
0x15efe  ldloc.0
0x15eff  ldloc.3
0x15f00  callvirt instance class [mscorlib]System.IO.DirectoryInfo[] [mscorlib]System.IO.DirectoryInfo::GetDirectories(string)
0x15f05  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.DirectoryInfo>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x15f0a  ldloc.2
0x15f0b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x15f10  brtrue.s loc_15EF6
0x15f12  leave.s  loc_15F1E
0x15f14  ldloc.2
0x15f15  brfalse.s loc_15F1D
0x15f17  ldloc.2
0x15f18  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15f1d  endfinally
0x15f1e  ldloc.0
0x15f1f  callvirt instance class [mscorlib]System.IO.DirectoryInfo[] [mscorlib]System.IO.DirectoryInfo::GetDirectories()
0x15f24  stloc.s  4
0x15f26  ldc.i4.0
0x15f27  stloc.s  5
0x15f29  br       loc_15FB5
0x15f2e  newobj   instance void <>c__DisplayClass71_0::.ctor()
0x15f33  stloc.s  6
0x15f35  ldloc.s  6
0x15f37  ldloc.s  4
0x15f39  ldloc.s  5
0x15f3b  ldelem.ref
0x15f3c  stfld    class [mscorlib]System.IO.DirectoryInfo <>c__DisplayClass71_0::subdirectory
0x15f41  ldloc.1
0x15f42  ldloc.s  6
0x15f44  ldftn    instance bool <>c__DisplayClass71_0::<BackupDirectoryTree>b__0(class [mscorlib]System.IO.DirectoryInfo excludedDir)
0x15f4a  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.IO.DirectoryInfo, bool>::.ctor(object, native int)
0x15f4f  call     T0x2B00001E
0x15f54  brtrue.s loc_15FAF
0x15f56  ldarg.2
0x15f57  ldloc.s  6
0x15f59  ldfld    class [mscorlib]System.IO.DirectoryInfo <>c__DisplayClass71_0::subdirectory
0x15f5e  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x15f63  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x15f68  stloc.s  7
0x15f6a  ldarg.0
0x15f6b  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_RollbackDescriptor()
0x15f70  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_FileSystemOperations()
0x15f75  newobj   instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::.ctor()
0x15f7a  dup
0x15f7b  ldc.i4.4
0x15f7c  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Operation(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode value)
0x15f81  dup
0x15f82  ldloc.s  7
0x15f84  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Source(string value)
0x15f89  dup
0x15f8a  ldloc.s  6
0x15f8c  ldfld    class [mscorlib]System.IO.DirectoryInfo <>c__DisplayClass71_0::subdirectory
0x15f91  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x15f96  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Target(string value)
0x15f9b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::Add(var<u1>)
0x15fa0  ldloc.s  6
0x15fa2  ldfld    class [mscorlib]System.IO.DirectoryInfo <>c__DisplayClass71_0::subdirectory
0x15fa7  ldloc.s  7
0x15fa9  ldc.i4.1
0x15faa  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::CopyDirectory(class [mscorlib]System.IO.DirectoryInfo sourceDirectory, string targetDirectoryPath, bool recurse)
0x15faf  ldloc.s  5
0x15fb1  ldc.i4.1
0x15fb2  add
0x15fb3  stloc.s  5
0x15fb5  ldloc.s  5
0x15fb7  ldloc.s  4
0x15fb9  ldlen
0x15fba  conv.i4
0x15fbb  blt      loc_15F2E
0x15fc0  ldloc.0
0x15fc1  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles()
0x15fc6  stloc.s  8
0x15fc8  ldc.i4.0
0x15fc9  stloc.s  5
0x15fcb  br.s     loc_16025
0x15fcd  ldloc.s  8
0x15fcf  ldloc.s  5
0x15fd1  ldelem.ref
0x15fd2  stloc.s  9
0x15fd4  ldarg.2
0x15fd5  ldloc.s  9
0x15fd7  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x15fdc  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x15fe1  stloc.s  0xA
0x15fe3  ldloc.s  9
0x15fe5  ldloc.s  0xA
0x15fe7  ldc.i4.1
0x15fe8  callvirt instance class [mscorlib]System.IO.FileInfo [mscorlib]System.IO.FileInfo::CopyTo(string, bool)
0x15fed  pop
0x15fee  ldarg.0
0x15fef  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_RollbackDescriptor()
0x15ff4  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_FileSystemOperations()
0x15ff9  newobj   instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::.ctor()
0x15ffe  dup
0x15fff  ldc.i4.1
0x16000  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Operation(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode value)
0x16005  dup
0x16006  ldloc.s  0xA
0x16008  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Source(string value)
0x1600d  dup
0x1600e  ldloc.s  9
0x16010  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x16015  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::set_Target(string value)
0x1601a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::Add(var<u1>)
0x1601f  ldloc.s  5
0x16021  ldc.i4.1
0x16022  add
0x16023  stloc.s  5
0x16025  ldloc.s  5
0x16027  ldloc.s  8
0x16029  ldlen
0x1602a  conv.i4
0x1602b  blt.s    loc_15FCD
0x1602d  ret
```
