# Microsoft.Crm.CrmLive.Provisioning.VerifySupportOrganizationAction::Do

- ea: `0x12110`
- end: `0x122e0`
- name: `Microsoft.Crm.CrmLive.Provisioning.VerifySupportOrganizationAction::Do`
- size: `464`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x64b0`
- `0x6520`
- `0x6550`
- `0x91b0`
- `0x12110`

## string_xrefs

- `0x1218d`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\VerifyMonitoringAndSupportOrganizationAction.cs`
- `0x12237`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\VerifyMonitoringAndSupportOrganizationAction.cs`

## pseudocode

```c

```

## disassembly

```asm
0x12110  ldarg.0
0x12111  ldarg.0
0x12112  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x12117  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1211c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x12121  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0x12126  ldarg.0
0x12127  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x1212c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x12131  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Type()
0x12136  ldc.i4.2
0x12137  bne.un   loc_122C9
0x1213c  ldarg.0
0x1213d  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x12142  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x12147  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ScaleGroupId()
0x1214c  stloc.0
0x1214d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x12152  stloc.1
0x12153  ldloc.1
0x12154  ldstr    aId// "Id"
0x12159  ldloc.0
0x1215a  box      [mscorlib]System.Guid
0x1215f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12164  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x12169  ldstr    aScalegroup// "ScaleGroup"
0x1216e  ldc.i4.1
0x1216f  newarr   [mscorlib]System.String
0x12174  dup
0x12175  ldc.i4.0
0x12176  ldstr    aId// "Id"
0x1217b  stelem.ref
0x1217c  ldc.i4.1
0x1217d  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x12182  dup
0x12183  ldc.i4.0
0x12184  ldloc.1
0x12185  stelem.ref
0x12186  ldc.i4.s 0x19
0x12188  ldstr    aDo// "Do"
0x1218d  ldstr    aDDbsShDccm2110_25// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x12192  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x12197  stloc.2
0x12198  ldloc.2
0x12199  brfalse.s loc_121AC
0x1219b  ldloc.2
0x1219c  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x121a1  brfalse.s loc_121AC
0x121a3  ldloc.2
0x121a4  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x121a9  ldc.i4.1
0x121aa  beq.s    loc_121BD
0x121ac  ldc.i4   0x8004B014
0x121b1  ldc.i4.0
0x121b2  newarr   [mscorlib]System.Object
0x121b7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x121bc  throw
0x121bd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x121c2  stloc.3
0x121c3  ldloc.3
0x121c4  ldstr    aType// "Type"
0x121c9  ldarg.0
0x121ca  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x121cf  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x121d4  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Type()
0x121d9  box      [mscorlib]System.Int32
0x121de  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x121e3  ldloc.3
0x121e4  ldstr    aScalegroupid// "ScaleGroupId"
0x121e9  ldloc.0
0x121ea  box      [mscorlib]System.Guid
0x121ef  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x121f4  ldloc.3
0x121f5  ldstr    aDatacenterid_0// "DatacenterId"
0x121fa  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x121ff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x12204  box      [mscorlib]System.Guid
0x12209  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1220e  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x12213  ldstr    aOrganization// "Organization"
0x12218  ldc.i4.1
0x12219  newarr   [mscorlib]System.String
0x1221e  dup
0x1221f  ldc.i4.0
0x12220  ldstr    aId// "Id"
0x12225  stelem.ref
0x12226  ldc.i4.1
0x12227  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x1222c  dup
0x1222d  ldc.i4.0
0x1222e  ldloc.3
0x1222f  stelem.ref
0x12230  ldc.i4.s 0x25
0x12232  ldstr    aDo// "Do"
0x12237  ldstr    aDDbsShDccm2110_25// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x1223c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x12241  stloc.2
0x12242  ldloc.2
0x12243  brfalse  loc_122C9
0x12248  ldloc.2
0x12249  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x1224e  brfalse.s loc_122C9
0x12250  ldloc.2
0x12251  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x12256  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x1225b  stloc.s  4
0x1225d  br.s     loc_122B0
0x1225f  ldloca.s 4
0x12261  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x12266  ldstr    aId// "Id"
0x1226b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x12270  unbox.any [mscorlib]System.Guid
0x12275  ldarg.0
0x12276  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x1227b  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x12280  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x12285  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1228a  brfalse.s loc_122B0
0x1228c  ldarg.0
0x1228d  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x12292  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x12297  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Type()
0x1229c  ldc.i4.2
0x1229d  bne.un.s loc_122B0
0x1229f  ldc.i4   0x8004B025
0x122a4  ldc.i4.0
0x122a5  newarr   [mscorlib]System.Object
0x122aa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x122af  throw
0x122b0  ldloca.s 4
0x122b2  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x122b7  brtrue.s loc_1225F
0x122b9  leave.s  loc_122C9
0x122bb  ldloca.s 4
0x122bd  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x122c3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x122c8  endfinally
0x122c9  ldarg.0
0x122ca  ldarg.0
0x122cb  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x122d0  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x122d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x122da  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x122df  ret
```
