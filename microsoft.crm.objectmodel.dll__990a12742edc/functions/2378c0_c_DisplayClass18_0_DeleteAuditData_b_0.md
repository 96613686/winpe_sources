# <>c__DisplayClass18_0::<DeleteAuditData>b__0

- ea: `0x2378c0`
- end: `0x237fcf`
- name: `<>c__DisplayClass18_0::<DeleteAuditData>b__0`
- size: `1807`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x19eb0`
- `0x1a010`
- `0x1a020`
- `0xc2e40`
- `0xc3220`
- `0xc3260`
- `0xc3380`
- `0xc65d0`
- `0xc6d90`
- `0x2378c0`

## string_xrefs

- `0x237c32`: `D:\a\1\s\src\Core\ObjectModel\Services\Audit\AuditService.cs`
- `0x237d4b`: `D:\a\1\s\src\Core\ObjectModel\Services\Audit\AuditService.cs`
- `0x237972`: `@createdOn`
- `0x237e7c`: `CommandText`
- `0x237efc`: `CommandText`
- `0x2378d6`: `prvDeleteAuditPartitions`
- `0x237908`: `AuditService: DeleteAuditData`
- `0x237963`: `CreatedOn <= @createdOn`
- `0x2379b6`: `SQL doesn't support partitioning, deleted all the rows from AuditBase that fall before `
- `0x237a32`: `Error in retrieving partition list. There are no partitions to delete.`
- `0x237b84`: `You cannot delete audit data in the partitions that are currently in use, or delete the partitions that are created for storing future audit data `
- `0x237bda`: `You cannot delete audit data in the partitions that are currently in use, or delete the partitions that are created for storing future audit data.`
- `0x237c1c`: `select count(1) as NewMaxdopParameterCount from sys.objects as o inner join sys.parameters as p on o.object_id = p.object_id \nwhere o.object_id in (select object_id from sys.objects where type = 'P' and object_id = object_id('p_DeleteSingleAuditPartition')) and p.name in ('@maxdop');`
- `0x237c2d`: `DeleteAuditData`
- `0x237d46`: `DeleteAuditData`
- `0x237cae`: `p_DeleteSingleAuditPartition`
- `0x237d7c`: `Cannot delete current partition `
- `0x237dd7`: ` is not the oldest AuditBase partition. Please select oldest AuditBase partition to delete. Exiting...`
- `0x237df3`: `Successfully deleted partition with input date `
- `0x237e10`: `Successfully deleted partition with input date {0}. No ReturnValue from stored procedure p_DeleteSingleAuditPartition`
- `0x237e29`: `Unknown ReturnValue: {0} from {1}. Unable to delete partition on specified date {2}.`
- `0x237ed4`: `Failed to delete audit data from the specified range `

## pseudocode

```c

```

## disassembly

```asm
0x2378c0  ldarg.0
0x2378c1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass18_0::context
0x2378c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x2378cb  ldarg.0
0x2378cc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass18_0::context
0x2378d1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2378d6  ldstr    aPrvdeleteaudit// "prvDeleteAuditPartitions"
0x2378db  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0x2378e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x2378e5  ldarg.0
0x2378e6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass18_0::context
0x2378eb  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2378f0  ldsfld   string [mscorlib]System.String::Empty
0x2378f5  stloc.0
0x2378f6  ldc.i4.m1
0x2378f7  stloc.1
0x2378f8  ldc.i4.m1
0x2378f9  stloc.2
0x2378fa  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x2378ff  stloc.s  5
0x237901  ldloc.s  5
0x237903  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x237908  ldstr    aAuditserviceDe_1// "AuditService: DeleteAuditData"
0x23790d  stloc.s  6
0x23790f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x237914  stloc.s  7
0x237916  ldloc.s  7
0x237918  ldstr    aModulename// "moduleName"
0x23791d  ldloc.s  6
0x23791f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x237924  ldarg.0
0x237925  ldfld    class Microsoft.Crm.ObjectModel.AuditService <>c__DisplayClass18_0::<>4__this
0x23792a  ldarg.0
0x23792b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime <>c__DisplayClass18_0::endDate
0x237930  ldarg.0
0x237931  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass18_0::context
0x237936  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.ObjectModel.AuditService::GetDateTimeFromCrmDateTime(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime crmDateTime, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x23793b  stloc.s  8
0x23793d  ldarg.0
0x23793e  ldfld    class Microsoft.Crm.ObjectModel.AuditService <>c__DisplayClass18_0::<>4__this
0x237943  ldarg.0
0x237944  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass18_0::context
0x237949  ldc.i4.6
0x23794a  ldnull
0x23794b  ldloca.s 4
0x23794d  call     instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AuditPartitionDetailCollection Microsoft.Crm.ObjectModel.AuditService::RetrieveAuditPartitionListInternal(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype EventNames eventType, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken timer, [out] class [mscorlib]System.Collections.ArrayList& endTimes)
0x237952  dup
0x237953  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AuditPartitionDetail>::get_Count()
0x237958  stloc.3
0x237959  callvirt instance bool [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AuditPartitionDetailCollection::get_IsLogicalCollection()
0x23795e  brfalse  loc_237A15
0x237963  ldstr    aCreatedonCreat// "CreatedOn <= @createdOn"
0x237968  stloc.s  0xD
0x23796a  ldc.i4.1
0x23796b  newarr   [System.Data]System.Data.SqlClient.SqlParameter
0x237970  dup
0x237971  ldc.i4.0
0x237972  ldstr    aCreatedon_1// "@createdOn"
0x237977  ldloc.s  8
0x237979  box      [mscorlib]System.DateTime
0x23797e  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x237983  stelem.ref
0x237984  stloc.s  0xE
0x237986  ldarg.0
0x237987  ldfld    class Microsoft.Crm.ObjectModel.AuditService <>c__DisplayClass18_0::<>4__this
0x23798c  ldloc.s  0xD
0x23798e  ldloc.s  0xE
0x237990  ldarg.0
0x237991  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass18_0::context
0x237996  call     instance int32 Microsoft.Crm.ObjectModel.AuditService::DeleteRowsWiseAuditTable(string conditionText, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Data]System.Data.SqlClient.SqlParameter> conditionParameters, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x23799b  stloc.s  0xF
0x23799d  ldloc.s  5
0x23799f  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x2379a4  ldloc.s  5
0x2379a6  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x2379ab  stloc.s  0x10
0x2379ad  ldloca.s 0x10
0x2379af  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x2379b4  conv.i4
0x2379b5  stloc.2
0x2379b6  ldstr    aSqlDoesnTSuppo// "SQL doesn't support partitioning, delet"...
0x2379bb  ldloca.s 8
0x2379bd  ldstr    aMmDdYyyyHhMmSs// "MM/dd/yyyy HH:mm:ss.fff"
0x2379c2  call     instance string [mscorlib]System.DateTime::ToString(string)
0x2379c7  call     string [mscorlib]System.String::Concat(string, string)
0x2379cc  stloc.0
0x2379cd  ldloc.s  7
0x2379cf  ldstr    aMessage_0// "message"
0x2379d4  ldloc.0
0x2379d5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x2379da  ldloc.s  7
0x2379dc  ldstr    aRowsaffected// "rowsAffected"
0x2379e1  ldloca.s 0xF
0x2379e3  call     instance string [mscorlib]System.Int32::ToString()
0x2379e8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x2379ed  ldloc.s  7
0x2379ef  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x2379f4  call     class Microsoft.Crm.Platform.AuditServiceEventSource Microsoft.Crm.Platform.AuditServiceEventSource::get_Instance()
0x2379f9  ldarg.0
0x2379fa  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass18_0::context
0x2379ff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x237a04  ldloc.s  6
0x237a06  ldloc.0
0x237a07  ldloc.2
0x237a08  ldsfld   string [mscorlib]System.String::Empty
0x237a0d  callvirt instance void Microsoft.Crm.Platform.AuditServiceEventSource::AuditPartitionDeleteInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 durationInSecs, string sqlcommandText)
0x237a12  ldloc.s  0xF
0x237a14  ret
0x237a15  ldloc.s  5
0x237a17  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x237a1c  ldloc.s  5
0x237a1e  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x237a23  stloc.s  0x10
0x237a25  ldloca.s 0x10
0x237a27  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x237a2c  conv.i4
0x237a2d  stloc.2
0x237a2e  ldloc.3
0x237a2f  ldc.i4.3
0x237a30  bge.s    loc_237A82
0x237a32  ldstr    aErrorInRetriev_5// "Error in retrieving partition list. The"...
0x237a37  stloc.s  0x11
0x237a39  ldloc.s  7
0x237a3b  ldstr    aCrmtracemessag// "crmTraceMessage"
0x237a40  ldloc.s  0x11
0x237a42  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x237a47  ldloc.s  7
0x237a49  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x237a4e  call     class Microsoft.Crm.Platform.AuditServiceEventSource Microsoft.Crm.Platform.AuditServiceEventSource::get_Instance()
0x237a53  ldarg.0
0x237a54  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass18_0::context
0x237a59  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x237a5e  ldloc.s  6
0x237a60  ldloc.s  0x11
0x237a62  ldsfld   string [mscorlib]System.String::Empty
0x237a67  call     string [mscorlib]System.Environment::get_StackTrace()
0x237a6c  ldloc.2
0x237a6d  ldsfld   string [mscorlib]System.String::Empty
0x237a72  callvirt instance void Microsoft.Crm.Platform.AuditServiceEventSource::AuditPartitionDeleteError(valuetype [mscorlib]System.Guid organizationId, string moduleName, string crmTraceMessage, string errorMessage, string stackTrace, int32 durationInSecs, string sqlcommandText)
0x237a77  ldstr    aErrorInRetriev_6// "Error in retrieving partition list"
0x237a7c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x237a81  throw
0x237a82  ldc.i4.0
0x237a83  stloc.s  0x12
0x237a85  br.s     loc_237AE8
0x237a87  ldloc.s  4
0x237a89  ldloc.s  0x12
0x237a8b  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x237a90  brtrue.s loc_237AE2
0x237a92  ldstr    aErrorInRetriev_7// "Error in retrieving partition list. The"...
0x237a97  stloc.s  0x13
0x237a99  ldloc.s  7
0x237a9b  ldstr    aCrmtracemessag// "crmTraceMessage"
0x237aa0  ldloc.s  0x13
0x237aa2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x237aa7  ldloc.s  7
0x237aa9  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x237aae  call     class Microsoft.Crm.Platform.AuditServiceEventSource Microsoft.Crm.Platform.AuditServiceEventSource::get_Instance()
0x237ab3  ldarg.0
0x237ab4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass18_0::context
0x237ab9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x237abe  ldloc.s  6
0x237ac0  ldloc.s  0x13
0x237ac2  ldsfld   string [mscorlib]System.String::Empty
0x237ac7  call     string [mscorlib]System.Environment::get_StackTrace()
0x237acc  ldloc.2
0x237acd  ldsfld   string [mscorlib]System.String::Empty
0x237ad2  callvirt instance void Microsoft.Crm.Platform.AuditServiceEventSource::AuditPartitionDeleteError(valuetype [mscorlib]System.Guid organizationId, string moduleName, string crmTraceMessage, string errorMessage, string stackTrace, int32 durationInSecs, string sqlcommandText)
0x237ad7  ldstr    aErrorInRetriev_6// "Error in retrieving partition list"
0x237adc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x237ae1  throw
0x237ae2  ldloc.s  0x12
0x237ae4  ldc.i4.1
0x237ae5  add
0x237ae6  stloc.s  0x12
0x237ae8  ldloc.s  0x12
0x237aea  ldloc.3
0x237aeb  ldc.i4.1
0x237aec  sub
0x237aed  blt.s    loc_237A87
0x237aef  ldloc.s  8
0x237af1  ldarg.0
0x237af2  ldfld    class Microsoft.Crm.ObjectModel.AuditService <>c__DisplayClass18_0::<>4__this
0x237af7  ldloc.s  4
0x237af9  ldc.i4.0
0x237afa  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x237aff  unbox.any [mscorlib]System.DateTime
0x237b04  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.ObjectModel.AuditService::GetTruncatedUtc(valuetype [mscorlib]System.DateTime dateTime)
0x237b09  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x237b0e  brfalse.s loc_237B76
0x237b10  ldstr    aThereAreNoPart// "There are no partitions ending before t"...
0x237b15  ldloca.s 8
0x237b17  ldstr    aMmDdYyyyHhMmSs// "MM/dd/yyyy HH:mm:ss.fff"
0x237b1c  call     instance string [mscorlib]System.DateTime::ToString(string)
0x237b21  call     string [mscorlib]System.String::Concat(string, string)
0x237b26  stloc.s  0x14
0x237b28  ldloc.s  7
0x237b2a  ldstr    aCrmtracemessag// "crmTraceMessage"
0x237b2f  ldloc.s  0x14
0x237b31  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x237b36  ldloc.s  7
0x237b38  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x237b3d  call     class Microsoft.Crm.Platform.AuditServiceEventSource Microsoft.Crm.Platform.AuditServiceEventSource::get_Instance()
0x237b42  ldarg.0
0x237b43  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass18_0::context
0x237b48  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x237b4d  ldloc.s  6
0x237b4f  ldloc.s  0x14
0x237b51  ldsfld   string [mscorlib]System.String::Empty
0x237b56  call     string [mscorlib]System.Environment::get_StackTrace()
0x237b5b  ldloc.2
0x237b5c  ldsfld   string [mscorlib]System.String::Empty
0x237b61  callvirt instance void Microsoft.Crm.Platform.AuditServiceEventSource::AuditPartitionDeleteError(valuetype [mscorlib]System.Guid organizationId, string moduleName, string crmTraceMessage, string errorMessage, string stackTrace, int32 durationInSecs, string sqlcommandText)
0x237b66  ldstr    aThereAreNoPart_0// "There are no partitions ending before t"...
0x237b6b  ldstr    aEnddate// "endDate"
0x237b70  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x237b75  throw
0x237b76  ldloc.s  8
0x237b78  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x237b7d  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x237b82  brfalse.s loc_237BEF
0x237b84  ldstr    aYouCannotDelet// "You cannot delete audit data in the par"...
0x237b89  ldloca.s 8
0x237b8b  ldstr    aMmDdYyyyHhMmSs// "MM/dd/yyyy HH:mm:ss.fff"
0x237b90  call     instance string [mscorlib]System.DateTime::ToString(string)
0x237b95  call     string [mscorlib]System.String::Concat(string, string)
0x237b9a  stloc.s  0x15
0x237b9c  ldloc.s  7
0x237b9e  ldstr    aCrmtracemessag// "crmTraceMessage"
0x237ba3  ldloc.s  0x15
0x237ba5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x237baa  ldloc.s  7
0x237bac  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x237bb1  call     class Microsoft.Crm.Platform.AuditServiceEventSource Microsoft.Crm.Platform.AuditServiceEventSource::get_Instance()
0x237bb6  ldarg.0
0x237bb7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass18_0::context
0x237bbc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x237bc1  ldloc.s  6
0x237bc3  ldloc.s  0x15
0x237bc5  ldsfld   string [mscorlib]System.String::Empty
0x237bca  call     string [mscorlib]System.Environment::get_StackTrace()
0x237bcf  ldloc.2
0x237bd0  ldsfld   string [mscorlib]System.String::Empty
0x237bd5  callvirt instance void Microsoft.Crm.Platform.AuditServiceEventSource::AuditPartitionDeleteError(valuetype [mscorlib]System.Guid organizationId, string moduleName, string crmTraceMessage, string errorMessage, string stackTrace, int32 durationInSecs, string sqlcommandText)
0x237bda  ldstr    aYouCannotDelet_0// "You cannot delete audit data in the par"...
0x237bdf  ldstr    aEnddate// "endDate"
0x237be4  ldc.i4   0x8004E200
0x237be9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string, int32)
0x237bee  throw
0x237bef  ldc.i4.0
0x237bf0  stloc.s  9
0x237bf2  ldarg.0
0x237bf3  ldfld    class Microsoft.Crm.ObjectModel.AuditService <>c__DisplayClass18_0::<>4__this
0x237bf8  ldarg.0
0x237bf9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass18_0::context
0x237bfe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x237c03  call     instance int32 Microsoft.Crm.ObjectModel.AuditService::GetMaxDopValueForAuditPartition(valuetype [mscorlib]System.Guid orgId)
0x237c08  stloc.s  0xA
0x237c0a  ldc.i4.0
0x237c0b  stloc.s  0xB
0x237c0d  ldarg.0
0x237c0e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass18_0::context
0x237c13  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x237c18  stloc.s  0x16
0x237c1a  ldloc.s  0x16
0x237c1c  ldstr    aSelectCount1As// "select count(1) as NewMaxdopParameterCo"...
0x237c21  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x237c26  ldloc.s  0x16
0x237c28  ldc.i4   0x363
0x237c2d  ldstr    aDeleteauditdat// "DeleteAuditData"
0x237c32  ldstr    aDA1SSrcCoreObj_17// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0x237c37  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x237c3c  stloc.s  0x17
0x237c3e  ldloc.s  0x17
0x237c40  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x237c45  brfalse.s loc_237C5E
0x237c47  ldloc.s  0x17
0x237c49  ldstr    aNewmaxdopparam// "NewMaxdopParameterCount"
0x237c4e  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x237c53  unbox.any [mscorlib]System.Int32
0x237c58  ldc.i4.1
0x237c59  bne.un.s loc_237C5E
0x237c5b  ldc.i4.1
0x237c5c  stloc.s  0xB
0x237c5e  leave.s  loc_237C78
0x237c60  ldloc.s  0x17
0x237c62  brfalse.s loc_237C6B
0x237c64  ldloc.s  0x17
0x237c66  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x237c6b  endfinally
0x237c6c  ldloc.s  0x16
0x237c6e  brfalse.s loc_237C77
0x237c70  ldloc.s  0x16
0x237c72  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x237c77  endfinally
0x237c78  ldc.i4.0
0x237c79  stloc.s  0x18
0x237c7b  br       loc_237F6C
0x237c80  ldloc.s  5
0x237c82  callvirt instance void [System]System.Diagnostics.Stopwatch::Restart()
  ... truncated ...
```
