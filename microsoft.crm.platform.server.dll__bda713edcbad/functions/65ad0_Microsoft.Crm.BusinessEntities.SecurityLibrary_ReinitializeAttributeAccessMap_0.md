# Microsoft.Crm.BusinessEntities.SecurityLibrary::ReinitializeAttributeAccessMap_0

- ea: `0x65ad0`
- end: `0x65bff`
- name: `Microsoft.Crm.BusinessEntities.SecurityLibrary::ReinitializeAttributeAccessMap_0`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x65ab0`
- `0x65c00`

## callees

- `0x1e6b0`
- `0x5d5d0`
- `0x61160`
- `0x611a0`
- `0x611b0`
- `0x611e0`
- `0x63470`
- `0x64d70`
- `0x65ad0`
- `0x66b00`
- `0x7f370`

## string_xrefs

- `0x65bf4`: `Update`
- `0x65b55`: `exec p_PrincipalAttributeAccessMapReinitBulk @PrincipalUserIds, @PrincipalTeamIds, @ResetSyncSubscriptions`

## pseudocode

```c

```

## disassembly

```asm
0x65ad0  ldarg.0
0x65ad1  ldstr    aPrincipals// "principals"
0x65ad6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x65adb  ldarg.3
0x65adc  ldstr    aContext// "context"
0x65ae1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x65ae6  ldarg.0
0x65ae7  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.BusinessEntities.SecurityPrincipal>::get_Count()
0x65aec  brtrue.s loc_65AEF
0x65aee  ret
0x65aef  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x65af4  stloc.0
0x65af5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x65afa  stloc.1
0x65afb  ldarg.0
0x65afc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.BusinessEntities.SecurityPrincipal>::GetEnumerator()
0x65b01  stloc.2
0x65b02  br.s     loc_65B3B
0x65b04  ldloc.2
0x65b05  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.BusinessEntities.SecurityPrincipal>::get_Current()
0x65b0a  stloc.3
0x65b0b  ldloc.3
0x65b0c  call     void Microsoft.Crm.BusinessEntities.SecurityPrincipal::ValidateSecurityPrincipal(class Microsoft.Crm.BusinessEntities.SecurityPrincipal principal)
0x65b11  ldloc.3
0x65b12  callvirt instance bool Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_IsUserPrincipal()
0x65b17  brfalse.s loc_65B27
0x65b19  ldloc.0
0x65b1a  ldloc.3
0x65b1b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x65b20  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x65b25  br.s     loc_65B3B
0x65b27  ldloc.3
0x65b28  callvirt instance bool Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_IsTeamPrincipal()
0x65b2d  brfalse.s loc_65B3B
0x65b2f  ldloc.1
0x65b30  ldloc.3
0x65b31  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x65b36  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x65b3b  ldloc.2
0x65b3c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x65b41  brtrue.s loc_65B04
0x65b43  leave.s  loc_65B4F
0x65b45  ldloc.2
0x65b46  brfalse.s loc_65B4E
0x65b48  ldloc.2
0x65b49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65b4e  endfinally
0x65b4f  ldarg.3
0x65b50  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x65b55  ldstr    aExecPPrincipal// "exec p_PrincipalAttributeAccessMapReini"...
0x65b5a  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x65b5f  stloc.s  4
0x65b61  ldloc.s  4
0x65b63  call     int32 [Microsoft.Crm]Microsoft.Crm.Timeouts::GetExtendedTimeout()
0x65b68  ldc.i4.2
0x65b69  mul
0x65b6a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandTimeout(int32)
0x65b6f  ldloc.s  4
0x65b71  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x65b76  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x65b7b  dup
0x65b7c  ldloc.0
0x65b7d  call     T0x2B00006E
0x65b82  brtrue.s loc_65B87
0x65b84  ldnull
0x65b85  br.s     loc_65B88
0x65b87  ldloc.0
0x65b88  ldstr    aPrincipaluseri// "@PrincipalUserIds"
0x65b8d  call     class [System.Data]System.Data.SqlClient.SqlParameter Microsoft.Crm.Query.QueryHelper::GetEntityIdTableParameter(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> entityIds, string parameterName)
0x65b92  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x65b97  pop
0x65b98  dup
0x65b99  ldloc.1
0x65b9a  call     T0x2B00006E
0x65b9f  brtrue.s loc_65BA4
0x65ba1  ldnull
0x65ba2  br.s     loc_65BA5
0x65ba4  ldloc.1
0x65ba5  ldstr    aPrincipalteami// "@PrincipalTeamIds"
0x65baa  call     class [System.Data]System.Data.SqlClient.SqlParameter Microsoft.Crm.Query.QueryHelper::GetEntityIdTableParameter(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> entityIds, string parameterName)
0x65baf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x65bb4  pop
0x65bb5  ldstr    aResetsyncsubsc// "@ResetSyncSubscriptions"
0x65bba  ldarg.2
0x65bbb  box      [mscorlib]System.Boolean
0x65bc0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x65bc5  pop
0x65bc6  ldloc.s  4
0x65bc8  ldarg.3
0x65bc9  call     int32 Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x65bce  pop
0x65bcf  leave.s  loc_65BDD
0x65bd1  ldloc.s  4
0x65bd3  brfalse.s loc_65BDC
0x65bd5  ldloc.s  4
0x65bd7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65bdc  endfinally
0x65bdd  ldarg.1
0x65bde  brfalse.s loc_65BF1
0x65be0  ldloc.0
0x65be1  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x65be6  call     bool Microsoft.Crm.BusinessEntities.SecurityLibrary::get_HardFlush()
0x65beb  ldarg.3
0x65bec  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::FlushUsersBulk(valuetype [mscorlib]System.Guid[] userIds, bool flushImmediate, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x65bf1  ldarg.3
0x65bf2  ldc.i4.s 0x2B
0x65bf4  ldstr    aUpdate// "Update"
0x65bf9  call     void Microsoft.Crm.BusinessEntities.ChangeTrackingHelper::TryAddEntityToChangedTypes(class Microsoft.Crm.BusinessEntities.ExecutionContext context, int32 otc, string messageName)
0x65bfe  ret
```
