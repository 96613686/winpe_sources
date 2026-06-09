# Microsoft.Crm.ServerLocatorService::UpdateProvisioningStateAndGroupId

- ea: `0xb300`
- end: `0xb3cf`
- name: `Microsoft.Crm.ServerLocatorService::UpdateProvisioningStateAndGroupId`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xb3d0`

## callees

- `0xb300`
- `0xbfa0`
- `0x1be90`
- `0x44400`
- `0x44510`
- `0x4d750`
- `0x62500`

## string_xrefs

- `0xb3b7`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xb3b2`: `UpdateProvisioningStateAndGroupId`

## pseudocode

```c

```

## disassembly

```asm
0xb300  ldarg.1
0xb301  ldstr    aOrganizationid_0// "organizationId"
0xb306  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xb30b  ldarg.s  5
0xb30d  ldstr    aAzureresourceg_0// "azureResourceGroupId"
0xb312  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xb317  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xb31c  stloc.0
0xb31d  ldloc.0
0xb31e  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0xb323  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xb328  stloc.1
0xb329  ldloc.1
0xb32a  ldstr    aOrganizationid_1// "OrganizationId"
0xb32f  ldarg.1
0xb330  box      [mscorlib]System.Guid
0xb335  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb33a  ldloc.1
0xb33b  ldstr    aOrgapplication// "OrgApplicationType"
0xb340  ldarg.s  4
0xb342  box      [mscorlib]System.Int32
0xb347  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb34c  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xb351  stloc.2
0xb352  ldloc.2
0xb353  ldstr    aOrgapplication_1// "OrgApplicationStatus"
0xb358  ldarg.2
0xb359  box      [mscorlib]System.Int32
0xb35e  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb363  ldloc.2
0xb364  ldstr    aMobileofflineo// "MobileOfflineOrgApplicationStatus"
0xb369  ldarg.3
0xb36a  box      valuetype [mscorlib]System.Nullable`1<int32>
0xb36f  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb374  ldloc.2
0xb375  ldstr    aAzureresourceg// "AzureResourceGroupId"
0xb37a  ldarg.s  5
0xb37c  box      [mscorlib]System.Guid
0xb381  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb386  ldloc.2
0xb387  ldstr    aModifiedon// "ModifiedOn"
0xb38c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xb391  box      [mscorlib]System.DateTime
0xb396  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb39b  ldloc.0
0xb39c  ldstr    aOrgapplication_0// "OrgApplicationMap"
0xb3a1  ldloc.2
0xb3a2  ldc.i4.1
0xb3a3  newarr   Microsoft.Crm.Data.PropertyBag
0xb3a8  dup
0xb3a9  ldc.i4.0
0xb3aa  ldloc.1
0xb3ab  stelem.ref
0xb3ac  ldc.i4.1
0xb3ad  ldc.i4   0xBC7
0xb3b2  ldstr    aUpdateprovisio_2// "UpdateProvisioningStateAndGroupId"
0xb3b7  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xb3bc  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Update(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, class Microsoft.Crm.Data.PropertyBag[] conditions, bool fireNotification, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xb3c1  pop
0xb3c2  leave.s  loc_B3CE
0xb3c4  ldloc.0
0xb3c5  brfalse.s loc_B3CD
0xb3c7  ldloc.0
0xb3c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb3cd  endfinally
0xb3ce  ret
```
