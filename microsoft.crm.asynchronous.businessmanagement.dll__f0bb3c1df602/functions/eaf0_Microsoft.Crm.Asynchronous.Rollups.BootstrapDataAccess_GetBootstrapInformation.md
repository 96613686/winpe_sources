# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::GetBootstrapInformation

- ea: `0xeaf0`
- end: `0xed2d`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::GetBootstrapInformation`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0xef40`

## callees

- `0xeaf0`

## string_xrefs

- `0xeb6b`: `RollupPropertiesId`
- `0xebe8`: `@rollupPropertiesId`
- `0xeb03`: `SELECT {0}, {1}, {2}, {3}, {4}, {5} FROM {6} WHERE {7} = @rollupPropertiesId`
- `0xec05`: `d:\dbs\sh\dccm2\1101_190851\cmd\77\src\Core\ObjectModel\Async\Handlers\BusinessManagement\Rollups\BootstrapDataAccess.cs`

## pseudocode

```c

```

## disassembly

```asm
0xeaf0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xeaf5  stloc.0
0xeaf6  ldloc.0
0xeaf7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xeafc  pop
0xeafd  ldloc.0
0xeafe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xeb03  ldstr    aSelect012345Fr// "SELECT {0}, {1}, {2}, {3}, {4}, {5} FRO"...
0xeb08  ldc.i4.8
0xeb09  newarr   [mscorlib]System.Object
0xeb0e  dup
0xeb0f  ldc.i4.0
0xeb10  ldstr    aAllowhierarchy// "AllowHierarchyOnSource"
0xeb15  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xeb1a  stelem.ref
0xeb1b  dup
0xeb1c  ldc.i4.1
0xeb1d  ldstr    aRollupentitylo// "RollupEntityLogicalName"
0xeb22  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xeb27  stelem.ref
0xeb28  dup
0xeb29  ldc.i4.2
0xeb2a  ldstr    aBootstrapstepn// "BootstrapStepNumber"
0xeb2f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xeb34  stelem.ref
0xeb35  dup
0xeb36  ldc.i4.3
0xeb37  ldstr    aBootstrapretry// "BootstrapRetryCount"
0xeb3c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xeb41  stelem.ref
0xeb42  dup
0xeb43  ldc.i4.4
0xeb44  ldstr    aInitialvalueca// "InitialValueCalculationStatus"
0xeb49  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xeb4e  stelem.ref
0xeb4f  dup
0xeb50  ldc.i4.5
0xeb51  ldstr    aBootstraprollu// "BootstrapRollupAsyncJobId"
0xeb56  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xeb5b  stelem.ref
0xeb5c  dup
0xeb5d  ldc.i4.6
0xeb5e  ldstr    aRollupproperti_2// "RollupProperties"
0xeb63  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xeb68  stelem.ref
0xeb69  dup
0xeb6a  ldc.i4.7
0xeb6b  ldstr    aRollupproperti// "RollupPropertiesId"
0xeb70  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xeb75  stelem.ref
0xeb76  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xeb7b  pop
0xeb7c  ldloc.0
0xeb7d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xeb82  pop
0xeb83  ldloca.s 1
0xeb85  ldc.i4.m1
0xeb86  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xeb8b  ldloca.s 2
0xeb8d  ldc.i4.m1
0xeb8e  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xeb93  ldc.i4.m1
0xeb94  stloc.3
0xeb95  ldloca.s 4
0xeb97  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0xeb9d  ldsfld   string [mscorlib]System.String::Empty
0xeba2  stloc.s  5
0xeba4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xeba9  stloc.s  6
0xebab  ldarg.0
0xebac  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0xebb1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xebb6  ldc.i4.0
0xebb7  ldc.i4.0
0xebb8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xebbd  stloc.s  7
0xebbf  ldloc.s  7
0xebc1  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0xebc6  stloc.s  8
0xebc8  ldloc.s  7
0xebca  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xebcf  ldloc.s  8
0xebd1  ldloc.0
0xebd2  callvirt instance string [mscorlib]System.Object::ToString()
0xebd7  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xebdc  ldloc.s  8
0xebde  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xebe3  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xebe8  ldstr    aRollupproperti_0// "@rollupPropertiesId"
0xebed  ldarg.1
0xebee  box      [mscorlib]System.Guid
0xebf3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xebf8  pop
0xebf9  ldloc.s  8
0xebfb  ldc.i4   0xDB
0xec00  ldstr    aGetbootstrapin// "GetBootstrapInformation"
0xec05  ldstr    aDDbsShDccm2110_4// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xec0a  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xec0f  stloc.s  9
0xec11  ldloc.s  9
0xec13  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xec18  brfalse.s loc_EC98
0xec1a  ldloc.s  9
0xec1c  ldstr    aAllowhierarchy// "AllowHierarchyOnSource"
0xec21  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xec26  isinst   valuetype [mscorlib]System.Nullable`1<bool>
0xec2b  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0xec30  stloc.s  4
0xec32  ldloc.s  9
0xec34  ldstr    aRollupentitylo// "RollupEntityLogicalName"
0xec39  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xec3e  isinst   [mscorlib]System.String
0xec43  stloc.s  5
0xec45  ldloc.s  9
0xec47  ldstr    aBootstrapstepn// "BootstrapStepNumber"
0xec4c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xec51  isinst   valuetype [mscorlib]System.Nullable`1<int32>
0xec56  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0xec5b  stloc.1
0xec5c  ldloc.s  9
0xec5e  ldstr    aBootstrapretry// "BootstrapRetryCount"
0xec63  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xec68  isinst   valuetype [mscorlib]System.Nullable`1<int32>
0xec6d  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0xec72  stloc.2
0xec73  ldloc.s  9
0xec75  ldstr    aInitialvalueca// "InitialValueCalculationStatus"
0xec7a  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xec7f  unbox.any [mscorlib]System.Int32
0xec84  stloc.3
0xec85  ldloc.s  9
0xec87  ldstr    aBootstraprollu// "BootstrapRollupAsyncJobId"
0xec8c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xec91  unbox.any [mscorlib]System.Guid
0xec96  stloc.s  6
0xec98  leave.s  loc_ECBE
0xec9a  ldloc.s  9
0xec9c  brfalse.s loc_ECA5
0xec9e  ldloc.s  9
0xeca0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xeca5  endfinally
0xeca6  ldloc.s  8
0xeca8  brfalse.s loc_ECB1
0xecaa  ldloc.s  8
0xecac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xecb1  endfinally
0xecb2  ldloc.s  7
0xecb4  brfalse.s loc_ECBD
0xecb6  ldloc.s  7
0xecb8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xecbd  endfinally
0xecbe  ldloc.1
0xecbf  stloc.s  0xA
0xecc1  ldc.i4.m1
0xecc2  stloc.s  0xB
0xecc4  ldloca.s 0xA
0xecc6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0xeccb  ldloc.s  0xB
0xeccd  beq.s    loc_ECD2
0xeccf  ldc.i4.0
0xecd0  br.s     loc_ECD9
0xecd2  ldloca.s 0xA
0xecd4  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xecd9  brtrue.s loc_ED13
0xecdb  ldloc.2
0xecdc  stloc.s  0xA
0xecde  ldc.i4.m1
0xecdf  stloc.s  0xB
0xece1  ldloca.s 0xA
0xece3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0xece8  ldloc.s  0xB
0xecea  beq.s    loc_ECEF
0xecec  ldc.i4.0
0xeced  br.s     loc_ECF6
0xecef  ldloca.s 0xA
0xecf1  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xecf6  brtrue.s loc_ED13
0xecf8  ldloc.3
0xecf9  ldc.i4.m1
0xecfa  beq.s    loc_ED13
0xecfc  ldloc.s  5
0xecfe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xed03  brtrue.s loc_ED13
0xed05  ldloc.s  6
0xed07  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xed0c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xed11  brfalse.s loc_ED1E
0xed13  ldstr    aBootstrapValue// "Bootstrap values were not initialized c"...
0xed18  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xed1d  throw
0xed1e  ldloc.1
0xed1f  ldloc.2
0xed20  ldloc.s  4
0xed22  ldloc.s  5
0xed24  ldloc.3
0xed25  ldloc.s  6
0xed27  newobj   instance void class [mscorlib]System.Tuple`6<valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<bool>, string, int32, valuetype [mscorlib]System.Guid>::.ctor(var<u1>, !!T0, var<u1>, void, var<u1>, bool)
0xed2c  ret
```
