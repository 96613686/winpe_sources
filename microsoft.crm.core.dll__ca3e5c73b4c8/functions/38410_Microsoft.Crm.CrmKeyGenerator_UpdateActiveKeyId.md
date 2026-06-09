# Microsoft.Crm.CrmKeyGenerator::UpdateActiveKeyId

- ea: `0x38410`
- end: `0x38635`
- name: `Microsoft.Crm.CrmKeyGenerator::UpdateActiveKeyId`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x38280`

## callees

- `0xd2f0`
- `0xd620`
- `0xdab0`
- `0x1f4b0`
- `0x38410`
- `0x38640`
- `0x38960`
- `0x38990`
- `0x398d0`
- `0x3b8e0`
- `0x3b940`
- `0x4d750`
- `0x626d0`

## string_xrefs

- `0x38450`: `p_UpdateCurrentActiveKey`
- `0x385cc`: `UpdateActiveKeyId`
- `0x385d1`: `D:\a\1\s\src\Platform\Core\Security\Cryptography\CrmKeyGenerator.cs`
- `0x3860c`: `{0} updated with currently active CrmKey : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x38410  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x38415  ldc.i4.s 0x14
0x38417  ldstr    aUpdating0WithC// "Updating {0} with currently active CrmK"...
0x3841c  ldc.i4.1
0x3841d  newarr   [mscorlib]System.Object
0x38422  dup
0x38423  ldc.i4.0
0x38424  ldarg.0
0x38425  callvirt instance class Microsoft.Crm.CrmKeySetting Microsoft.Crm.CrmKeyInfo::get_CurrentKeySetting()
0x3842a  callvirt instance string Microsoft.Crm.BaseAuditableConfigurationEntity::get_TableName()
0x3842f  stelem.ref
0x38430  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x38435  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3843a  stloc.0
0x3843b  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x38440  stloc.1
0x38441  ldloc.1
0x38442  ldc.i4.2
0x38443  callvirt instance class Microsoft.Crm.CrmDbConnection Microsoft.Crm.SharedDatabase.DatabaseService::CreateConnection(valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope)
0x38448  stloc.2
0x38449  ldloc.2
0x3844a  callvirt instance void Microsoft.Crm.CrmDbConnection::Open()
0x3844f  ldloc.2
0x38450  ldstr    aPUpdatecurrent// "p_UpdateCurrentActiveKey"
0x38455  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand(string commandText)
0x3845a  stloc.3
0x3845b  ldloc.3
0x3845c  ldc.i4.4
0x3845d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x38462  ldloc.3
0x38463  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x38468  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x3846d  stloc.s  4
0x3846f  ldloc.s  4
0x38471  ldc.i4.1
0x38472  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x38477  ldloc.s  4
0x38479  ldstr    aScalegroupid_2// "@scaleGroupId"
0x3847e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x38483  ldloc.s  4
0x38485  ldc.i4.0
0x38486  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x3848b  ldloc.s  4
0x3848d  ldc.i4.s 0xE
0x3848f  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x38494  ldloc.s  4
0x38496  ldarg.1
0x38497  box      [mscorlib]System.Guid
0x3849c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x384a1  dup
0x384a2  ldloc.s  4
0x384a4  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x384a9  pop
0x384aa  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x384af  stloc.s  5
0x384b1  ldloc.s  5
0x384b3  ldc.i4.1
0x384b4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x384b9  ldloc.s  5
0x384bb  ldstr    aKeygenerationi// "@keyGenerationInterval"
0x384c0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x384c5  ldloc.s  5
0x384c7  ldc.i4.0
0x384c8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x384cd  ldloc.s  5
0x384cf  ldc.i4.8
0x384d0  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x384d5  ldloc.s  5
0x384d7  ldarg.0
0x384d8  callvirt instance class Microsoft.Crm.CrmKeySetting Microsoft.Crm.CrmKeyInfo::get_CurrentKeySetting()
0x384dd  callvirt instance int32 Microsoft.Crm.CrmKeySetting::get_KeyGenerationInterval()
0x384e2  box      [mscorlib]System.Int32
0x384e7  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x384ec  dup
0x384ed  ldloc.s  5
0x384ef  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x384f4  pop
0x384f5  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x384fa  stloc.s  6
0x384fc  ldloc.s  6
0x384fe  ldc.i4.1
0x384ff  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x38504  ldloc.s  6
0x38506  ldstr    aKeytype_1// "@keyType"
0x3850b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x38510  ldloc.s  6
0x38512  ldc.i4.s 0x32
0x38514  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x38519  ldloc.s  6
0x3851b  ldc.i4.s 0xC
0x3851d  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x38522  ldloc.s  6
0x38524  ldarg.0
0x38525  callvirt instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeyInfo::get_KeyType()
0x3852a  box      Microsoft.Crm.CrmKeyType
0x3852f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x38534  dup
0x38535  ldloc.s  6
0x38537  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x3853c  pop
0x3853d  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x38542  stloc.s  7
0x38544  ldloc.s  7
0x38546  ldc.i4.1
0x38547  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x3854c  ldloc.s  7
0x3854e  ldstr    aModifiedby_0// "@modifiedBy"
0x38553  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x38558  ldloc.s  7
0x3855a  ldc.i4.s 0x64
0x3855c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x38561  ldloc.s  7
0x38563  ldc.i4.s 0xC
0x38565  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x3856a  ldloc.s  7
0x3856c  ldarg.0
0x3856d  callvirt instance class Microsoft.Crm.CrmKeySetting Microsoft.Crm.CrmKeyInfo::get_CurrentKeySetting()
0x38572  callvirt instance string Microsoft.Crm.BaseAuditableConfigurationEntity::get_ModifiedBy()
0x38577  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x3857c  dup
0x3857d  ldloc.s  7
0x3857f  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x38584  pop
0x38585  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x3858a  stloc.s  8
0x3858c  ldloc.s  8
0x3858e  ldc.i4.3
0x3858f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x38594  ldloc.s  8
0x38596  ldstr    aActivekeyid_0// "@activeKeyId"
0x3859b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x385a0  ldloc.s  8
0x385a2  ldc.i4.0
0x385a3  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x385a8  ldloc.s  8
0x385aa  ldc.i4.s 0xE
0x385ac  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x385b1  ldloc.s  8
0x385b3  ldloc.0
0x385b4  box      [mscorlib]System.Guid
0x385b9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x385be  ldloc.s  8
0x385c0  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x385c5  pop
0x385c6  ldloc.3
0x385c7  ldc.i4   0x191
0x385cc  ldstr    aUpdateactiveke// "UpdateActiveKeyId"
0x385d1  ldstr    aDA1SSrcPlatfor_18// "D:\\a\\1\\s\\src\\Platform\\Core\\Secur"...
0x385d6  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x385db  pop
0x385dc  ldloc.s  8
0x385de  ldloc.0
0x385df  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmKeyGenerator::Parameter2Guid(class [System.Data]System.Data.IDataParameter parameter, valuetype [mscorlib]System.Guid defaultValue)
0x385e4  stloc.0
0x385e5  leave.s  loc_38605
0x385e7  ldloc.3
0x385e8  brfalse.s loc_385F0
0x385ea  ldloc.3
0x385eb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x385f0  endfinally
0x385f1  ldloc.2
0x385f2  brfalse.s loc_385FA
0x385f4  ldloc.2
0x385f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x385fa  endfinally
0x385fb  ldloc.1
0x385fc  brfalse.s loc_38604
0x385fe  ldloc.1
0x385ff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38604  endfinally
0x38605  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3860a  ldc.i4.s 0x14
0x3860c  ldstr    a0UpdatedWithCu// "{0} updated with currently active CrmKe"...
0x38611  ldc.i4.2
0x38612  newarr   [mscorlib]System.Object
0x38617  dup
0x38618  ldc.i4.0
0x38619  ldarg.0
0x3861a  callvirt instance class Microsoft.Crm.CrmKeySetting Microsoft.Crm.CrmKeyInfo::get_CurrentKeySetting()
0x3861f  callvirt instance string Microsoft.Crm.BaseAuditableConfigurationEntity::get_TableName()
0x38624  stelem.ref
0x38625  dup
0x38626  ldc.i4.1
0x38627  ldloc.0
0x38628  box      [mscorlib]System.Guid
0x3862d  stelem.ref
0x3862e  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x38633  ldloc.0
0x38634  ret
```
