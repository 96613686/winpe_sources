# Microsoft.Crm.Tools.Admin.UpdateOrganizationInstaller::RestoreSqlEncryptionKey

- ea: `0x15ee0`
- end: `0x15f57`
- name: `Microsoft.Crm.Tools.Admin.UpdateOrganizationInstaller::RestoreSqlEncryptionKey`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x15e00`

## callees

- `0x15ee0`

## string_xrefs

- `0x15f0d`: `Cannot restore Sql Encryption Key because the Encryption Key is not set in Config DB. Sql Encryption Key needs to be restored manually.`

## pseudocode

```c

```

## disassembly

```asm
0x15ee0  ldc.i4.1
0x15ee1  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheConfig::set_LoadMethod(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LoadMethod)
0x15ee6  ldarg.1
0x15ee7  ldc.i4.0
0x15ee8  ldc.i4.0
0x15ee9  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x15eee  stloc.0
0x15eef  ldloc.0
0x15ef0  ldc.i4.1
0x15ef1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x15ef6  ldc.i4.1
0x15ef7  ldloc.0
0x15ef8  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionService::.ctor(valuetype [Microsoft.Crm.MetadataService]Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x15efd  stloc.1
0x15efe  ldloc.1
0x15eff  callvirt instance string [Microsoft.Crm.MetadataService]Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionService::RetrieveEncryptionKey()
0x15f04  stloc.2
0x15f05  ldloc.2
0x15f06  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15f0b  brfalse.s loc_15F1F
0x15f0d  ldstr    aCannotRestoreS// "Cannot restore Sql Encryption Key becau"...
0x15f12  ldc.i4.0
0x15f13  newarr   [mscorlib]System.Object
0x15f18  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x15f1d  leave.s  loc_15F56
0x15f1f  ldloc.1
0x15f20  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionService::IsEncryptionActive()
0x15f25  brtrue.s loc_15F30
0x15f27  ldloc.1
0x15f28  ldloc.2
0x15f29  ldc.i4.1
0x15f2a  ldc.i4.1
0x15f2b  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionService::RestoreEncryptionKey(string, valuetype [Microsoft.Crm.MetadataService]Microsoft.Crm.SqlCellLevelEncryption.OrgDBIsEncryptionActiveCheckType, bool)
0x15f30  ldloc.0
0x15f31  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x15f36  leave.s  loc_15F56
0x15f38  stloc.3
0x15f39  ldloc.0
0x15f3a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x15f3f  castclass [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext
0x15f44  ldloc.3
0x15f45  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnErrorRequest(class [mscorlib]System.Exception)
0x15f4a  rethrow
0x15f4c  ldloc.0
0x15f4d  brfalse.s loc_15F55
0x15f4f  ldloc.0
0x15f50  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15f55  endfinally
0x15f56  ret
```
