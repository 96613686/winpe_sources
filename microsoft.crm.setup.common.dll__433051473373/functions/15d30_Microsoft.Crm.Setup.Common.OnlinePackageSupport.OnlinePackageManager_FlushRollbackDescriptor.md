# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::FlushRollbackDescriptor

- ea: `0x15d30`
- end: `0x15d6a`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::FlushRollbackDescriptor`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x15990`
- `0x15be0`

## callees

- `0x13300`
- `0x14fa0`
- `0x14fe0`
- `0x15d30`

## string_xrefs

- `0x15d3e`: `RollbackDescriptor.xml`
- `0x15d49`: `Writing rollback descriptor to {0}`

## pseudocode

```c

```

## disassembly

```asm
0x15d30  ldarg.0
0x15d31  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_RollbackDescriptor()
0x15d36  brfalse.s loc_15D69
0x15d38  ldarg.0
0x15d39  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_BackupDirectoryPath()
0x15d3e  ldstr    aRollbackdescri// "RollbackDescriptor.xml"
0x15d43  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x15d48  stloc.0
0x15d49  ldstr    aWritingRollbac// "Writing rollback descriptor to {0}"
0x15d4e  ldc.i4.1
0x15d4f  newarr   [mscorlib]System.Object
0x15d54  dup
0x15d55  ldc.i4.0
0x15d56  ldloc.0
0x15d57  stelem.ref
0x15d58  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15d5d  ldarg.0
0x15d5e  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_RollbackDescriptor()
0x15d63  ldloc.0
0x15d64  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::WriteToFile(string filePath)
0x15d69  ret
```
