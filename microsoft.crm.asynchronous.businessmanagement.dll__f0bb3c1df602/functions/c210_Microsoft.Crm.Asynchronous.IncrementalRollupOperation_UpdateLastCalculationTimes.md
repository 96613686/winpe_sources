# Microsoft.Crm.Asynchronous.IncrementalRollupOperation::UpdateLastCalculationTimes

- ea: `0xc210`
- end: `0xc275`
- name: `Microsoft.Crm.Asynchronous.IncrementalRollupOperation::UpdateLastCalculationTimes`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0xc310`

## callees

- `0xc210`
- `0xc460`
- `0xc4c0`
- `0xe600`

## string_xrefs

- `0xc217`: `DECLARE @RollupId uniqueidentifier\nDECLARE @CreatedOn datetime\n\nDECLARE UPDATE_NEEDED_CURSOR CURSOR\n	LOCAL FAST_FORWARD\nFOR\n	SELECT RollupPropertiesId FROM RollupPropertiesBase\n	WHERE RollupEntityTypeCode = @etc\n		AND (LastCalculationTime IS NULL\n		OR LastCalculationTime < GETUTCDATE() - 1) -- -24hrs\n\nOPEN UPDATE_NEEDED_CURSOR\nFETCH NEXT FROM UPDATE_NEEDED_CURSOR INTO @RollupId\nWHILE @@FETCH_STATUS = 0\nBEGIN\n	SET @CreatedOn =\n		ISNULL(\n			(SELECT MIN(r.RecordCre`

## pseudocode

```c

```

## disassembly

```asm
0xc210  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xc215  stloc.0
0xc216  ldloc.0
0xc217  ldstr    aDeclareRollupi// "DECLARE @RollupId uniqueidentifier\r\nD"...
0xc21c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xc221  ldloc.0
0xc222  callvirt instance class [System.Data]System.Data.IDbDataParameter [System.Data]System.Data.IDbCommand::CreateParameter()
0xc227  stloc.1
0xc228  ldloc.1
0xc229  ldstr    aEtc// "@etc"
0xc22e  callvirt instance void [System.Data]System.Data.IDataParameter::set_ParameterName(string)
0xc233  ldloc.1
0xc234  ldarg.0
0xc235  ldfld    class Microsoft.Crm.Asynchronous.RollupsAsyncContext Microsoft.Crm.Asynchronous.IncrementalRollupOperation::_rollupsAsyncContext
0xc23a  callvirt instance int32 Microsoft.Crm.Asynchronous.RollupsAsyncContext::get_EntityTypeCode()
0xc23f  box      [mscorlib]System.Int32
0xc244  callvirt instance void [System.Data]System.Data.IDataParameter::set_Value(object)
0xc249  ldloc.0
0xc24a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xc24f  ldloc.1
0xc250  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0xc255  pop
0xc256  ldarg.0
0xc257  ldfld    class Microsoft.Crm.Asynchronous.RollupsAsyncContext Microsoft.Crm.Asynchronous.IncrementalRollupOperation::_rollupsAsyncContext
0xc25c  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess Microsoft.Crm.Asynchronous.RollupsAsyncContext::get_RollupsDataAccess()
0xc261  ldloc.0
0xc262  callvirt instance object Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xc267  pop
0xc268  leave.s  loc_C274
0xc26a  ldloc.0
0xc26b  brfalse.s loc_C273
0xc26d  ldloc.0
0xc26e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc273  endfinally
0xc274  ret
```
