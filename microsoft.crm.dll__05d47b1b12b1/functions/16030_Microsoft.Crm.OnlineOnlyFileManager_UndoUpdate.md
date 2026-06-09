# Microsoft.Crm.OnlineOnlyFileManager::UndoUpdate

- ea: `0x16030`
- end: `0x1608d`
- name: `Microsoft.Crm.OnlineOnlyFileManager::UndoUpdate`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x16030`
- `0x16170`
- `0x162d0`

## string_xrefs

- `0x1603c`: `updateIndentifier`
- `0x16050`: `MonitoringAgent`
- `0x16063`: `Skipping OnlineOnlyFileManager.UndoUpdate because role is not supported`

## pseudocode

```c

```

## disassembly

```asm
0x16030  ldarg.0
0x16031  ldstr    aCrmserverfolde// "crmServerFolder"
0x16036  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1603b  ldarg.1
0x1603c  ldstr    aUpdateindentif// "updateIndentifier"
0x16041  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x16046  ldarg.2
0x16047  call     bool Microsoft.Crm.OnlineOnlyFileManager::ShouldCopyMonitoringAgent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles roles)
0x1604c  brfalse.s loc_1605A
0x1604e  ldarg.0
0x1604f  ldarg.1
0x16050  ldstr    aMonitoringagen// "MonitoringAgent"
0x16055  call     void Microsoft.Crm.OnlineOnlyFileManager::UndoUpdate(string crmServerFolder, string updateIdentifier, string roleFolderName)
0x1605a  ldarg.2
0x1605b  ldc.i4   0x1808000
0x16060  and
0x16061  brtrue.s loc_16074
0x16063  ldstr    aSkippingOnline// "Skipping OnlineOnlyFileManager.UndoUpda"...
0x16068  ldc.i4.0
0x16069  newarr   [mscorlib]System.Object
0x1606e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x16073  ret
0x16074  ldarg.0
0x16075  ldarg.1
0x16076  ldstr    aCrmweb// "CRMWeb"
0x1607b  call     void Microsoft.Crm.OnlineOnlyFileManager::UndoUpdate(string crmServerFolder, string updateIdentifier, string roleFolderName)
0x16080  ldarg.0
0x16081  ldarg.1
0x16082  ldstr    aServer// "Server"
0x16087  call     void Microsoft.Crm.OnlineOnlyFileManager::UndoUpdate(string crmServerFolder, string updateIdentifier, string roleFolderName)
0x1608c  ret
```
