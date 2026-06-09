# Microsoft.Crm.Platform.SolutionAwareComponents.MPODeleteIdAction::Execute

- ea: `0x345d0`
- end: `0x34709`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.MPODeleteIdAction::Execute`
- size: `313`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x345d0`
- `0x36110`
- `0x37da0`
- `0x42ed0`
- `0x66ae0`

## string_xrefs

- `0x34604`: `DELETE FROM [{0}] WHERE [{1}] = (@id)`
- `0x346d6`: `Metadata entity {0} does not have an ids table - id {1} therefore not deleted from an ids table`

## pseudocode

```c

```

## disassembly

```asm
0x345d0  ldarg.0
0x345d1  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x345d6  castclass Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance
0x345db  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance::get_Entity()
0x345e0  stloc.0
0x345e1  ldloc.0
0x345e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x345e7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_IdsTableName()
0x345ec  brfalse  loc_346CE
0x345f1  ldarg.1
0x345f2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x345f7  ldc.i4.1
0x345f8  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(bool)
0x345fd  stloc.1
0x345fe  ldloc.1
0x345ff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x34604  ldstr    aDeleteFrom0Whe_0// "DELETE FROM [{0}] WHERE [{1}] = (@id)"
0x34609  ldc.i4.2
0x3460a  newarr   [mscorlib]System.Object
0x3460f  dup
0x34610  ldc.i4.0
0x34611  ldloc.0
0x34612  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x34617  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_IdsTableName()
0x3461c  stelem.ref
0x3461d  dup
0x3461e  ldc.i4.1
0x3461f  ldloc.0
0x34620  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x34625  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x3462a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_PhysicalName()
0x3462f  stelem.ref
0x34630  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x34635  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3463a  ldloc.1
0x3463b  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x34640  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x34645  ldstr    aId_4// "@id"
0x3464a  ldloc.0
0x3464b  ldloc.0
0x3464c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x34651  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x34656  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x3465b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x34660  unbox.any [mscorlib]System.Guid
0x34665  box      [mscorlib]System.Guid
0x3466a  ldc.i4.1
0x3466b  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToSqlParameter(object, bool)
0x34670  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x34675  pop
0x34676  ldarg.1
0x34677  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3467c  ldc.i4.s 0x14
0x3467e  ldstr    aDeletingId0Fro// "Deleting id {0} from the ids table {1}"
0x34683  ldc.i4.2
0x34684  newarr   [mscorlib]System.Object
0x34689  dup
0x3468a  ldc.i4.0
0x3468b  ldloc.0
0x3468c  ldloc.0
0x3468d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x34692  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x34697  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x3469c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x346a1  stelem.ref
0x346a2  dup
0x346a3  ldc.i4.1
0x346a4  ldloc.0
0x346a5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x346aa  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_IdsTableName()
0x346af  stelem.ref
0x346b0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x346b5  ldloc.1
0x346b6  ldarg.1
0x346b7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x346bc  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x346c1  pop
0x346c2  leave.s  loc_34708
0x346c4  ldloc.1
0x346c5  brfalse.s loc_346CD
0x346c7  ldloc.1
0x346c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x346cd  endfinally
0x346ce  ldarg.1
0x346cf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x346d4  ldc.i4.s 0x14
0x346d6  ldstr    aMetadataEntity// "Metadata entity {0} does not have an id"...
0x346db  ldc.i4.2
0x346dc  newarr   [mscorlib]System.Object
0x346e1  dup
0x346e2  ldc.i4.0
0x346e3  ldloc.0
0x346e4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityName()
0x346e9  stelem.ref
0x346ea  dup
0x346eb  ldc.i4.1
0x346ec  ldloc.0
0x346ed  ldloc.0
0x346ee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x346f3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x346f8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x346fd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x34702  stelem.ref
0x34703  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x34708  ret
```
