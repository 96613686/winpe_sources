# Microsoft.Crm.ServerLocatorService::UpsertProvisioningStateAndGroupId

- ea: `0xb3d0`
- end: `0xb4ea`
- name: `Microsoft.Crm.ServerLocatorService::UpsertProvisioningStateAndGroupId`
- size: `282`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4640`
- `0x4c60`
- `0xb300`
- `0xb3d0`
- `0xbfa0`
- `0x1be90`
- `0x44400`
- `0x44510`
- `0x4d750`
- `0x61910`

## string_xrefs

- `0xb432`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xb4d2`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xb486`: `CreatedOn`

## pseudocode

```c

```

## disassembly

```asm
0xb3d0  ldarg.1
0xb3d1  ldstr    aOrganizationid_0// "organizationId"
0xb3d6  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xb3db  ldarg.s  4
0xb3dd  ldstr    aAzureresourceg_0// "azureResourceGroupId"
0xb3e2  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xb3e7  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xb3ec  stloc.0
0xb3ed  ldloc.0
0xb3ee  ldstr    aOrganizationid_1// "OrganizationId"
0xb3f3  ldarg.1
0xb3f4  box      [mscorlib]System.Guid
0xb3f9  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb3fe  ldloc.0
0xb3ff  ldstr    aOrgapplication// "OrgApplicationType"
0xb404  ldarg.3
0xb405  box      [mscorlib]System.Int32
0xb40a  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb40f  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0xb414  ldstr    aOrgapplication_0// "OrgApplicationMap"
0xb419  ldc.i4.1
0xb41a  newarr   [mscorlib]System.String
0xb41f  dup
0xb420  ldc.i4.0
0xb421  ldstr    aOrgapplication_1// "OrgApplicationStatus"
0xb426  stelem.ref
0xb427  ldloc.0
0xb428  ldc.i4   0xBDA
0xb42d  ldstr    aUpsertprovisio_1// "UpsertProvisioningStateAndGroupId"
0xb432  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xb437  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xb43c  brfalse.s loc_B453
0xb43e  ldarg.0
0xb43f  ldarg.1
0xb440  ldarg.2
0xb441  ldloca.s 1
0xb443  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xb449  ldloc.1
0xb44a  ldarg.3
0xb44b  ldarg.s  4
0xb44d  call     instance void Microsoft.Crm.ServerLocatorService::UpdateProvisioningStateAndGroupId(valuetype [mscorlib]System.Guid organizationId, int32 orgApplicationStatus, valuetype [mscorlib]System.Nullable`1<int32> orgApplicationSubStatus, int32 orgApplicationType, valuetype [mscorlib]System.Guid azureResourceGroupId)
0xb452  ret
0xb453  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xb458  stloc.2
0xb459  ldloc.2
0xb45a  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0xb45f  ldloc.0
0xb460  ldstr    aId// "Id"
0xb465  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xb46a  box      [mscorlib]System.Guid
0xb46f  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb474  ldloc.0
0xb475  ldstr    aOrgapplication_1// "OrgApplicationStatus"
0xb47a  ldarg.2
0xb47b  box      [mscorlib]System.Int32
0xb480  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb485  ldloc.0
0xb486  ldstr    aCreatedon// "CreatedOn"
0xb48b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xb490  box      [mscorlib]System.DateTime
0xb495  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb49a  ldloc.0
0xb49b  ldstr    aModifiedon// "ModifiedOn"
0xb4a0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xb4a5  box      [mscorlib]System.DateTime
0xb4aa  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb4af  ldloc.0
0xb4b0  ldstr    aAzureresourceg// "AzureResourceGroupId"
0xb4b5  ldarg.s  4
0xb4b7  box      [mscorlib]System.Guid
0xb4bc  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb4c1  ldloc.2
0xb4c2  ldstr    aOrgapplication_0// "OrgApplicationMap"
0xb4c7  ldloc.0
0xb4c8  ldc.i4   0xBE9
0xb4cd  ldstr    aUpsertprovisio_1// "UpsertProvisioningStateAndGroupId"
0xb4d2  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xb4d7  callvirt instance object Microsoft.Crm.SharedDatabase.DatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xb4dc  pop
0xb4dd  leave.s  loc_B4E9
0xb4df  ldloc.2
0xb4e0  brfalse.s loc_B4E8
0xb4e2  ldloc.2
0xb4e3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb4e8  endfinally
0xb4e9  ret
```
