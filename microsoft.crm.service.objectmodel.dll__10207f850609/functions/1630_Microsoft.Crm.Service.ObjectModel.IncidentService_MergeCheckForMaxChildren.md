# Microsoft.Crm.Service.ObjectModel.IncidentService::MergeCheckForMaxChildren

- ea: `0x1630`
- end: `0x173e`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::MergeCheckForMaxChildren`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1630`
- `0x1cc0`
- `0x1d10`

## string_xrefs

- `0x1657`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Service\ObjectModel\Services\CS\IncidentService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x1630  ldc.i4.0
0x1631  stloc.0
0x1632  ldc.i4.0
0x1633  stloc.1
0x1634  ldc.i4.0
0x1635  stloc.2
0x1636  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x163b  brtrue.s loc_1672
0x163d  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x1642  ldarg.3
0x1643  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1648  ldstr    aMaxchildincide// "MaxChildIncidentNumber"
0x164d  ldc.i4   0x14D
0x1652  ldstr    aMergecheckform// "MergeCheckForMaxChildren"
0x1657  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x165c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x1661  stloc.s  5
0x1663  ldloc.s  5
0x1665  brtrue.s loc_166A
0x1667  ldc.i4.0
0x1668  br.s     loc_1671
0x166a  ldloc.s  5
0x166c  unbox.any [mscorlib]System.Int32
0x1671  stloc.2
0x1672  ldarg.1
0x1673  ldstr    aIncidentid// "incidentid"
0x1678  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x167d  unbox.any [mscorlib]System.Guid
0x1682  ldarg.1
0x1683  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x1688  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x168d  ldarg.3
0x168e  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1693  stloc.3
0x1694  ldarg.0
0x1695  ldloc.3
0x1696  ldarg.3
0x1697  call     instance bool Microsoft.Crm.Service.ObjectModel.IncidentService::IsParentCase(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x169c  brfalse.s loc_16B7
0x169e  ldarg.0
0x169f  ldloc.3
0x16a0  ldarg.3
0x16a1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.IncidentService::RetrieveActiveChildRecords(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16a6  stloc.s  6
0x16a8  ldloc.s  6
0x16aa  brfalse.s loc_16B5
0x16ac  ldloc.s  6
0x16ae  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x16b3  br.s     loc_16B6
0x16b5  ldc.i4.0
0x16b6  stloc.0
0x16b7  ldarg.2
0x16b8  ldstr    aIncidentid// "incidentid"
0x16bd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x16c2  unbox.any [mscorlib]System.Guid
0x16c7  ldarg.2
0x16c8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x16cd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x16d2  ldarg.3
0x16d3  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x16d8  stloc.s  4
0x16da  ldarg.0
0x16db  ldloc.s  4
0x16dd  ldarg.3
0x16de  call     instance bool Microsoft.Crm.Service.ObjectModel.IncidentService::IsParentCase(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16e3  brfalse.s loc_16FF
0x16e5  ldarg.0
0x16e6  ldloc.s  4
0x16e8  ldarg.3
0x16e9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.IncidentService::RetrieveActiveChildRecords(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16ee  stloc.s  7
0x16f0  ldloc.s  7
0x16f2  brfalse.s loc_16FD
0x16f4  ldloc.s  7
0x16f6  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x16fb  br.s     loc_16FE
0x16fd  ldc.i4.0
0x16fe  stloc.1
0x16ff  ldloc.2
0x1700  ldloc.0
0x1701  ldloc.1
0x1702  add
0x1703  bge.s    loc_173D
0x1705  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x170a  ldstr    aAParentCaseCan// "A Parent Case cannot have more than {0}"...
0x170f  ldc.i4.1
0x1710  newarr   [mscorlib]System.Object
0x1715  dup
0x1716  ldc.i4.0
0x1717  ldloc.2
0x1718  box      [mscorlib]System.Int32
0x171d  stelem.ref
0x171e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1723  ldc.i4   0x8003F454
0x1728  ldc.i4.1
0x1729  newarr   [mscorlib]System.Object
0x172e  dup
0x172f  ldc.i4.0
0x1730  ldloc.2
0x1731  box      [mscorlib]System.Int32
0x1736  stelem.ref
0x1737  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32, object[])
0x173c  throw
0x173d  ret
```
