# Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_LockedFileTempDirectoryPath

- ea: `0x14090`
- end: `0x140a6`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_LockedFileTempDirectoryPath`
- size: `22`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14120`
- `0x143e0`
- `0x14510`

## callees

- `0x14090`
- `0x140b0`

## pseudocode

```c

```

## disassembly

```asm
0x14090  ldarg.0
0x14091  call     instance class [mscorlib]System.IO.DirectoryInfo Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_LockedFileTempDirectory()
0x14096  brfalse.s loc_140A4
0x14098  ldarg.0
0x14099  call     instance class [mscorlib]System.IO.DirectoryInfo Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_LockedFileTempDirectory()
0x1409e  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x140a3  ret
0x140a4  ldnull
0x140a5  ret
```
