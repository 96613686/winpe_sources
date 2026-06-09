# Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::BuildRoleConditionWithBusinessUnitIdsAsParameters

- ea: `0x75dd0`
- end: `0x75ea8`
- name: `Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::BuildRoleConditionWithBusinessUnitIdsAsParameters`
- size: `216`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x76d00`
- `0x77050`

## callees

- `0x1dfd0`
- `0x679e0`
- `0x72ee0`
- `0x75d30`
- `0x75dd0`
- `0x77580`

## string_xrefs

- `0x75e1b`: `securityQueryDetails`
- `0x75e20`: `businessUnitReadPrivilegeLength`

## pseudocode

```c

```

## disassembly

```asm
0x75dd0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x75dd5  ldarg.0
0x75dd6  ldarg.3
0x75dd7  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x75ddc  stloc.0
0x75ddd  ldloc.0
0x75dde  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, valuetype [mscorlib]System.Guid[]> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_BusinessUnitReadPrivilegeDictionary()
0x75de3  brfalse  loc_75EA7
0x75de8  ldloc.0
0x75de9  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, valuetype [mscorlib]System.Guid[]> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_BusinessUnitReadPrivilegeDictionary()
0x75dee  ldarg.1
0x75def  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x75df4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x75df9  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, valuetype [mscorlib]System.Guid[]>::ContainsKey(var<u1>)
0x75dfe  brfalse  loc_75EA7
0x75e03  ldloc.0
0x75e04  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, valuetype [mscorlib]System.Guid[]> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_BusinessUnitReadPrivilegeDictionary()
0x75e09  ldarg.1
0x75e0a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x75e0f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x75e14  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, valuetype [mscorlib]System.Guid[]>::get_Item(void)
0x75e19  stloc.1
0x75e1a  ldarg.3
0x75e1b  ldstr    aSecurityqueryd// "securityQueryDetails"
0x75e20  ldstr    aBusinessunitre// "businessUnitReadPrivilegeLength"
0x75e25  ldloc.1
0x75e26  ldlen
0x75e27  conv.i4
0x75e28  box      [mscorlib]System.Int32
0x75e2d  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::AddToInternalContextVariables(string innerDictionaryKey, string Key, object value)
0x75e32  ldstr    asc_CC172// "("
0x75e37  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x75e3c  stloc.2
0x75e3d  ldloc.1
0x75e3e  ldlen
0x75e3f  conv.i4
0x75e40  ldarg.3
0x75e41  call     int32 Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::RetrieveIdsCountForUsingGuidStringForSecuritySetting(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x75e46  ble.s    loc_75E67
0x75e48  ldloc.2
0x75e49  ldloc.1
0x75e4a  ldstr    aBuids// "@buIds"
0x75e4f  ldarg.2
0x75e50  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x75e55  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x75e5a  call     string Microsoft.Crm.Query.QueryHelper::GetSqlStringForManyGuidsUsingTableValuedParameter(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> values, string parameterName, class [System.Data]System.Data.SqlClient.SqlParameterCollection parameters)
0x75e5f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x75e64  pop
0x75e65  br.s     loc_75E8F
0x75e67  ldloc.1
0x75e68  stloc.3
0x75e69  ldc.i4.0
0x75e6a  stloc.s  4
0x75e6c  br.s     loc_75E88
0x75e6e  ldloc.3
0x75e6f  ldloc.s  4
0x75e71  ldelem   [mscorlib]System.Guid
0x75e76  ldstr    aBuid// "@buId"
0x75e7b  ldarg.2
0x75e7c  ldloc.2
0x75e7d  call     void Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::AddPrincipalToCommand(valuetype [mscorlib]System.Guid principalId, string parameterName, class [System.Data]System.Data.IDbCommand command, class [mscorlib]System.Text.StringBuilder sb)
0x75e82  ldloc.s  4
0x75e84  ldc.i4.1
0x75e85  add
0x75e86  stloc.s  4
0x75e88  ldloc.s  4
0x75e8a  ldloc.3
0x75e8b  ldlen
0x75e8c  conv.i4
0x75e8d  blt.s    loc_75E6E
0x75e8f  ldloc.2
0x75e90  ldstr    asc_CC192// ")"
0x75e95  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x75e9a  pop
0x75e9b  ldarg.2
0x75e9c  ldloc.2
0x75e9d  callvirt instance string [mscorlib]System.Object::ToString()
0x75ea2  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x75ea7  ret
```
