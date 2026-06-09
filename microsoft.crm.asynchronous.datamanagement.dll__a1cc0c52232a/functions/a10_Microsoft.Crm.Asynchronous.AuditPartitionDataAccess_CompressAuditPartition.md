# Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::CompressAuditPartition

- ea: `0xa10`
- end: `0xdb0`
- name: `Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::CompressAuditPartition`
- size: `928`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f250`

## callees

- `0xa10`
- `0xdf0`
- `0xe00`
- `0xe10`

## string_xrefs

- `0xa16`: `p_ChangePartitonDataCompression`
- `0xa31`: `CreateNextPartition: p_ChangePartitonDataCompression`
- `0xa99`: `IOrganizationConfiguration is null.`
- `0xadd`: `@skipAuditPartitionsToCompress`
- `0xb18`: `@maxAuditIndexesToCompressOnOlderPartition`
- `0xb53`: `@compressAuditClusteredIndexOnOlderPartition`
- `0xc05`: `Successfully compressed AuditBase table older partition(s).`
- `0xc49`: `PartitionCompressTimeout`
- `0xd01`: `PartitionCompressTimeout`
- `0xc5c`: `skipAuditPartitionsToCompress`
- `0xd14`: `skipAuditPartitionsToCompress`
- `0xc6f`: `maxAuditIndexesToCompressOnOlderPartition`
- `0xd27`: `maxAuditIndexesToCompressOnOlderPartition`
- `0xc82`: `compressAuditClusteredIndexOnOlderPartition`
- `0xd3a`: `compressAuditClusteredIndexOnOlderPartition`
- `0xcea`: `Error while Compressing AuditBase table older partition(s).`

## pseudocode

```c

```

## disassembly

```asm
0xa10  ldc.i4.m1
0xa11  stloc.0
0xa12  ldc.i4.m1
0xa13  stloc.1
0xa14  ldc.i4.0
0xa15  stloc.2
0xa16  ldstr    aPChangepartito// "p_ChangePartitonDataCompression"
0xa1b  stloc.3
0xa1c  ldsfld   string [mscorlib]System.String::Empty
0xa21  stloc.s  4
0xa23  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0xa28  stloc.s  5
0xa2a  ldloc.s  5
0xa2c  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0xa31  ldstr    aCreatenextpart_0// "CreateNextPartition: p_ChangePartitonDa"...
0xa36  stloc.s  6
0xa38  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xa3d  stloc.s  7
0xa3f  ldloc.s  7
0xa41  ldstr    aModulename// "moduleName"
0xa46  ldloc.s  6
0xa48  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa4d  ldarg.0
0xa4e  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::_config
0xa53  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xa58  ldc.i4.0
0xa59  ldc.i4.0
0xa5a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xa5f  stloc.s  8
0xa61  ldarg.0
0xa62  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::_config
0xa67  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xa6c  call     int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ShrinkDatabaseUtility::ReindexAllOperationTimeout(valuetype [mscorlib]System.Guid)
0xa71  stloc.s  9
0xa73  ldarg.0
0xa74  ldloc.s  8
0xa76  call     instance int32 Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::GetSkipAuditPartitionsToCompress(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa7b  stloc.s  0xA
0xa7d  ldarg.0
0xa7e  ldloc.s  8
0xa80  call     instance int32 Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::GetMaxAuditIndexesToCompressOnOlderPartition(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa85  stloc.s  0xB
0xa87  ldarg.0
0xa88  ldloc.s  8
0xa8a  call     instance bool Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::IsCompressAuditClusteredIndexOnOlderPartitionEnabled(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa8f  stloc.s  0xC
0xa91  ldarg.0
0xa92  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::_config
0xa97  brtrue.s loc_AA4
0xa99  ldstr    aIorganizationc// "IOrganizationConfiguration is null."
0xa9e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xaa3  throw
0xaa4  ldarg.0
0xaa5  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::_config
0xaaa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xaaf  pop
0xab0  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xab5  stloc.s  0xD
0xab7  ldloc.s  0xD
0xab9  ldloc.3
0xaba  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xabf  ldloc.s  0xD
0xac1  ldc.i4.4
0xac2  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0xac7  ldloc.s  0xD
0xac9  ldc.i4.2
0xaca  ldloc.s  9
0xacc  mul
0xacd  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandTimeout(int32)
0xad2  ldloc.s  0xD
0xad4  callvirt instance class [System.Data]System.Data.IDbDataParameter [System.Data]System.Data.IDbCommand::CreateParameter()
0xad9  stloc.s  0xE
0xadb  ldloc.s  0xE
0xadd  ldstr    aSkipauditparti// "@skipAuditPartitionsToCompress"
0xae2  callvirt instance void [System.Data]System.Data.IDataParameter::set_ParameterName(string)
0xae7  ldloc.s  0xE
0xae9  ldc.i4.s 0xB
0xaeb  callvirt instance void [System.Data]System.Data.IDataParameter::set_DbType(valuetype [System.Data]System.Data.DbType)
0xaf0  ldloc.s  0xE
0xaf2  ldloc.s  0xA
0xaf4  box      [mscorlib]System.Int32
0xaf9  callvirt instance void [System.Data]System.Data.IDataParameter::set_Value(object)
0xafe  ldloc.s  0xD
0xb00  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xb05  ldloc.s  0xE
0xb07  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0xb0c  pop
0xb0d  ldloc.s  0xD
0xb0f  callvirt instance class [System.Data]System.Data.IDbDataParameter [System.Data]System.Data.IDbCommand::CreateParameter()
0xb14  stloc.s  0xF
0xb16  ldloc.s  0xF
0xb18  ldstr    aMaxauditindexe// "@maxAuditIndexesToCompressOnOlderPartit"...
0xb1d  callvirt instance void [System.Data]System.Data.IDataParameter::set_ParameterName(string)
0xb22  ldloc.s  0xF
0xb24  ldc.i4.s 0xB
0xb26  callvirt instance void [System.Data]System.Data.IDataParameter::set_DbType(valuetype [System.Data]System.Data.DbType)
0xb2b  ldloc.s  0xF
0xb2d  ldloc.s  0xB
0xb2f  box      [mscorlib]System.Int32
0xb34  callvirt instance void [System.Data]System.Data.IDataParameter::set_Value(object)
0xb39  ldloc.s  0xD
0xb3b  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xb40  ldloc.s  0xF
0xb42  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0xb47  pop
0xb48  ldloc.s  0xD
0xb4a  callvirt instance class [System.Data]System.Data.IDbDataParameter [System.Data]System.Data.IDbCommand::CreateParameter()
0xb4f  stloc.s  0x10
0xb51  ldloc.s  0x10
0xb53  ldstr    aCompressauditc// "@compressAuditClusteredIndexOnOlderPart"...
0xb58  callvirt instance void [System.Data]System.Data.IDataParameter::set_ParameterName(string)
0xb5d  ldloc.s  0x10
0xb5f  ldc.i4.3
0xb60  callvirt instance void [System.Data]System.Data.IDataParameter::set_DbType(valuetype [System.Data]System.Data.DbType)
0xb65  ldloc.s  0x10
0xb67  ldloc.s  0xC
0xb69  box      [mscorlib]System.Boolean
0xb6e  callvirt instance void [System.Data]System.Data.IDataParameter::set_Value(object)
0xb73  ldloc.s  0xD
0xb75  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xb7a  ldloc.s  0x10
0xb7c  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0xb81  pop
0xb82  ldloc.s  0xD
0xb84  callvirt instance class [System.Data]System.Data.IDbDataParameter [System.Data]System.Data.IDbCommand::CreateParameter()
0xb89  stloc.s  0x11
0xb8b  ldloc.s  0x11
0xb8d  ldstr    aReturnvalue// "returnValue"
0xb92  callvirt instance void [System.Data]System.Data.IDataParameter::set_ParameterName(string)
0xb97  ldloc.s  0x11
0xb99  ldc.i4.s 0xB
0xb9b  callvirt instance void [System.Data]System.Data.IDataParameter::set_DbType(valuetype [System.Data]System.Data.DbType)
0xba0  ldloc.s  0x11
0xba2  ldc.i4   0x7FFFFFFF
0xba7  callvirt instance void [System.Data]System.Data.IDbDataParameter::set_Size(int32)
0xbac  ldloc.s  0x11
0xbae  ldc.i4.6
0xbaf  callvirt instance void [System.Data]System.Data.IDataParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0xbb4  ldloc.s  0xD
0xbb6  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xbbb  ldloc.s  0x11
0xbbd  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0xbc2  pop
0xbc3  ldarg.0
0xbc4  ldloc.s  0xD
0xbc6  ldarg.0
0xbc7  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::_config
0xbcc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xbd1  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Guid)
0xbd6  pop
0xbd7  ldloc.s  0x11
0xbd9  callvirt instance object [System.Data]System.Data.IDataParameter::get_Value()
0xbde  unbox.any [mscorlib]System.Int32
0xbe3  stloc.0
0xbe4  ldloc.0
0xbe5  ldc.i4.1
0xbe6  bne.un.s loc_BF3
0xbe8  ldstr    aPartitionFunct// "Partition function AuditPFN Not found. "...
0xbed  stloc.s  4
0xbef  ldc.i4.0
0xbf0  stloc.2
0xbf1  br.s     loc_C2B
0xbf3  ldloc.0
0xbf4  ldc.i4.5
0xbf5  bne.un.s loc_C02
0xbf7  ldstr    aNotSqlAzureOrS// "Not SQL Azure or SQL Enterprise Edition"...
0xbfc  stloc.s  4
0xbfe  ldc.i4.0
0xbff  stloc.2
0xc00  br.s     loc_C2B
0xc02  ldloc.0
0xc03  brtrue.s loc_C10
0xc05  ldstr    aSuccessfullyCo// "Successfully compressed AuditBase table"...
0xc0a  stloc.s  4
0xc0c  ldc.i4.1
0xc0d  stloc.2
0xc0e  br.s     loc_C2B
0xc10  ldstr    aUnknownReturnv_0// "Unknown ReturnValue: {0} from {1}"
0xc15  ldloc.0
0xc16  box      [mscorlib]System.Int32
0xc1b  ldloc.3
0xc1c  call     string [mscorlib]System.String::Format(string, object, object)
0xc21  stloc.s  4
0xc23  ldloc.s  4
0xc25  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xc2a  throw
0xc2b  leave.s  loc_C39
0xc2d  ldloc.s  0xD
0xc2f  brfalse.s loc_C38
0xc31  ldloc.s  0xD
0xc33  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc38  endfinally
0xc39  ldloc.s  7
0xc3b  ldstr    aMessage// "message"
0xc40  ldloc.s  4
0xc42  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc47  ldloc.s  7
0xc49  ldstr    aPartitioncompr// "PartitionCompressTimeout"
0xc4e  ldloca.s 9
0xc50  call     instance string [mscorlib]System.Int32::ToString()
0xc55  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc5a  ldloc.s  7
0xc5c  ldstr    aSkipauditparti_0// "skipAuditPartitionsToCompress"
0xc61  ldloca.s 0xA
0xc63  call     instance string [mscorlib]System.Int32::ToString()
0xc68  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc6d  ldloc.s  7
0xc6f  ldstr    aMaxauditindexe_0// "maxAuditIndexesToCompressOnOlderPartiti"...
0xc74  ldloca.s 0xB
0xc76  call     instance string [mscorlib]System.Int32::ToString()
0xc7b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc80  ldloc.s  7
0xc82  ldstr    aCompressauditc_0// "compressAuditClusteredIndexOnOlderParti"...
0xc87  ldloca.s 0xC
0xc89  call     instance string [mscorlib]System.Boolean::ToString()
0xc8e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc93  ldloc.s  7
0xc95  ldstr    aSqltext// "sqltext"
0xc9a  ldloc.3
0xc9b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xca0  ldloc.s  7
0xca2  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0xca7  ldloc.s  5
0xca9  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xcae  ldloc.s  5
0xcb0  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0xcb5  stloc.s  0x12
0xcb7  ldloca.s 0x12
0xcb9  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0xcbe  conv.i4
0xcbf  stloc.1
0xcc0  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Platform.AuditServiceEventSource [Microsoft.Crm.ObjectModel]Microsoft.Crm.Platform.AuditServiceEventSource::get_Instance()
0xcc5  ldarg.0
0xcc6  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::_config
0xccb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcd0  ldloc.s  6
0xcd2  ldloc.s  4
0xcd4  ldloc.1
0xcd5  ldloc.s  9
0xcd7  ldloc.s  0xA
0xcd9  ldloc.s  0xB
0xcdb  ldloc.s  0xC
0xcdd  ldloc.3
0xcde  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Platform.AuditServiceEventSource::AuditPartitionCompressInformation(valuetype [mscorlib]System.Guid, string, string, int32, int32, int32, int32, bool, string)
0xce3  leave    loc_DA7
0xce8  stloc.s  0x13
0xcea  ldstr    aErrorWhileComp// "Error while Compressing AuditBase table"...
0xcef  stloc.s  4
0xcf1  ldloc.s  7
0xcf3  ldstr    aMessage// "message"
0xcf8  ldloc.s  4
0xcfa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xcff  ldloc.s  7
0xd01  ldstr    aPartitioncompr// "PartitionCompressTimeout"
0xd06  ldloca.s 9
0xd08  call     instance string [mscorlib]System.Int32::ToString()
0xd0d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xd12  ldloc.s  7
0xd14  ldstr    aSkipauditparti_0// "skipAuditPartitionsToCompress"
0xd19  ldloca.s 0xA
0xd1b  call     instance string [mscorlib]System.Int32::ToString()
0xd20  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xd25  ldloc.s  7
0xd27  ldstr    aMaxauditindexe_0// "maxAuditIndexesToCompressOnOlderPartiti"...
0xd2c  ldloca.s 0xB
0xd2e  call     instance string [mscorlib]System.Int32::ToString()
0xd33  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xd38  ldloc.s  7
0xd3a  ldstr    aCompressauditc_0// "compressAuditClusteredIndexOnOlderParti"...
0xd3f  ldloca.s 0xC
0xd41  call     instance string [mscorlib]System.Boolean::ToString()
0xd46  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xd4b  ldloc.s  7
0xd4d  ldstr    aSqltext// "sqltext"
0xd52  ldloc.3
0xd53  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xd58  ldloc.s  7
0xd5a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0xd5f  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Platform.AuditServiceEventSource [Microsoft.Crm.ObjectModel]Microsoft.Crm.Platform.AuditServiceEventSource::get_Instance()
0xd64  ldarg.0
0xd65  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::_config
0xd6a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xd6f  ldloc.s  6
0xd71  ldloc.s  4
0xd73  ldloc.s  0x13
0xd75  callvirt instance string [mscorlib]System.Object::ToString()
0xd7a  call     string [mscorlib]System.Environment::get_StackTrace()
0xd7f  ldloc.1
0xd80  ldloc.s  9
0xd82  ldloc.s  0xA
0xd84  ldloc.s  0xB
0xd86  ldloc.s  0xC
0xd88  ldloc.3
0xd89  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Platform.AuditServiceEventSource::AuditPartitionCompressError(valuetype [mscorlib]System.Guid, string, string, string, string, int32, int32, int32, int32, bool, string)
0xd8e  ldloc.s  4
0xd90  ldstr    aError// " Error: "
0xd95  ldloc.s  0x13
0xd97  callvirt instance string [mscorlib]System.Object::ToString()
0xd9c  call     string [mscorlib]System.String::Concat(string, string, string)
0xda1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
  ... truncated ...
```
