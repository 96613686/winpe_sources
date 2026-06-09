# Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::.ctor

- ea: `0x14120`
- end: `0x14159`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::.ctor`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x15500`
- `0x16190`

## callees

- `0x14090`
- `0x140c0`
- `0x140e0`
- `0x14160`

## pseudocode

```c

```

## disassembly

```asm
0x14120  ldarg.0
0x14121  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor>::.ctor()
0x14126  stfld    class [mscorlib]System.Collections.Generic.List`1<class DeferredFileReplacementDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::_uncommittedFileReplacements
0x1412b  ldarg.0
0x1412c  call     instance void [mscorlib]System.Object::.ctor()
0x14131  ldarg.0
0x14132  ldarg.0
0x14133  ldarg.1
0x14134  ldarg.2
0x14135  call     instance class [mscorlib]System.IO.DirectoryInfo Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::CreateLockedFileTempDirectory(string rootDirectoryPath, string nameTag)
0x1413a  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::set_LockedFileTempDirectory(class [mscorlib]System.IO.DirectoryInfo value)
0x1413f  ldarg.0
0x14140  ldc.i4   0x103
0x14145  ldarg.0
0x14146  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_LockedFileTempDirectoryPath()
0x1414b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x14150  ldc.i4.1
0x14151  add
0x14152  sub
0x14153  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::set_MaxTempFileNameLength(int32 value)
0x14158  ret
```
