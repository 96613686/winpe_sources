# Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::CreateNextPartition

- ea: `0x7c0`
- end: `0xa0c`
- name: `Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::CreateNextPartition`
- size: `588`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1f140`

## callees

- `0x7c0`
- `0xdb0`

## string_xrefs

- `0x7e1`: `CreateNextPartition: p_CreateNextAuditPartition`
- `0x7fd`: `p_CreateNextAuditPartition`
- `0x88e`: `Partition already exists for `
- `0x8bf`: `Partition already exists within 2 months of `
- `0x8fb`: `Successfully created partition with input date `
- `0x917`: `Unknown ReturnValue: {0} from {1}. Unable to create partition on current date {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x7c0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x7c5  stloc.0
0x7c6  ldsfld   string [mscorlib]System.String::Empty
0x7cb  stloc.1
0x7cc  ldsfld   string [mscorlib]System.String::Empty
0x7d1  stloc.2
0x7d2  ldc.i4.m1
0x7d3  stloc.3
0x7d4  ldc.i4.0
0x7d5  stloc.s  4
0x7d7  ldc.i4.m1
0x7d8  stloc.s  5
0x7da  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x7df  stloc.s  6
0x7e1  ldstr    aCreatenextpart// "CreateNextPartition: p_CreateNextAuditP"...
0x7e6  stloc.s  7
0x7e8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x7ed  stloc.s  8
0x7ef  ldloc.s  8
0x7f1  ldstr    aModulename// "moduleName"
0x7f6  ldloc.s  7
0x7f8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x7fd  ldstr    aPCreatenextaud// "p_CreateNextAuditPartition"
0x802  stloc.2
0x803  ldloc.s  6
0x805  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x80a  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x80f  stloc.s  9
0x811  ldloc.s  9
0x813  ldloc.2
0x814  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x819  ldloc.s  9
0x81b  ldc.i4.4
0x81c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x821  ldloc.s  9
0x823  callvirt instance class [System.Data]System.Data.IDbDataParameter [System.Data]System.Data.IDbCommand::CreateParameter()
0x828  stloc.s  0xA
0x82a  ldloc.s  0xA
0x82c  ldstr    aReturnvalue// "returnValue"
0x831  callvirt instance void [System.Data]System.Data.IDataParameter::set_ParameterName(string)
0x836  ldloc.s  0xA
0x838  ldc.i4.s 0xB
0x83a  callvirt instance void [System.Data]System.Data.IDataParameter::set_DbType(valuetype [System.Data]System.Data.DbType)
0x83f  ldloc.s  0xA
0x841  ldc.i4   0x7FFFFFFF
0x846  callvirt instance void [System.Data]System.Data.IDbDataParameter::set_Size(int32)
0x84b  ldloc.s  0xA
0x84d  ldc.i4.6
0x84e  callvirt instance void [System.Data]System.Data.IDataParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x853  ldloc.s  9
0x855  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x85a  ldloc.s  0xA
0x85c  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x861  pop
0x862  ldarg.0
0x863  ldloc.s  9
0x865  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x86a  pop
0x86b  ldloc.s  0xA
0x86d  callvirt instance object [System.Data]System.Data.IDataParameter::get_Value()
0x872  unbox.any [mscorlib]System.Int32
0x877  stloc.3
0x878  ldloc.3
0x879  ldc.i4.1
0x87a  bne.un.s loc_88A
0x87c  ldstr    aPartitionFunct// "Partition function AuditPFN Not found. "...
0x881  stloc.1
0x882  ldc.i4.0
0x883  stloc.s  4
0x885  br       loc_93C
0x88a  ldloc.3
0x88b  ldc.i4.2
0x88c  bne.un.s loc_8BB
0x88e  ldstr    aPartitionAlrea// "Partition already exists for "
0x893  ldarg.0
0x894  ldloc.0
0x895  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::GetNextQuarterEndDate(valuetype [mscorlib]System.DateTime date)
0x89a  stloc.s  0xB
0x89c  ldloca.s 0xB
0x89e  ldstr    aF// "F"
0x8a3  call     instance string [mscorlib]System.DateTime::ToString(string)
0x8a8  ldstr    aExiting// ". Exiting..."
0x8ad  call     string [mscorlib]System.String::Concat(string, string, string)
0x8b2  stloc.1
0x8b3  ldc.i4.0
0x8b4  stloc.s  4
0x8b6  br       loc_93C
0x8bb  ldloc.3
0x8bc  ldc.i4.3
0x8bd  bne.un.s loc_8E9
0x8bf  ldstr    aPartitionAlrea_0// "Partition already exists within 2 month"...
0x8c4  ldarg.0
0x8c5  ldloc.0
0x8c6  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::GetNextQuarterEndDate(valuetype [mscorlib]System.DateTime date)
0x8cb  stloc.s  0xB
0x8cd  ldloca.s 0xB
0x8cf  ldstr    aF// "F"
0x8d4  call     instance string [mscorlib]System.DateTime::ToString(string)
0x8d9  ldstr    aExiting// ". Exiting..."
0x8de  call     string [mscorlib]System.String::Concat(string, string, string)
0x8e3  stloc.1
0x8e4  ldc.i4.0
0x8e5  stloc.s  4
0x8e7  br.s     loc_93C
0x8e9  ldloc.3
0x8ea  ldc.i4.5
0x8eb  bne.un.s loc_8F8
0x8ed  ldstr    aNotSqlAzureOrS// "Not SQL Azure or SQL Enterprise Edition"...
0x8f2  stloc.1
0x8f3  ldc.i4.0
0x8f4  stloc.s  4
0x8f6  br.s     loc_93C
0x8f8  ldloc.3
0x8f9  brtrue.s loc_917
0x8fb  ldstr    aSuccessfullyCr// "Successfully created partition with inp"...
0x900  ldloca.s 0
0x902  ldstr    aF// "F"
0x907  call     instance string [mscorlib]System.DateTime::ToString(string)
0x90c  call     string [mscorlib]System.String::Concat(string, string)
0x911  stloc.1
0x912  ldc.i4.1
0x913  stloc.s  4
0x915  br.s     loc_93C
0x917  ldstr    aUnknownReturnv// "Unknown ReturnValue: {0} from {1}. Unab"...
0x91c  ldloc.3
0x91d  box      [mscorlib]System.Int32
0x922  ldloc.2
0x923  ldloca.s 0
0x925  ldstr    aF// "F"
0x92a  call     instance string [mscorlib]System.DateTime::ToString(string)
0x92f  call     string [mscorlib]System.String::Format(string, object, object, object)
0x934  stloc.1
0x935  ldloc.1
0x936  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x93b  throw
0x93c  leave.s  loc_94A
0x93e  ldloc.s  9
0x940  brfalse.s loc_949
0x942  ldloc.s  9
0x944  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x949  endfinally
0x94a  ldloc.s  6
0x94c  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x951  ldloc.s  6
0x953  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x958  stloc.s  0xC
0x95a  ldloca.s 0xC
0x95c  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x961  conv.i4
0x962  stloc.s  5
0x964  ldloc.s  8
0x966  ldstr    aMessage// "message"
0x96b  ldloc.1
0x96c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x971  ldloc.s  8
0x973  ldstr    aSqltext// "sqltext"
0x978  ldloc.2
0x979  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x97e  ldloc.s  8
0x980  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x985  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Platform.AuditServiceEventSource [Microsoft.Crm.ObjectModel]Microsoft.Crm.Platform.AuditServiceEventSource::get_Instance()
0x98a  ldarg.0
0x98b  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::_config
0x990  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x995  ldloc.s  7
0x997  ldloc.1
0x998  ldloc.s  5
0x99a  ldloc.2
0x99b  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Platform.AuditServiceEventSource::AuditPartitionCreateInformation(valuetype [mscorlib]System.Guid, string, string, int32, string)
0x9a0  leave.s  loc_A09
0x9a2  stloc.s  0xD
0x9a4  ldstr    aErrorWhileCrea// "Error while creating AuditBase table pa"...
0x9a9  stloc.1
0x9aa  ldloc.s  8
0x9ac  ldstr    aMessage// "message"
0x9b1  ldloc.1
0x9b2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x9b7  ldloc.s  8
0x9b9  ldstr    aSqltext// "sqltext"
0x9be  ldloc.2
0x9bf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x9c4  ldloc.s  8
0x9c6  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x9cb  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Platform.AuditServiceEventSource [Microsoft.Crm.ObjectModel]Microsoft.Crm.Platform.AuditServiceEventSource::get_Instance()
0x9d0  ldarg.0
0x9d1  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::_config
0x9d6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x9db  ldloc.s  7
0x9dd  ldloc.1
0x9de  ldloc.s  0xD
0x9e0  callvirt instance string [mscorlib]System.Object::ToString()
0x9e5  call     string [mscorlib]System.Environment::get_StackTrace()
0x9ea  ldloc.s  5
0x9ec  ldloc.2
0x9ed  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Platform.AuditServiceEventSource::AuditPartitionCreateError(valuetype [mscorlib]System.Guid, string, string, string, string, int32, string)
0x9f2  ldstr    aErrorWhileCrea_0// "Error while creating AuditBase table pa"...
0x9f7  ldloc.s  0xD
0x9f9  callvirt instance string [mscorlib]System.Object::ToString()
0x9fe  call     string [mscorlib]System.String::Concat(string, string)
0xa03  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xa08  throw
0xa09  ldloc.s  4
0xa0b  ret
```
