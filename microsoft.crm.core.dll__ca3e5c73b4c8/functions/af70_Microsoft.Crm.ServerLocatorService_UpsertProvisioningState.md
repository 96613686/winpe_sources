# Microsoft.Crm.ServerLocatorService::UpsertProvisioningState

- ea: `0xaf70`
- end: `0xb078`
- name: `Microsoft.Crm.ServerLocatorService::UpsertProvisioningState`
- size: `264`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4640`
- `0x4c60`
- `0xaed0`
- `0xaf70`
- `0xb4f0`
- `0xbfa0`
- `0x1be90`
- `0x44400`
- `0x44510`
- `0x4d750`
- `0x61910`

## string_xrefs

- `0xafc6`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xb060`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xb00f`: `CreatedOn`

## pseudocode

```c

```

## disassembly

```asm
0xaf70  ldarg.1
0xaf71  ldstr    aOrganizationid_0// "organizationId"
0xaf76  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xaf7b  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xaf80  stloc.0
0xaf81  ldloc.0
0xaf82  ldstr    aOrganizationid_1// "OrganizationId"
0xaf87  ldarg.1
0xaf88  box      [mscorlib]System.Guid
0xaf8d  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xaf92  ldloc.0
0xaf93  ldstr    aOrgapplication// "OrgApplicationType"
0xaf98  ldarg.3
0xaf99  box      [mscorlib]System.Int32
0xaf9e  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xafa3  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0xafa8  ldstr    aOrgapplication_0// "OrgApplicationMap"
0xafad  ldc.i4.1
0xafae  newarr   [mscorlib]System.String
0xafb3  dup
0xafb4  ldc.i4.0
0xafb5  ldstr    aOrgapplication_1// "OrgApplicationStatus"
0xafba  stelem.ref
0xafbb  ldloc.0
0xafbc  ldc.i4   0xB3A
0xafc1  ldstr    aUpsertprovisio// "UpsertProvisioningState"
0xafc6  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xafcb  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xafd0  brfalse.s loc_AFDC
0xafd2  ldarg.0
0xafd3  ldarg.1
0xafd4  ldarg.2
0xafd5  ldarg.3
0xafd6  call     instance void Microsoft.Crm.ServerLocatorService::UpdateProvisioningState(valuetype [mscorlib]System.Guid organizationId, int32 orgApplicationStatus, int32 orgApplicationType)
0xafdb  ret
0xafdc  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xafe1  stloc.1
0xafe2  ldloc.1
0xafe3  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0xafe8  ldloc.0
0xafe9  ldstr    aId// "Id"
0xafee  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xaff3  box      [mscorlib]System.Guid
0xaff8  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xaffd  ldloc.0
0xaffe  ldstr    aOrgapplication_1// "OrgApplicationStatus"
0xb003  ldarg.2
0xb004  box      [mscorlib]System.Int32
0xb009  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb00e  ldloc.0
0xb00f  ldstr    aCreatedon// "CreatedOn"
0xb014  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xb019  box      [mscorlib]System.DateTime
0xb01e  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb023  ldloc.0
0xb024  ldstr    aModifiedon// "ModifiedOn"
0xb029  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xb02e  box      [mscorlib]System.DateTime
0xb033  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb038  ldloc.0
0xb039  ldstr    aAzureresourceg// "AzureResourceGroupId"
0xb03e  ldarg.0
0xb03f  ldarg.3
0xb040  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServerLocatorService::GetAzureResourceGroupId(int32 orgType)
0xb045  box      [mscorlib]System.Guid
0xb04a  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb04f  ldloc.1
0xb050  ldstr    aOrgapplication_0// "OrgApplicationMap"
0xb055  ldloc.0
0xb056  ldc.i4   0xB49
0xb05b  ldstr    aUpsertprovisio// "UpsertProvisioningState"
0xb060  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xb065  callvirt instance object Microsoft.Crm.SharedDatabase.DatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xb06a  pop
0xb06b  leave.s  loc_B077
0xb06d  ldloc.1
0xb06e  brfalse.s loc_B076
0xb070  ldloc.1
0xb071  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb076  endfinally
0xb077  ret
```
