# Microsoft.Crm.Tools.Admin.OrganizationOperation::CheckIfXrmOrg

- ea: `0xa320`
- end: `0xa3c7`
- name: `Microsoft.Crm.Tools.Admin.OrganizationOperation::CheckIfXrmOrg`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x94a0`

## callees

- `0xa320`

## string_xrefs

- `0xa320`: `Begin: Check if CRM Solutions are installed {0}`
- `0xa348`: `msdynce_CRMExtensions`
- `0xa37e`: `Error during CheckIfXrmOrg`
- `0xa3ac`: `End: Check if CRM Solutions are installed isXrmOrg = {0}`

## pseudocode

```c

```

## disassembly

```asm
0xa320  ldstr    aBeginCheckIfCr// "Begin: Check if CRM Solutions are insta"...
0xa325  ldc.i4.1
0xa326  newarr   [mscorlib]System.Object
0xa32b  dup
0xa32c  ldc.i4.0
0xa32d  ldarg.0
0xa32e  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0xa333  stelem.ref
0xa334  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteFormat(string, object[])
0xa339  ldc.i4.0
0xa33a  stloc.0
0xa33b  ldarg.0
0xa33c  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0xa341  stloc.1
0xa342  ldloc.1
0xa343  ldstr    aSelectSolution// "SELECT SolutionId FROM Solution where  "...
0xa348  ldstr    aMsdynceCrmexte// "msdynce_CRMExtensions"
0xa34d  call     string [mscorlib]System.String::Format(string, object)
0xa352  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xa357  ldloc.1
0xa358  ldc.i4.1
0xa359  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0xa35e  ldloc.1
0xa35f  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0xa364  stloc.2
0xa365  ldloc.2
0xa366  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xa36b  ldc.i4.0
0xa36c  ceq
0xa36e  stloc.0
0xa36f  leave.s  loc_A37B
0xa371  ldloc.2
0xa372  brfalse.s loc_A37A
0xa374  ldloc.2
0xa375  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa37a  endfinally
0xa37b  leave.s  loc_A3AC
0xa37d  stloc.3
0xa37e  ldstr    aErrorDuringChe// "Error during CheckIfXrmOrg"
0xa383  ldc.i4.2
0xa384  newarr   [mscorlib]System.Object
0xa389  dup
0xa38a  ldc.i4.0
0xa38b  ldloc.3
0xa38c  callvirt instance string [mscorlib]System.Object::ToString()
0xa391  stelem.ref
0xa392  dup
0xa393  ldc.i4.1
0xa394  ldloc.1
0xa395  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0xa39a  stelem.ref
0xa39b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0xa3a0  leave.s  loc_A3AC
0xa3a2  ldloc.1
0xa3a3  brfalse.s loc_A3AB
0xa3a5  ldloc.1
0xa3a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa3ab  endfinally
0xa3ac  ldstr    aEndCheckIfCrmS// "End: Check if CRM Solutions are install"...
0xa3b1  ldc.i4.1
0xa3b2  newarr   [mscorlib]System.Object
0xa3b7  dup
0xa3b8  ldc.i4.0
0xa3b9  ldloc.0
0xa3ba  box      [mscorlib]System.Boolean
0xa3bf  stelem.ref
0xa3c0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteFormat(string, object[])
0xa3c5  ldloc.0
0xa3c6  ret
```
