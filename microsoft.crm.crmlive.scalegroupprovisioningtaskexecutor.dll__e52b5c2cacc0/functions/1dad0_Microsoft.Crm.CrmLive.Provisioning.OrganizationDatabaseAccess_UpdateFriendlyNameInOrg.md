# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateFriendlyNameInOrg

- ea: `0x1dad0`
- end: `0x1db9f`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateFriendlyNameInOrg`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1dad0`
- `0x208b0`
- `0x323c0`

## string_xrefs

- `0x1db0f`: `UPDATE BusinessUnitBase SET Name=@name WHERE ParentBusinessUnitId IS NULL`
- `0x1db3d`: `UPDATE OrganizationBase SET Name=@name`
- `0x1db4f`: `UPDATE TeamBase SET Name=@name WHERE IsDefault=1 AND BusinessUnitId in (SELECT BusinessUnitId FROM BusinessUnitBase WHERE ParentBusinessUnitId IS NULL)`

## pseudocode

```c

```

## disassembly

```asm
0x1dad0  newobj   instance void <>c__DisplayClass44_0::.ctor()
0x1dad5  stloc.0
0x1dad6  ldloc.0
0x1dad7  ldarg.2
0x1dad8  stfld    string <>c__DisplayClass44_0::friendlyName
0x1dadd  ldloc.0
0x1dade  ldarg.1
0x1dadf  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass44_0::organizationId
0x1dae4  ldloc.0
0x1dae5  ldfld    string <>c__DisplayClass44_0::friendlyName
0x1daea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1daef  brfalse.s loc_1DAF2
0x1daf1  ret
0x1daf2  ldloc.0
0x1daf3  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass44_0::organizationId
0x1daf8  ldc.i4.0
0x1daf9  ldc.i4.0
0x1dafa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1daff  stloc.1
0x1db00  ldloc.1
0x1db01  ldc.i4.1
0x1db02  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnBeginRequest(bool)
0x1db07  ldloc.1
0x1db08  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::CreateSqlCommand()
0x1db0d  stloc.2
0x1db0e  ldloc.2
0x1db0f  ldstr    aUpdateBusiness// "UPDATE BusinessUnitBase SET Name=@name "...
0x1db14  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1db19  ldloc.2
0x1db1a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1db1f  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1db24  ldstr    aName_2// "@name"
0x1db29  ldloc.0
0x1db2a  ldfld    string <>c__DisplayClass44_0::friendlyName
0x1db2f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1db34  pop
0x1db35  ldloc.2
0x1db36  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x1db3b  pop
0x1db3c  ldloc.2
0x1db3d  ldstr    aUpdateOrganiza// "UPDATE OrganizationBase SET Name=@name"
0x1db42  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1db47  ldloc.2
0x1db48  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x1db4d  pop
0x1db4e  ldloc.2
0x1db4f  ldstr    aUpdateTeambase// "UPDATE TeamBase SET Name=@name WHERE Is"...
0x1db54  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1db59  ldloc.2
0x1db5a  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x1db5f  pop
0x1db60  leave.s  loc_1DB6C
0x1db62  ldloc.2
0x1db63  brfalse.s loc_1DB6B
0x1db65  ldloc.2
0x1db66  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1db6b  endfinally
0x1db6c  ldloc.1
0x1db6d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnEndRequest()
0x1db72  leave.s  loc_1DB87
0x1db74  pop
0x1db75  ldloc.1
0x1db76  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnErrorRequest()
0x1db7b  rethrow
0x1db7d  ldloc.1
0x1db7e  brfalse.s loc_1DB86
0x1db80  ldloc.1
0x1db81  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1db86  endfinally
0x1db87  ldloc.0
0x1db88  ldftn    instance void <>c__DisplayClass44_0::<UpdateFriendlyNameInOrg>b__0(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x1db8e  newobj   instance void class [mscorlib]System.Action`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext>::.ctor(object, native int)
0x1db93  ldloc.0
0x1db94  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass44_0::organizationId
0x1db99  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::RunWithSystemUserCredentials(class [mscorlib]System.Action`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext> method, valuetype [mscorlib]System.Guid organizationId)
0x1db9e  ret
```
