# Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::SetRuleStatus

- ea: `0x1ec50`
- end: `0x1ed4f`
- name: `Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::SetRuleStatus`
- size: `255`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1dd70`
- `0x1ed50`

## callees

- `0x1ec50`
- `0x1f0f0`

## string_xrefs

- `0x1ec7f`: `UPDATE DuplicateRuleBase SET StateCode=@statecode, StatusCode=@statuscode WHERE DuplicateRuleId=@duplicateruleid`
- `0x1eccc`: `UPDATE DuplicateRuleBase SET StateCode=@statecode, StatusCode=@statuscode, BaseEntityMatchCodeTable=@null, MatchingEntityMatchCodeTable=@null WHERE DuplicateRuleId=@duplicateruleid`

## pseudocode

```c

```

## disassembly

```asm
0x1ec50  ldarg.1
0x1ec51  ldc.i4.2
0x1ec52  beq.s    loc_1EC68
0x1ec54  ldarg.1
0x1ec55  brfalse.s loc_1EC68
0x1ec57  ldc.i4   0x80048408
0x1ec5c  ldc.i4.0
0x1ec5d  newarr   [mscorlib]System.Object
0x1ec62  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1ec67  throw
0x1ec68  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x1ec6d  stloc.0
0x1ec6e  ldloc.0
0x1ec6f  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1ec74  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1ec79  stloc.1
0x1ec7a  ldarg.1
0x1ec7b  ldc.i4.2
0x1ec7c  bne.un.s loc_1ECC8
0x1ec7e  ldloc.0
0x1ec7f  ldstr    aUpdateDuplicat// "UPDATE DuplicateRuleBase SET StateCode="...
0x1ec84  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1ec89  ldloc.1
0x1ec8a  ldstr    aStatecode_3// "@statecode"
0x1ec8f  ldc.i4.1
0x1ec90  box      Microsoft.Crm.Asynchronous.DuplicateRuleState
0x1ec95  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ec9a  pop
0x1ec9b  ldloc.1
0x1ec9c  ldstr    aStatuscode_3// "@statuscode"
0x1eca1  ldc.i4.2
0x1eca2  box      [mscorlib]System.Int32
0x1eca7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ecac  pop
0x1ecad  ldloc.1
0x1ecae  ldstr    aDuplicaterulei_0// "@duplicateruleid"
0x1ecb3  ldarga.s 0
0x1ecb5  constrained. [mscorlib]System.Guid
0x1ecbb  callvirt instance string [mscorlib]System.Object::ToString()
0x1ecc0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ecc5  pop
0x1ecc6  br.s     loc_1ED24
0x1ecc8  ldarg.1
0x1ecc9  brtrue.s loc_1ED24
0x1eccb  ldloc.0
0x1eccc  ldstr    aUpdateDuplicat_0// "UPDATE DuplicateRuleBase SET StateCode="...
0x1ecd1  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1ecd6  ldloc.1
0x1ecd7  ldstr    aStatecode_3// "@statecode"
0x1ecdc  ldc.i4.0
0x1ecdd  box      Microsoft.Crm.Asynchronous.DuplicateRuleState
0x1ece2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ece7  pop
0x1ece8  ldloc.1
0x1ece9  ldstr    aStatuscode_3// "@statuscode"
0x1ecee  ldc.i4.0
0x1ecef  box      [mscorlib]System.Int32
0x1ecf4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ecf9  pop
0x1ecfa  ldloc.1
0x1ecfb  ldstr    aNull// "@null"
0x1ed00  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1ed05  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ed0a  pop
0x1ed0b  ldloc.1
0x1ed0c  ldstr    aDuplicaterulei_0// "@duplicateruleid"
0x1ed11  ldarga.s 0
0x1ed13  constrained. [mscorlib]System.Guid
0x1ed19  callvirt instance string [mscorlib]System.Object::ToString()
0x1ed1e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ed23  pop
0x1ed24  nop
0x1ed25  ldarg.2
0x1ed26  ldloc.0
0x1ed27  callvirt instance void Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess::ExecuteCommand(class [System.Data]System.Data.IDbCommand command)
0x1ed2c  leave.s  loc_1ED4E
0x1ed2e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DuplicateDetectionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DuplicateDetectionCache::Instance()
0x1ed33  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContextFactory::get_Current()
0x1ed38  ldarg.3
0x1ed39  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory::GetOrganizationContext(valuetype [mscorlib]System.Guid)
0x1ed3e  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IDuplicateRulesData>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ed43  endfinally
0x1ed44  ldloc.0
0x1ed45  brfalse.s loc_1ED4D
0x1ed47  ldloc.0
0x1ed48  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ed4d  endfinally
0x1ed4e  ret
```
