# Microsoft.Crm.Service.ObjectModel.SLAService::CheckMaximumSLAKPILimitReachedOnline

- ea: `0xad70`
- end: `0xae9e`
- name: `Microsoft.Crm.Service.ObjectModel.SLAService::CheckMaximumSLAKPILimitReachedOnline`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9fc0`

## callees

- `0xad70`

## string_xrefs

- `0xae5a`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Service\ObjectModel\Services\CS\SLAService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xad70  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xad75  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetSku()
0xad7a  ldc.i4.2
0xad7b  bne.un   loc_AE99
0xad80  ldarg.2
0xad81  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xad86  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xad8b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSLAFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xad90  brfalse  loc_AE99
0xad95  ldstr    aSelectCountDis// "SELECT count(DISTINCT [RelatedField])  "...
0xad9a  stloc.0
0xad9b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::.ctor()
0xada0  stloc.1
0xada1  ldstr    aObjecttypecode_0// "ObjectTypeCode"
0xada6  stloc.2
0xada7  ldloc.1
0xada8  ldloc.2
0xada9  ldarg.1
0xadaa  box      [mscorlib]System.Int32
0xadaf  ldc.i4.8
0xadb0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType::.ctor(object, valuetype [System.Data]System.Data.SqlDbType)
0xadb5  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType)
0xadba  stloc.3
0xadbb  ldstr    aStatuscode_0// "StatusCode"
0xadc0  stloc.s  4
0xadc2  ldloc.1
0xadc3  ldloc.s  4
0xadc5  ldc.i4.2
0xadc6  box      [mscorlib]System.Int32
0xadcb  ldc.i4.8
0xadcc  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType::.ctor(object, valuetype [System.Data]System.Data.SqlDbType)
0xadd1  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType)
0xadd6  stloc.s  5
0xadd8  ldstr    aSlaid_1// "SlaId"
0xaddd  stloc.s  6
0xaddf  ldloc.1
0xade0  ldloc.s  6
0xade2  ldarg.0
0xade3  box      [mscorlib]System.Guid
0xade8  ldc.i4.s 0xE
0xadea  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType::.ctor(object, valuetype [System.Data]System.Data.SqlDbType)
0xadef  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType)
0xadf4  stloc.s  7
0xadf6  ldarg.2
0xadf7  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0xadfc  stloc.s  8
0xadfe  ldloc.1
0xadff  ldloc.s  8
0xae01  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xae06  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xae0b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParametersToSqlParameterCollection(class [System.Data]System.Data.SqlClient.SqlParameterCollection)
0xae10  ldloc.s  8
0xae12  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xae17  ldloc.0
0xae18  ldc.i4.3
0xae19  newarr   [mscorlib]System.Object
0xae1e  dup
0xae1f  ldc.i4.0
0xae20  ldloc.3
0xae21  stelem.ref
0xae22  dup
0xae23  ldc.i4.1
0xae24  ldloc.s  5
0xae26  stelem.ref
0xae27  dup
0xae28  ldc.i4.2
0xae29  ldloc.s  7
0xae2b  stelem.ref
0xae2c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xae31  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xae36  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0xae3b  ldarg.2
0xae3c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xae41  ldarg.2
0xae42  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0xae47  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_MaximumSLAKPIPerEntityWithActiveSLA()
0xae4c  stloc.s  9
0xae4e  ldloc.s  8
0xae50  ldc.i4   0x305
0xae55  ldstr    aCheckmaximumsl// "CheckMaximumSLAKPILimitReachedOnline"
0xae5a  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0xae5f  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xae64  unbox.any [mscorlib]System.Int32
0xae69  ldloc.s  9
0xae6b  ble.s    loc_AE72
0xae6d  ldc.i4.1
0xae6e  stloc.s  0xA
0xae70  leave.s  loc_AE9B
0xae72  leave.s  loc_AE99
0xae74  stloc.s  0xB
0xae76  ldstr    aFailedToRetrie// "Failed to retrieve SLA KPI Count"
0xae7b  ldloc.s  0xB
0xae7d  callvirt instance string [mscorlib]System.Exception::get_Message()
0xae82  call     string [mscorlib]System.String::Concat(string, string)
0xae87  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xae8c  throw
0xae8d  ldloc.s  8
0xae8f  brfalse.s loc_AE98
0xae91  ldloc.s  8
0xae93  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xae98  endfinally
0xae99  ldc.i4.0
0xae9a  ret
0xae9b  ldloc.s  0xA
0xae9d  ret
```
