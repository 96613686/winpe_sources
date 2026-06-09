# Microsoft.Crm.ServerLocatorService::SetOrganizationReadCommittedSnapshotIsolation

- ea: `0x8f50`
- end: `0x8feb`
- name: `Microsoft.Crm.ServerLocatorService::SetOrganizationReadCommittedSnapshotIsolation`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8f50`
- `0xbfa0`
- `0x11620`
- `0x13de0`
- `0x14090`
- `0x1be90`
- `0x44400`
- `0x44510`
- `0x4d750`
- `0x62500`

## string_xrefs

- `0x8fb1`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x8f85`: `ReadCommittedSnapshotIsolationEnabled`
- `0x8fac`: `SetOrganizationReadCommittedSnapshotIsolation`

## pseudocode

```c

```

## disassembly

```asm
0x8f50  ldarg.1
0x8f51  ldstr    aOrganizationid_0// "organizationId"
0x8f56  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x8f5b  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x8f60  stloc.0
0x8f61  ldloc.0
0x8f62  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0x8f67  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x8f6c  stloc.1
0x8f6d  ldloc.1
0x8f6e  ldstr    aId// "Id"
0x8f73  ldarg.1
0x8f74  box      [mscorlib]System.Guid
0x8f79  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8f7e  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x8f83  stloc.2
0x8f84  ldloc.2
0x8f85  ldstr    aReadcommitteds// "ReadCommittedSnapshotIsolationEnabled"
0x8f8a  ldarg.2
0x8f8b  box      [mscorlib]System.Boolean
0x8f90  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8f95  ldloc.0
0x8f96  ldstr    aOrganization// "Organization"
0x8f9b  ldloc.2
0x8f9c  ldc.i4.1
0x8f9d  newarr   Microsoft.Crm.Data.PropertyBag
0x8fa2  dup
0x8fa3  ldc.i4.0
0x8fa4  ldloc.1
0x8fa5  stelem.ref
0x8fa6  ldc.i4.0
0x8fa7  ldc.i4   0x602
0x8fac  ldstr    aSetorganizatio_3// "SetOrganizationReadCommittedSnapshotIso"...
0x8fb1  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x8fb6  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Update(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, class Microsoft.Crm.Data.PropertyBag[] conditions, bool fireNotification, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x8fbb  pop
0x8fbc  ldc.i4.2
0x8fbd  ldarga.s 1
0x8fbf  ldstr    aB// "B"
0x8fc4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8fc9  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x8fce  ldarg.1
0x8fcf  newobj   instance void Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid organizationId)
0x8fd4  call     void Microsoft.Crm.NotificationManager::FireEvent(valuetype Microsoft.Crm.NotificationEventType eventType, string eventData, class Microsoft.Crm.IOrganizationContext context)
0x8fd9  call     void Microsoft.Crm.NotificationManager::Kick()
0x8fde  leave.s  loc_8FEA
0x8fe0  ldloc.0
0x8fe1  brfalse.s loc_8FE9
0x8fe3  ldloc.0
0x8fe4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8fe9  endfinally
0x8fea  ret
```
