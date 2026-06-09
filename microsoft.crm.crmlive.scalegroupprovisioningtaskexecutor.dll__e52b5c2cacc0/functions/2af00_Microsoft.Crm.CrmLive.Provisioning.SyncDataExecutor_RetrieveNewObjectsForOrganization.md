# Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::RetrieveNewObjectsForOrganization

- ea: `0x2af00`
- end: `0x2b04e`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::RetrieveNewObjectsForOrganization`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1110`
- `0x11a0`
- `0xe910`
- `0xe950`
- `0x2af00`
- `0x2b050`

## string_xrefs

- `0x2afb0`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\SyncDataExecutor.cs`
- `0x2af1c`: `_objectRevisionUpdater`
- `0x2af6e`: `Attempting retrieve objects for revision > {0}, batch size {1}`

## pseudocode

```c

```

## disassembly

```asm
0x2af00  ldarg.1
0x2af01  ldstr    aOrganizationid// "organizationId"
0x2af06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2af0b  ldarg.2
0x2af0c  ldstr    aBatchSizeMustB// "Batch size must be positive"
0x2af11  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNotPositive(int32, string)
0x2af16  ldarg.0
0x2af17  ldfld    class Microsoft.Crm.CrmLive.Provisioning.OrganizationObjectRevisionUpdater Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_objectRevisionUpdater
0x2af1c  ldstr    aObjectrevision// "_objectRevisionUpdater"
0x2af21  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2af26  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::.ctor()
0x2af2b  stloc.0
0x2af2c  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2af31  stloc.1
0x2af32  ldarg.0
0x2af33  ldfld    class Microsoft.Crm.CrmLive.Provisioning.OrganizationObjectRevisionUpdater Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_objectRevisionUpdater
0x2af38  callvirt instance int64 Microsoft.Crm.CrmLive.Provisioning.OrganizationObjectRevisionUpdater::RetrieveOrganizationRevision()
0x2af3d  stloc.2
0x2af3e  ldarg.0
0x2af3f  ldfld    class Microsoft.Crm.CrmLive.Provisioning.OrganizationObjectRevisionUpdater Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_objectRevisionUpdater
0x2af44  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.CrmLive.Provisioning.OrganizationObjectRevisionUpdater::get_ContextId()
0x2af49  stloc.s  7
0x2af4b  ldloca.s 7
0x2af4d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x2af52  stloc.3
0x2af53  ldarg.0
0x2af54  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncDataBehavior Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_syncDataBehavior
0x2af59  ldarg.2
0x2af5a  ldloc.3
0x2af5b  ldloc.2
0x2af5c  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::GetObjectQueryBySyncDataBehavior(class Microsoft.Crm.CrmLive.Provisioning.SyncDataBehavior behavior, int32 batchSize, valuetype [mscorlib]System.Guid contextId, int64 startRevision)
0x2af61  stloc.s  4
0x2af63  ldarg.0
0x2af64  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_syncDataLog
0x2af69  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2af6e  ldstr    aAttemptingRetr// "Attempting retrieve objects for revisio"...
0x2af73  ldc.i4.2
0x2af74  newarr   [mscorlib]System.Object
0x2af79  dup
0x2af7a  ldc.i4.0
0x2af7b  ldloc.2
0x2af7c  box      [mscorlib]System.Int64
0x2af81  stelem.ref
0x2af82  dup
0x2af83  ldc.i4.1
0x2af84  ldarg.2
0x2af85  box      [mscorlib]System.Int32
0x2af8a  stelem.ref
0x2af8b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2af90  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2af95  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x2af9a  stloc.s  5
0x2af9c  ldloc.s  5
0x2af9e  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x2afa3  ldloc.1
0x2afa4  ldloc.s  4
0x2afa6  ldc.i4   0x37C
0x2afab  ldstr    aRetrievenewobj// "RetrieveNewObjectsForOrganization"
0x2afb0  ldstr    aDDbsShDccm2110_42// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2afb5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.OrderedPropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery, int32, string, string)
0x2afba  stloc.s  6
0x2afbc  ldloc.s  5
0x2afbe  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x2afc3  ldarg.0
0x2afc4  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_syncDataLog
0x2afc9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2afce  ldstr    aQueryExecution// "Query execution time : {0}"
0x2afd3  ldc.i4.1
0x2afd4  newarr   [mscorlib]System.Object
0x2afd9  dup
0x2afda  ldc.i4.0
0x2afdb  ldloc.s  5
0x2afdd  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x2afe2  box      [mscorlib]System.TimeSpan
0x2afe7  stelem.ref
0x2afe8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2afed  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2aff2  call     class Microsoft.Crm.CrmLive.Telemetry.SyncDataEventSource Microsoft.Crm.CrmLive.Telemetry.SyncDataEventSource::get_Instance()
0x2aff7  ldarg.0
0x2aff8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_orgId
0x2affd  ldloc.2
0x2affe  ldarg.2
0x2afff  ldloc.s  5
0x2b001  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x2b006  callvirt instance void Microsoft.Crm.CrmLive.Telemetry.SyncDataEventSource::SyncDataRetrieveNewObjectsForOrg(valuetype [mscorlib]System.Guid organizationId, int64 revision, int32 batchSize, int64 elapsedMilliseconds)
0x2b00b  ldloc.0
0x2b00c  ldloc.s  6
0x2b00e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> [Microsoft.Crm.Core]Microsoft.Crm.Data.OrderedPropertyBagCollection::RetrievePropertyBags()
0x2b013  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x2b018  ldloc.0
0x2b019  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, object> <>c::<>9__32_0
0x2b01e  dup
0x2b01f  brtrue.s loc_2B038
0x2b021  pop
0x2b022  ldsfld   class <>c <>c::<>9
0x2b027  ldftn    instance object <>c::<RetrieveNewObjectsForOrganization>b__32_0(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag record)
0x2b02d  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, object>::.ctor(object, native int)
0x2b032  dup
0x2b033  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, object> <>c::<>9__32_0
0x2b038  call     T0x2B0000C8
0x2b03d  stloc.s  8
0x2b03f  leave.s  loc_2B04B
0x2b041  ldloc.1
0x2b042  brfalse.s loc_2B04A
0x2b044  ldloc.1
0x2b045  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b04a  endfinally
0x2b04b  ldloc.s  8
0x2b04d  ret
```
