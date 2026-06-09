# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::FixSystemRequiredMetadata

- ea: `0x1ed40`
- end: `0x1edc3`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::FixSystemRequiredMetadata`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1ed40`

## string_xrefs

- `0x1ed99`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\OrganizationDatabaseAccess.cs`
- `0x1ed40`: `update MetadataSchema.Attribute\n								set AttributeRequiredLevelId = @systemRequired\n								where AttributeId in \n								(\n									select customAttr.AttributeId\n									from MetadataSchema.Attribute systemAttr inner join MetadataSchema.Attribute customAttr on systemAttr.AttributeId = customAttr.AttributeId\n									where systemAttr.AttributeRequiredLevelId =  @systemRequired\n									and systemAttr.SolutionId = @systemSolutionId\n									and customAttr.SolutionId <> @system`

## pseudocode

```c

```

## disassembly

```asm
0x1ed40  ldstr    aUpdateMetadata// "update MetadataSchema.Attribute\r\n\t\t"...
0x1ed45  stloc.0
0x1ed46  ldarg.1
0x1ed47  ldc.i4.0
0x1ed48  ldc.i4.0
0x1ed49  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1ed4e  stloc.1
0x1ed4f  ldloc.1
0x1ed50  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1ed55  ldloc.1
0x1ed56  ldloc.0
0x1ed57  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x1ed5c  stloc.2
0x1ed5d  ldloc.2
0x1ed5e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1ed63  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1ed68  dup
0x1ed69  ldstr    aSystemrequired// "@systemRequired"
0x1ed6e  ldstr    aSystemrequired_0// "systemrequired"
0x1ed73  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ed78  pop
0x1ed79  ldstr    aSystemsolution// "@systemSolutionId"
0x1ed7e  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x1ed83  box      [mscorlib]System.Guid
0x1ed88  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ed8d  pop
0x1ed8e  ldloc.2
0x1ed8f  ldc.i4   0x8D6
0x1ed94  ldstr    aFixsystemrequi// "FixSystemRequiredMetadata"
0x1ed99  ldstr    aDDbsShDccm2110_31// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x1ed9e  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x1eda3  pop
0x1eda4  leave.s  loc_1EDB0
0x1eda6  ldloc.2
0x1eda7  brfalse.s loc_1EDAF
0x1eda9  ldloc.2
0x1edaa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1edaf  endfinally
0x1edb0  ldloc.1
0x1edb1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x1edb6  leave.s  loc_1EDC2
0x1edb8  ldloc.1
0x1edb9  brfalse.s loc_1EDC1
0x1edbb  ldloc.1
0x1edbc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1edc1  endfinally
0x1edc2  ret
```
