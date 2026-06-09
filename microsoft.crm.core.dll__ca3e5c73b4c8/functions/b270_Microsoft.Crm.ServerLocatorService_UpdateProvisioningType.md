# Microsoft.Crm.ServerLocatorService::UpdateProvisioningType

- ea: `0xb270`
- end: `0xb2fa`
- name: `Microsoft.Crm.ServerLocatorService::UpdateProvisioningType`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0xb270`
- `0xbfa0`
- `0x1be90`
- `0x44400`
- `0x44510`
- `0x4d750`
- `0x62500`

## string_xrefs

- `0xb2e2`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xb2dd`: `UpdateProvisioningType`

## pseudocode

```c

```

## disassembly

```asm
0xb270  ldarg.1
0xb271  ldstr    aOrganizationid_0// "organizationId"
0xb276  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xb27b  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xb280  stloc.0
0xb281  ldloc.0
0xb282  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0xb287  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xb28c  stloc.1
0xb28d  ldloc.1
0xb28e  ldstr    aOrganizationid_1// "OrganizationId"
0xb293  ldarg.1
0xb294  box      [mscorlib]System.Guid
0xb299  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb29e  ldloc.1
0xb29f  ldstr    aOrgapplication// "OrgApplicationType"
0xb2a4  ldarg.2
0xb2a5  box      [mscorlib]System.Int32
0xb2aa  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb2af  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xb2b4  stloc.2
0xb2b5  ldloc.2
0xb2b6  ldstr    aOrgprovisionin// "OrgProvisioningType"
0xb2bb  ldarg.3
0xb2bc  box      [mscorlib]System.Int32
0xb2c1  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb2c6  ldloc.0
0xb2c7  ldstr    aOrgapplication_0// "OrgApplicationMap"
0xb2cc  ldloc.2
0xb2cd  ldc.i4.1
0xb2ce  newarr   Microsoft.Crm.Data.PropertyBag
0xb2d3  dup
0xb2d4  ldc.i4.0
0xb2d5  ldloc.1
0xb2d6  stelem.ref
0xb2d7  ldc.i4.1
0xb2d8  ldc.i4   0xBA8
0xb2dd  ldstr    aUpdateprovisio_1// "UpdateProvisioningType"
0xb2e2  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xb2e7  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Update(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, class Microsoft.Crm.Data.PropertyBag[] conditions, bool fireNotification, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xb2ec  pop
0xb2ed  leave.s  loc_B2F9
0xb2ef  ldloc.0
0xb2f0  brfalse.s loc_B2F8
0xb2f2  ldloc.0
0xb2f3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb2f8  endfinally
0xb2f9  ret
```
