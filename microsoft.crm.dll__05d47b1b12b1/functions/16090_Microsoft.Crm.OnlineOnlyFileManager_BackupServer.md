# Microsoft.Crm.OnlineOnlyFileManager::BackupServer

- ea: `0x16090`
- end: `0x160f3`
- name: `Microsoft.Crm.OnlineOnlyFileManager::BackupServer`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x16090`
- `0x16210`
- `0x162d0`

## string_xrefs

- `0x1609c`: `updateIndentifier`
- `0x160b0`: `MonitoringAgent`

## pseudocode

```c

```

## disassembly

```asm
0x16090  ldarg.0
0x16091  ldstr    aCrmserverfolde// "crmServerFolder"
0x16096  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1609b  ldarg.2
0x1609c  ldstr    aUpdateindentif// "updateIndentifier"
0x160a1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x160a6  ldarg.3
0x160a7  call     bool Microsoft.Crm.OnlineOnlyFileManager::ShouldCopyMonitoringAgent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles roles)
0x160ac  brfalse.s loc_160BC
0x160ae  ldarg.0
0x160af  ldarg.1
0x160b0  ldstr    aMonitoringagen// "MonitoringAgent"
0x160b5  ldarg.2
0x160b6  ldc.i4.1
0x160b7  call     void Microsoft.Crm.OnlineOnlyFileManager::ProcessFilesInternal(string crmServerFolder, string onlineOnlyFolder, string roleFolderName, string updateIdentifier, bool backupOnly)
0x160bc  ldarg.3
0x160bd  ldc.i4   0x1808000
0x160c2  and
0x160c3  brtrue.s loc_160D6
0x160c5  ldstr    aSkippingOnline_0// "Skipping OnlineOnlyFileManager.BackupSe"...
0x160ca  ldc.i4.0
0x160cb  newarr   [mscorlib]System.Object
0x160d0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x160d5  ret
0x160d6  ldarg.0
0x160d7  ldarg.1
0x160d8  ldstr    aCrmweb// "CRMWeb"
0x160dd  ldarg.2
0x160de  ldc.i4.1
0x160df  call     void Microsoft.Crm.OnlineOnlyFileManager::ProcessFilesInternal(string crmServerFolder, string onlineOnlyFolder, string roleFolderName, string updateIdentifier, bool backupOnly)
0x160e4  ldarg.0
0x160e5  ldarg.1
0x160e6  ldstr    aServer// "Server"
0x160eb  ldarg.2
0x160ec  ldc.i4.1
0x160ed  call     void Microsoft.Crm.OnlineOnlyFileManager::ProcessFilesInternal(string crmServerFolder, string onlineOnlyFolder, string roleFolderName, string updateIdentifier, bool backupOnly)
0x160f2  ret
```
