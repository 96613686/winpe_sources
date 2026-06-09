# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::LoadRollbackDescriptorFromDisk

- ea: `0x16310`
- end: `0x1635d`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::LoadRollbackDescriptorFromDisk`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x160e0`

## callees

- `0x13230`
- `0x14fa0`
- `0x14ff0`

## string_xrefs

- `0x16326`: `RollbackDescriptor.xml`
- `0x16316`: `BackupFolderPath must be set to load rollback descriptor`
- `0x16337`: `Rollback descriptor not found: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x16310  ldarg.0
0x16311  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x16316  ldstr    aBackupfolderpa// "BackupFolderPath must be set to load ro"...
0x1631b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x16320  ldarg.0
0x16321  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x16326  ldstr    aRollbackdescri// "RollbackDescriptor.xml"
0x1632b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x16330  stloc.0
0x16331  ldloc.0
0x16332  call     bool [mscorlib]System.IO.File::Exists(string)
0x16337  ldstr    aRollbackDescri// "Rollback descriptor not found: {0}"
0x1633c  ldc.i4.1
0x1633d  newarr   [mscorlib]System.Object
0x16342  dup
0x16343  ldc.i4.0
0x16344  ldloc.0
0x16345  stelem.ref
0x16346  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x1634b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x16350  ldarg.0
0x16351  ldloc.0
0x16352  call     class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::LoadFromFile(string filePath)
0x16357  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_RollbackDescriptor(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor value)
0x1635c  ret
```
