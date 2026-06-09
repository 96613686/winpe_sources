# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::GetStagingPathForInstallLocation

- ea: `0x156e0`
- end: `0x156f3`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::GetStagingPathForInstallLocation`
- size: `19`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x15610`
- `0x15a10`
- `0x16030`

## callees

- `0x13f70`
- `0x15040`
- `0x15080`

## pseudocode

```c

```

## disassembly

```asm
0x156e0  ldarg.1
0x156e1  ldarg.0
0x156e2  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_InstallationPathRoot()
0x156e7  ldarg.0
0x156e8  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_StagingDirectoryPath()
0x156ed  call     string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::GetPathRelativeToTarget(string fullSourcePath, string sourceDirectoryPath, string targetDirectoryPath)
0x156f2  ret
```
