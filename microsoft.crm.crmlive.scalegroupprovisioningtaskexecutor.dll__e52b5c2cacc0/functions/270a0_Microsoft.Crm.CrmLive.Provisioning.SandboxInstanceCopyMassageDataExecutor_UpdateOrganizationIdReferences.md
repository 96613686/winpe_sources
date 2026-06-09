# Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::UpdateOrganizationIdReferences

- ea: `0x270a0`
- end: `0x27147`
- name: `Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::UpdateOrganizationIdReferences`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x26b20`

## callees

- `0x26a00`
- `0x270a0`

## string_xrefs

- `0x270ca`: `update MetadataSchema.OrganizationLanguagePack set OrganizationId = @neworgid`
- `0x270f3`: `PluginTraceLog`
- `0x27129`: `update [dbo].[PluginTraceLog] set OrganizationId = @neworgid`

## pseudocode

```c

```

## disassembly

```asm
0x270a0  ldarg.1
0x270a1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x270a6  ldc.i4.1
0x270a7  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(bool)
0x270ac  stloc.0
0x270ad  ldloc.0
0x270ae  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x270b3  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x270b8  ldstr    aNeworgid// "neworgid"
0x270bd  ldarg.2
0x270be  box      [mscorlib]System.Guid
0x270c3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x270c8  pop
0x270c9  ldloc.0
0x270ca  ldstr    aUpdateMetadata_1// "update MetadataSchema.OrganizationLangu"...
0x270cf  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x270d4  ldloc.0
0x270d5  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x270da  pop
0x270db  leave.s  loc_270E7
0x270dd  ldloc.0
0x270de  brfalse.s loc_270E6
0x270e0  ldloc.0
0x270e1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x270e6  endfinally
0x270e7  ldarg.0
0x270e8  ldarg.1
0x270e9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::MetadataCache(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x270ee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_EntitiesByName()
0x270f3  ldstr    aPlugintracelog// "PluginTraceLog"
0x270f8  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0x270fd  brfalse.s loc_27146
0x270ff  ldarg.1
0x27100  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x27105  ldc.i4.1
0x27106  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(bool)
0x2710b  stloc.1
0x2710c  ldloc.1
0x2710d  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x27112  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x27117  ldstr    aNeworgid// "neworgid"
0x2711c  ldarg.2
0x2711d  box      [mscorlib]System.Guid
0x27122  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x27127  pop
0x27128  ldloc.1
0x27129  ldstr    aUpdateDboPlugi// "update [dbo].[PluginTraceLog] set Organ"...
0x2712e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x27133  ldloc.1
0x27134  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x27139  pop
0x2713a  leave.s  loc_27146
0x2713c  ldloc.1
0x2713d  brfalse.s loc_27145
0x2713f  ldloc.1
0x27140  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27145  endfinally
0x27146  ret
```
