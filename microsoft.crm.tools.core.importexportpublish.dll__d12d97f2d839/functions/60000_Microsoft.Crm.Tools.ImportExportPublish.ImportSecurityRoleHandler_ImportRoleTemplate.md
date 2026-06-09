# Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::ImportRoleTemplate

- ea: `0x60000`
- end: `0x600b4`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::ImportRoleTemplate`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x5f250`

## callees

- `0x60000`
- `0x63df0`

## string_xrefs

- `0x60013`: `@roletemplateid`
- `0x60044`: `INSERT INTO RoleTemplateBase (RoleTemplateId, Name, Upgrading)\n									SELECT @roletemplateid,@rolename,@upgrading\n									WHERE\n										NOT EXISTS(\n										 SELECT RoleTemplateId from RoleTemplateBase where RoleTemplateId = @roletemplateid\n										)`
- `0x60057`: `ImportRoleTemplate`
- `0x6005c`: `D:\a\1\s\src\Core\ObjectModel\ImportExportPublish\ImportSecurityRoleHandler.cs`
- `0x60075`: `Role template import: FAILURE, Could not add role template with name {0} and id {1} to RoleTemplateBase. Role id for this role template is {2}. Upgrading used is {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x60000  ldarg.3
0x60001  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x60006  stloc.0
0x60007  ldloc.0
0x60008  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x6000d  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x60012  dup
0x60013  ldstr    aRoletemplateid_0// "@roletemplateid"
0x60018  ldarg.1
0x60019  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6001e  pop
0x6001f  dup
0x60020  ldstr    aRolename// "@rolename"
0x60025  ldarg.2
0x60026  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6002b  pop
0x6002c  ldstr    aUpgrading// "@upgrading"
0x60031  ldarg.s  4
0x60033  brtrue.s loc_60038
0x60035  ldc.i4.0
0x60036  br.s     loc_60039
0x60038  ldc.i4.1
0x60039  box      [mscorlib]System.Int32
0x6003e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x60043  pop
0x60044  ldstr    aInsertIntoRole// "INSERT INTO RoleTemplateBase (RoleTempl"...
0x60049  stloc.1
0x6004a  ldloc.0
0x6004b  ldloc.1
0x6004c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x60051  ldloc.0
0x60052  ldc.i4   0x1FA
0x60057  ldstr    aImportroletemp// "ImportRoleTemplate"
0x6005c  ldstr    aDA1SSrcCoreObj_3// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Im"...
0x60061  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x60066  pop
0x60067  leave.s  loc_600B3
0x60069  stloc.2
0x6006a  ldarg.0
0x6006b  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::tracer
0x60070  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x60075  ldstr    aRoleTemplateIm// "Role template import: FAILURE, Could no"...
0x6007a  ldc.i4.4
0x6007b  newarr   [mscorlib]System.Object
0x60080  dup
0x60081  ldc.i4.0
0x60082  ldarg.2
0x60083  stelem.ref
0x60084  dup
0x60085  ldc.i4.1
0x60086  ldarg.1
0x60087  stelem.ref
0x60088  dup
0x60089  ldc.i4.2
0x6008a  ldarg.0
0x6008b  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x60090  stelem.ref
0x60091  dup
0x60092  ldc.i4.3
0x60093  ldarg.s  4
0x60095  box      [mscorlib]System.Boolean
0x6009a  stelem.ref
0x6009b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x600a0  ldloc.2
0x600a1  ldc.i4.3
0x600a2  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x600a7  rethrow
0x600a9  ldloc.0
0x600aa  brfalse.s loc_600B2
0x600ac  ldloc.0
0x600ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x600b2  endfinally
0x600b3  ret
```
