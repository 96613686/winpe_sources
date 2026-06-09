# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::RestoreFromBackup

- ea: `0x160e0`
- end: `0x16185`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::RestoreFromBackup`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x131d0`
- `0x14f50`
- `0x14f60`
- `0x14f70`
- `0x14fa0`
- `0x14fb0`
- `0x14fe0`
- `0x15030`
- `0x160e0`
- `0x16190`
- `0x16310`
- `0x16360`

## string_xrefs

- `0x16129`: `MainEngineThread is returning {0:D}`

## pseudocode

```c

```

## disassembly

```asm
0x160e0  ldarg.1
0x160e1  ldstr    aBackupFolderMu// "backup folder must be specified"
0x160e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x160eb  ldarg.0
0x160ec  ldarg.1
0x160ed  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_BackupDirectoryPath(string value)
0x160f2  ldarg.0
0x160f3  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::LoadRollbackDescriptorFromDisk()
0x160f8  ldarg.0
0x160f9  ldarg.0
0x160fa  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x160ff  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x16104  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_DeploymentSupportDirectoryPath(string value)
0x16109  ldarg.0
0x1610a  ldarg.0
0x1610b  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_RollbackDescriptor()
0x16110  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_PackageName()
0x16115  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_PackageName(string value)
0x1611a  ldarg.0
0x1611b  ldarg.0
0x1611c  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::RestoreFromBackup()
0x16121  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_ResultCode(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult value)
0x16126  leave.s  loc_1617E
0x16128  ldarg.0
0x16129  ldstr    aMainenginethre// "MainEngineThread is returning {0:D}"
0x1612e  ldc.i4.1
0x1612f  newarr   [mscorlib]System.Object
0x16134  dup
0x16135  ldc.i4.0
0x16136  ldarg.0
0x16137  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_ResultCode()
0x1613c  box      Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult
0x16141  stelem.ref
0x16142  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::Log(string format, object[] args)
0x16147  ldarg.0
0x16148  ldstr    aOnlinepackagem// "OnlinePackageManager result: {0}, value"...
0x1614d  ldc.i4.2
0x1614e  newarr   [mscorlib]System.Object
0x16153  dup
0x16154  ldc.i4.0
0x16155  ldarg.0
0x16156  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_ResultCode()
0x1615b  stloc.0
0x1615c  ldloca.s 0
0x1615e  constrained. Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult
0x16164  callvirt instance string [mscorlib]System.Object::ToString()
0x16169  stelem.ref
0x1616a  dup
0x1616b  ldc.i4.1
0x1616c  ldarg.0
0x1616d  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_ResultCode()
0x16172  box      [mscorlib]System.Int32
0x16177  stelem.ref
0x16178  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::Log(string format, object[] args)
0x1617d  endfinally
0x1617e  ldarg.0
0x1617f  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_ResultCode()
0x16184  ret
```
