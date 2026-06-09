# Microsoft.Crm.ServerLocatorService::UpsertProvisioningSubState

- ea: `0xb140`
- end: `0xb26e`
- name: `Microsoft.Crm.ServerLocatorService::UpsertProvisioningSubState`
- size: `302`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4640`
- `0x4c60`
- `0xb080`
- `0xb140`
- `0xb4f0`
- `0xbfa0`
- `0x1be90`
- `0x44400`
- `0x44510`
- `0x4d750`
- `0x61910`

## string_xrefs

- `0xb196`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xb256`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xb1f0`: `CreatedOn`

## pseudocode

```c

```

## disassembly

```asm
0xb140  ldarg.1
0xb141  ldstr    aOrganizationid_0// "organizationId"
0xb146  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xb14b  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xb150  stloc.0
0xb151  ldloc.0
0xb152  ldstr    aOrganizationid_1// "OrganizationId"
0xb157  ldarg.1
0xb158  box      [mscorlib]System.Guid
0xb15d  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb162  ldloc.0
0xb163  ldstr    aOrgapplication// "OrgApplicationType"
0xb168  ldarg.3
0xb169  box      [mscorlib]System.Int32
0xb16e  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb173  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0xb178  ldstr    aOrgapplication_0// "OrgApplicationMap"
0xb17d  ldc.i4.1
0xb17e  newarr   [mscorlib]System.String
0xb183  dup
0xb184  ldc.i4.0
0xb185  ldstr    aMobileofflineo// "MobileOfflineOrgApplicationStatus"
0xb18a  stelem.ref
0xb18b  ldloc.0
0xb18c  ldc.i4   0xB7D
0xb191  ldstr    aUpsertprovisio_0// "UpsertProvisioningSubState"
0xb196  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xb19b  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xb1a0  brfalse.s loc_B1AC
0xb1a2  ldarg.0
0xb1a3  ldarg.1
0xb1a4  ldarg.2
0xb1a5  ldarg.3
0xb1a6  call     instance void Microsoft.Crm.ServerLocatorService::UpdateProvisioningSubState(valuetype [mscorlib]System.Guid organizationId, int32 orgApplicationSubStatus, int32 orgApplicationType)
0xb1ab  ret
0xb1ac  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xb1b1  stloc.1
0xb1b2  ldloc.1
0xb1b3  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0xb1b8  ldloc.0
0xb1b9  ldstr    aId// "Id"
0xb1be  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xb1c3  box      [mscorlib]System.Guid
0xb1c8  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb1cd  ldloc.0
0xb1ce  ldstr    aOrgapplication_1// "OrgApplicationStatus"
0xb1d3  ldc.i4.0
0xb1d4  box      [mscorlib]System.Int32
0xb1d9  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb1de  ldloc.0
0xb1df  ldstr    aMobileofflineo// "MobileOfflineOrgApplicationStatus"
0xb1e4  ldarg.2
0xb1e5  box      [mscorlib]System.Int32
0xb1ea  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb1ef  ldloc.0
0xb1f0  ldstr    aCreatedon// "CreatedOn"
0xb1f5  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xb1fa  box      [mscorlib]System.DateTime
0xb1ff  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb204  ldloc.0
0xb205  ldstr    aModifiedon// "ModifiedOn"
0xb20a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xb20f  box      [mscorlib]System.DateTime
0xb214  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb219  ldloc.0
0xb21a  ldstr    aOrgstatusmodif// "OrgStatusModifiedOn"
0xb21f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xb224  box      [mscorlib]System.DateTime
0xb229  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb22e  ldloc.0
0xb22f  ldstr    aAzureresourceg// "AzureResourceGroupId"
0xb234  ldarg.0
0xb235  ldarg.3
0xb236  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServerLocatorService::GetAzureResourceGroupId(int32 orgType)
0xb23b  box      [mscorlib]System.Guid
0xb240  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb245  ldloc.1
0xb246  ldstr    aOrgapplication_0// "OrgApplicationMap"
0xb24b  ldloc.0
0xb24c  ldc.i4   0xB8E
0xb251  ldstr    aUpsertprovisio_0// "UpsertProvisioningSubState"
0xb256  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xb25b  callvirt instance object Microsoft.Crm.SharedDatabase.DatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xb260  pop
0xb261  leave.s  loc_B26D
0xb263  ldloc.1
0xb264  brfalse.s loc_B26C
0xb266  ldloc.1
0xb267  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb26c  endfinally
0xb26d  ret
```
