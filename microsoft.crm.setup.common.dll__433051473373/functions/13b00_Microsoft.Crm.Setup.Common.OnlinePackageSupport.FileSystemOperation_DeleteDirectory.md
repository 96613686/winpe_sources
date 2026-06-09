# Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteDirectory

- ea: `0x13b00`
- end: `0x13b08`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteDirectory`
- size: `8`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x150b0`
- `0x15340`
- `0x15be0`
- `0x16190`

## callees

- `0x13b10`

## pseudocode

```c

```

## disassembly

```asm
0x13b00  ldarg.0
0x13b01  ldnull
0x13b02  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::DeleteDirectory(string directoryPath, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x13b07  ret
```
