# Microsoft.Crm.ObjectModel.OrganizationManagementHelper::UpdateOrgIdReferences

- ea: `0xcea10`
- end: `0xcecbd`
- name: `Microsoft.Crm.ObjectModel.OrganizationManagementHelper::UpdateOrgIdReferences`
- size: `685`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x238880`

## callees

- `0xcea10`
- `0xced30`
- `0xced70`

## string_xrefs

- `0xcebeb`: `UpdateOrgIdReferences`
- `0xcec5c`: `UpdateOrgIdReferences`
- `0xcecac`: `UpdateOrgIdReferences`
- `0xcebf0`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\OrganizationManagementHelper.cs`
- `0xcec61`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\OrganizationManagementHelper.cs`
- `0xcecb1`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\OrganizationManagementHelper.cs`
- `0xcea45`: `UPDATE `
- `0xceac4`: `BulkDeleteFailure`
- `0xcec1c`: `UPDATE PluginTraceLogBase SET OrganizationId = @newOrganizationId WHERE OrganizationId = @oldOrganizationId`
- `0xcec6c`: `IF NOT EXISTS (SELECT OrganizationId FROM SharedCacheState WHERE OrganizationId = @newOrganizationId) UPDATE SharedCacheState SET OrganizationId = @newOrganizationId WHERE OrganizationId = @oldOrganizationId`

## pseudocode

```c

```

## disassembly

```asm
0xcea10  ldarg.2
0xcea11  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencesTo()
0xcea16  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xcea1b  stloc.1
0xcea1c  br       loc_CEBFB
0xcea21  ldloc.1
0xcea22  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xcea27  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship
0xcea2c  stloc.2
0xcea2d  ldarg.0
0xcea2e  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::ClearParameters(class [System.Data]System.Data.IDbCommand command)
0xcea33  ldloc.2
0xcea34  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0xcea39  stloc.3
0xcea3a  ldloc.3
0xcea3b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsLogical()
0xcea40  brtrue   loc_CEBFB
0xcea45  ldstr    aUpdate_2// "UPDATE "
0xcea4a  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0xcea4f  stloc.s  4
0xcea51  ldloc.2
0xcea52  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0xcea57  stloc.s  5
0xcea59  ldloc.3
0xcea5a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsStoredOnPrimaryTable()
0xcea5f  brfalse.s loc_CEA72
0xcea61  ldloc.s  4
0xcea63  ldloc.s  5
0xcea65  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_BaseTableName()
0xcea6a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xcea6f  pop
0xcea70  br.s     loc_CEA81
0xcea72  ldloc.s  4
0xcea74  ldloc.s  5
0xcea76  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ExtensionTableName()
0xcea7b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xcea80  pop
0xcea81  ldloc.s  4
0xcea83  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcea88  ldstr    aSet0Neworganiz// " SET {0} = @newOrganizationId "
0xcea8d  ldc.i4.1
0xcea8e  newarr   [mscorlib]System.Object
0xcea93  dup
0xcea94  ldc.i4.0
0xcea95  ldloc.3
0xcea96  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0xcea9b  stelem.ref
0xcea9c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xceaa1  pop
0xceaa2  ldloc.2
0xceaa3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0xceaa8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PhysicalName()
0xceaad  ldstr    aAsyncoperation_3// "AsyncOperation"
0xceab2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xceab7  brtrue.s loc_CEAD3
0xceab9  ldloc.2
0xceaba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0xceabf  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PhysicalName()
0xceac4  ldstr    aBulkdeletefail// "BulkDeleteFailure"
0xceac9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xceace  brfalse  loc_CEB90
0xcead3  ldloc.3
0xcead4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_HasChildAttributes()
0xcead9  brfalse  loc_CEB90
0xceade  ldloc.3
0xceadf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ChildAttributes()
0xceae4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::GetEnumerator()
0xceae9  stloc.s  6
0xceaeb  br       loc_CEB76
0xceaf0  ldloc.s  6
0xceaf2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Current()
0xceaf7  stloc.s  7
0xceaf9  ldloc.s  7
0xceafb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsLogical()
0xceb00  brtrue.s loc_CEB76
0xceb02  ldloc.s  7
0xceb04  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0xceb09  stloc.s  8
0xceb0b  ldloc.s  8
0xceb0d  ldstr    aRegardingobjec_9// "RegardingObjectIdName"
0xceb12  call     bool [mscorlib]System.String::op_Equality(string, string)
0xceb17  brtrue.s loc_CEB27
0xceb19  ldloc.s  8
0xceb1b  ldstr    aOrganizationid_8// "OrganizationIdName"
0xceb20  call     bool [mscorlib]System.String::op_Equality(string, string)
0xceb25  brfalse.s loc_CEB76
0xceb27  ldloc.s  4
0xceb29  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xceb2e  ldstr    a0Newfriendlyna// ", {0} = @newFriendlyName "
0xceb33  ldc.i4.1
0xceb34  newarr   [mscorlib]System.Object
0xceb39  dup
0xceb3a  ldc.i4.0
0xceb3b  ldloc.s  7
0xceb3d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0xceb42  stelem.ref
0xceb43  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xceb48  pop
0xceb49  ldarg.0
0xceb4a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xceb4f  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0xceb54  brfalse.s loc_CEB68
0xceb56  ldarg.0
0xceb57  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xceb5c  ldstr    aNewfriendlynam// "@newFriendlyName"
0xceb61  callvirt instance object [System.Data]System.Data.IDataParameterCollection::get_Item(string)
0xceb66  brtrue.s loc_CEB76
0xceb68  ldarg.0
0xceb69  ldarg.1
0xceb6a  ldstr    aNewfriendlynam// "@newFriendlyName"
0xceb6f  ldc.i4.s 0x10
0xceb71  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0xceb76  ldloc.s  6
0xceb78  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xceb7d  brtrue   loc_CEAF0
0xceb82  leave.s  loc_CEB90
0xceb84  ldloc.s  6
0xceb86  brfalse.s loc_CEB8F
0xceb88  ldloc.s  6
0xceb8a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xceb8f  endfinally
0xceb90  ldloc.s  4
0xceb92  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xceb97  ldstr    aWhere0Oldorgan// " WHERE {0} = @oldOrganizationId "
0xceb9c  ldc.i4.1
0xceb9d  newarr   [mscorlib]System.Object
0xceba2  dup
0xceba3  ldc.i4.0
0xceba4  ldloc.3
0xceba5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0xcebaa  stelem.ref
0xcebab  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xcebb0  pop
0xcebb1  ldarg.0
0xcebb2  ldloc.s  4
0xcebb4  callvirt instance string [mscorlib]System.Object::ToString()
0xcebb9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xcebbe  ldarg.0
0xcebbf  ldarg.3
0xcebc0  box      [mscorlib]System.Guid
0xcebc5  ldstr    aNeworganizatio// "@newOrganizationId"
0xcebca  ldc.i4.s 9
0xcebcc  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0xcebd1  ldarg.0
0xcebd2  ldarg.s  4
0xcebd4  box      [mscorlib]System.Guid
0xcebd9  ldstr    aOldorganizatio_0// "@oldOrganizationId"
0xcebde  ldc.i4.s 9
0xcebe0  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0xcebe5  ldarg.0
0xcebe6  ldc.i4   0x115
0xcebeb  ldstr    aUpdateorgidref// "UpdateOrgIdReferences"
0xcebf0  ldstr    aDA1SSrcCoreObj_21// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0xcebf5  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xcebfa  pop
0xcebfb  ldloc.1
0xcebfc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcec01  brtrue   loc_CEA21
0xcec06  leave.s  loc_CEC1C
0xcec08  ldloc.1
0xcec09  isinst   [mscorlib]System.IDisposable
0xcec0e  stloc.s  9
0xcec10  ldloc.s  9
0xcec12  brfalse.s loc_CEC1B
0xcec14  ldloc.s  9
0xcec16  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcec1b  endfinally
0xcec1c  ldstr    aUpdatePlugintr// "UPDATE PluginTraceLogBase SET Organizat"...
0xcec21  stloc.0
0xcec22  ldarg.0
0xcec23  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::ClearParameters(class [System.Data]System.Data.IDbCommand command)
0xcec28  ldarg.0
0xcec29  ldloc.0
0xcec2a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xcec2f  ldarg.0
0xcec30  ldarg.3
0xcec31  box      [mscorlib]System.Guid
0xcec36  ldstr    aNeworganizatio// "@newOrganizationId"
0xcec3b  ldc.i4.s 9
0xcec3d  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0xcec42  ldarg.0
0xcec43  ldarg.s  4
0xcec45  box      [mscorlib]System.Guid
0xcec4a  ldstr    aOldorganizatio_0// "@oldOrganizationId"
0xcec4f  ldc.i4.s 9
0xcec51  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0xcec56  ldarg.0
0xcec57  ldc.i4   0x11D
0xcec5c  ldstr    aUpdateorgidref// "UpdateOrgIdReferences"
0xcec61  ldstr    aDA1SSrcCoreObj_21// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0xcec66  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xcec6b  pop
0xcec6c  ldstr    aIfNotExistsSel_0// "IF NOT EXISTS (SELECT OrganizationId FR"...
0xcec71  stloc.0
0xcec72  ldarg.0
0xcec73  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::ClearParameters(class [System.Data]System.Data.IDbCommand command)
0xcec78  ldarg.0
0xcec79  ldloc.0
0xcec7a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xcec7f  ldarg.0
0xcec80  ldarg.3
0xcec81  box      [mscorlib]System.Guid
0xcec86  ldstr    aNeworganizatio// "@newOrganizationId"
0xcec8b  ldc.i4.s 9
0xcec8d  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0xcec92  ldarg.0
0xcec93  ldarg.s  4
0xcec95  box      [mscorlib]System.Guid
0xcec9a  ldstr    aOldorganizatio_0// "@oldOrganizationId"
0xcec9f  ldc.i4.s 9
0xceca1  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0xceca6  ldarg.0
0xceca7  ldc.i4   0x124
0xcecac  ldstr    aUpdateorgidref// "UpdateOrgIdReferences"
0xcecb1  ldstr    aDA1SSrcCoreObj_21// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0xcecb6  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xcecbb  pop
0xcecbc  ret
```
