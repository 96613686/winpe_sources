# Microsoft.Crm.ConfigurationDatabase.OrganizationDatabaseService::RetrieveOrganizationDatabaseData

- ea: `0x4ea90`
- end: `0x4eb95`
- name: `Microsoft.Crm.ConfigurationDatabase.OrganizationDatabaseService::RetrieveOrganizationDatabaseData`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4c00`
- `0x444f0`
- `0x4e9f0`
- `0x4ea00`
- `0x4ea10`
- `0x4ea30`
- `0x4ea50`
- `0x4ea60`
- `0x4ea90`

## string_xrefs

- `0x4eac6`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\OrganizationDatabaseService.cs`
- `0x4eb6f`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\OrganizationDatabaseService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x4ea90  ldarg.0
0x4ea91  ldfld    class Microsoft.Crm.LocatorService Microsoft.Crm.ConfigurationDatabase.OrganizationDatabaseService::_locatorService
0x4ea96  ldstr    aOrganization// "Organization"
0x4ea9b  ldarg.1
0x4ea9c  box      [mscorlib]System.Guid
0x4eaa1  ldc.i4.3
0x4eaa2  newarr   [mscorlib]System.String
0x4eaa7  dup
0x4eaa8  ldc.i4.0
0x4eaa9  ldstr    aScalegroupid_0// "ScaleGroupId"
0x4eaae  stelem.ref
0x4eaaf  dup
0x4eab0  ldc.i4.1
0x4eab1  ldstr    aConnectionstri_0// "ConnectionString"
0x4eab6  stelem.ref
0x4eab7  dup
0x4eab8  ldc.i4.2
0x4eab9  ldstr    aState// "State"
0x4eabe  stelem.ref
0x4eabf  ldc.i4.s 0x17
0x4eac1  ldstr    aRetrieveorgani_0// "RetrieveOrganizationDatabaseData"
0x4eac6  ldstr    aDA1SSrcPlatfor_39// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4eacb  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4ead0  stloc.0
0x4ead1  ldloc.0
0x4ead2  brtrue.s loc_4EAD6
0x4ead4  ldnull
0x4ead5  ret
0x4ead6  newobj   instance void Microsoft.Crm.ConfigurationDatabase.OrganizationDatabaseData::.ctor()
0x4eadb  stloc.1
0x4eadc  ldloc.1
0x4eadd  ldloc.0
0x4eade  ldstr    aConnectionstri_0// "ConnectionString"
0x4eae3  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4eae8  castclass [mscorlib]System.String
0x4eaed  callvirt instance void Microsoft.Crm.ConfigurationDatabase.OrganizationDatabaseData::set_ConnectionString(string value)
0x4eaf2  ldloc.1
0x4eaf3  ldloc.0
0x4eaf4  ldstr    aScalegroupid_0// "ScaleGroupId"
0x4eaf9  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4eafe  brfalse.s loc_4EB12
0x4eb00  ldloc.0
0x4eb01  ldstr    aScalegroupid_0// "ScaleGroupId"
0x4eb06  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4eb0b  unbox.any [mscorlib]System.Guid
0x4eb10  br.s     loc_4EB17
0x4eb12  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4eb17  callvirt instance void Microsoft.Crm.ConfigurationDatabase.OrganizationDatabaseData::set_ScaleGroupId(valuetype [mscorlib]System.Guid value)
0x4eb1c  ldloc.1
0x4eb1d  ldloc.0
0x4eb1e  ldstr    aState// "State"
0x4eb23  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4eb28  unbox.any [mscorlib]System.Int32
0x4eb2d  callvirt instance void Microsoft.Crm.ConfigurationDatabase.OrganizationDatabaseData::set_State(valuetype Microsoft.Crm.OrganizationState value)
0x4eb32  ldloc.1
0x4eb33  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ConfigurationDatabase.OrganizationDatabaseData::get_ScaleGroupId()
0x4eb38  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4eb3d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4eb42  brfalse.s loc_4EB93
0x4eb44  ldarg.0
0x4eb45  ldfld    class Microsoft.Crm.LocatorService Microsoft.Crm.ConfigurationDatabase.OrganizationDatabaseService::_locatorService
0x4eb4a  ldstr    aScalegroup// "ScaleGroup"
0x4eb4f  ldloc.0
0x4eb50  ldstr    aScalegroupid_0// "ScaleGroupId"
0x4eb55  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4eb5a  ldc.i4.1
0x4eb5b  newarr   [mscorlib]System.String
0x4eb60  dup
0x4eb61  ldc.i4.0
0x4eb62  ldstr    aName// "Name"
0x4eb67  stelem.ref
0x4eb68  ldc.i4.s 0x2E
0x4eb6a  ldstr    aRetrieveorgani_0// "RetrieveOrganizationDatabaseData"
0x4eb6f  ldstr    aDA1SSrcPlatfor_39// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4eb74  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4eb79  stloc.2
0x4eb7a  ldloc.2
0x4eb7b  brfalse.s loc_4EB93
0x4eb7d  ldloc.1
0x4eb7e  ldloc.2
0x4eb7f  ldstr    aName// "Name"
0x4eb84  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4eb89  castclass [mscorlib]System.String
0x4eb8e  callvirt instance void Microsoft.Crm.ConfigurationDatabase.OrganizationDatabaseData::set_ScaleGroupName(string value)
0x4eb93  ldloc.1
0x4eb94  ret
```
