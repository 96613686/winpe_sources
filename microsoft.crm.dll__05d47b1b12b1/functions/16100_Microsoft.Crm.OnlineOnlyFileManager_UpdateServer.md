# Microsoft.Crm.OnlineOnlyFileManager::UpdateServer

- ea: `0x16100`
- end: `0x16163`
- name: `Microsoft.Crm.OnlineOnlyFileManager::UpdateServer`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x16100`
- `0x16210`
- `0x162d0`

## string_xrefs

- `0x16120`: `MonitoringAgent`
- `0x16135`: `Skipping OnlineOnlyFileManager.UpdateServer because role is not supported`

## pseudocode

```c

```

## disassembly

```asm
0x16100  ldarg.0
0x16101  ldstr    aCrmserverfolde// "crmServerFolder"
0x16106  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1610b  ldarg.1
0x1610c  ldstr    aOnlineonlyfold// "onlineOnlyFolder"
0x16111  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x16116  ldarg.3
0x16117  call     bool Microsoft.Crm.OnlineOnlyFileManager::ShouldCopyMonitoringAgent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles roles)
0x1611c  brfalse.s loc_1612C
0x1611e  ldarg.0
0x1611f  ldarg.1
0x16120  ldstr    aMonitoringagen// "MonitoringAgent"
0x16125  ldarg.2
0x16126  ldc.i4.0
0x16127  call     void Microsoft.Crm.OnlineOnlyFileManager::ProcessFilesInternal(string crmServerFolder, string onlineOnlyFolder, string roleFolderName, string updateIdentifier, bool backupOnly)
0x1612c  ldarg.3
0x1612d  ldc.i4   0x1808000
0x16132  and
0x16133  brtrue.s loc_16146
0x16135  ldstr    aSkippingOnline_1// "Skipping OnlineOnlyFileManager.UpdateSe"...
0x1613a  ldc.i4.0
0x1613b  newarr   [mscorlib]System.Object
0x16140  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x16145  ret
0x16146  ldarg.0
0x16147  ldarg.1
0x16148  ldstr    aCrmweb// "CRMWeb"
0x1614d  ldarg.2
0x1614e  ldc.i4.0
0x1614f  call     void Microsoft.Crm.OnlineOnlyFileManager::ProcessFilesInternal(string crmServerFolder, string onlineOnlyFolder, string roleFolderName, string updateIdentifier, bool backupOnly)
0x16154  ldarg.0
0x16155  ldarg.1
0x16156  ldstr    aServer// "Server"
0x1615b  ldarg.2
0x1615c  ldc.i4.0
0x1615d  call     void Microsoft.Crm.OnlineOnlyFileManager::ProcessFilesInternal(string crmServerFolder, string onlineOnlyFolder, string roleFolderName, string updateIdentifier, bool backupOnly)
0x16162  ret
```
