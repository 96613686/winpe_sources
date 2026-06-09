# Microsoft.Crm.ServerLocatorService::UpdateProvisioningState

- ea: `0xaed0`
- end: `0xaf6f`
- name: `Microsoft.Crm.ServerLocatorService::UpdateProvisioningState`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xaf70`

## callees

- `0xaed0`
- `0xbfa0`
- `0x1be90`
- `0x44400`
- `0x44510`
- `0x4d750`
- `0x62500`

## string_xrefs

- `0xaf57`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xaf52`: `UpdateProvisioningState`

## pseudocode

```c

```

## disassembly

```asm
0xaed0  ldarg.1
0xaed1  ldstr    aOrganizationid_0// "organizationId"
0xaed6  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xaedb  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xaee0  stloc.0
0xaee1  ldloc.0
0xaee2  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0xaee7  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xaeec  stloc.1
0xaeed  ldloc.1
0xaeee  ldstr    aOrganizationid_1// "OrganizationId"
0xaef3  ldarg.1
0xaef4  box      [mscorlib]System.Guid
0xaef9  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xaefe  ldloc.1
0xaeff  ldstr    aOrgapplication// "OrgApplicationType"
0xaf04  ldarg.3
0xaf05  box      [mscorlib]System.Int32
0xaf0a  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xaf0f  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xaf14  stloc.2
0xaf15  ldloc.2
0xaf16  ldstr    aOrgapplication_1// "OrgApplicationStatus"
0xaf1b  ldarg.2
0xaf1c  box      [mscorlib]System.Int32
0xaf21  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xaf26  ldloc.2
0xaf27  ldstr    aModifiedon// "ModifiedOn"
0xaf2c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xaf31  box      [mscorlib]System.DateTime
0xaf36  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xaf3b  ldloc.0
0xaf3c  ldstr    aOrgapplication_0// "OrgApplicationMap"
0xaf41  ldloc.2
0xaf42  ldc.i4.1
0xaf43  newarr   Microsoft.Crm.Data.PropertyBag
0xaf48  dup
0xaf49  ldc.i4.0
0xaf4a  ldloc.1
0xaf4b  stelem.ref
0xaf4c  ldc.i4.1
0xaf4d  ldc.i4   0xB28
0xaf52  ldstr    aUpdateprovisio// "UpdateProvisioningState"
0xaf57  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xaf5c  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Update(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, class Microsoft.Crm.Data.PropertyBag[] conditions, bool fireNotification, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xaf61  pop
0xaf62  leave.s  loc_AF6E
0xaf64  ldloc.0
0xaf65  brfalse.s loc_AF6D
0xaf67  ldloc.0
0xaf68  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaf6d  endfinally
0xaf6e  ret
```
