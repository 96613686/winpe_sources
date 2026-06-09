# Microsoft.Crm.CrmLive.Provisioning.Organization::Delete_1

- ea: `0x187c0`
- end: `0x18eab`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::Delete_1`
- size: `1771`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x187b0`
- `0x22bb0`

## callees

- `0x2d30`
- `0x4d90`
- `0x5ac0`
- `0x6510`
- `0x6d00`
- `0x7860`
- `0x9110`
- `0x91b0`
- `0x9260`
- `0x9650`
- `0x9c80`
- `0xa5e0`
- `0xa600`
- `0xa630`
- `0x12fc0`
- `0x18730`
- `0x187c0`
- `0x18eb0`
- `0x18fa0`
- `0x1a530`
- `0x1bb70`
- `0x1c0c0`
- `0x1c3b0`
- `0x31960`

## string_xrefs

- `0x188e1`: `DeleteOrganization`
- `0x18cb3`: `DeleteOrganization`
- `0x18827`: `Delete`
- `0x18864`: `Delete`
- `0x1882c`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Organization.cs`
- `0x18869`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Organization.cs`
- `0x18901`: `Both organization and organizationlifecycle records does not exist. Delete operation exiting`
- `0x18c17`: `Delete organization: create BreakOrgDBMirroring queue item.`
- `0x18d98`: `Completed`
- `0x18e2a`: `Organization Delete: {0} Failed with Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x187c0  newobj   instance void <>c__DisplayClass9_0::.ctor()
0x187c5  stloc.0
0x187c6  ldloc.0
0x187c7  ldarg.1
0x187c8  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass9_0::organizationId
0x187cd  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::.ctor()
0x187d2  stloc.1
0x187d3  ldnull
0x187d4  stloc.2
0x187d5  ldnull
0x187d6  stloc.3
0x187d7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x187dc  stloc.s  4
0x187de  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0x187e3  stloc.s  5
0x187e5  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x187ea  stloc.s  6
0x187ec  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x187f1  stloc.s  7
0x187f3  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x187f8  stloc.s  0xD
0x187fa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x187ff  stloc.s  0xE
0x18801  ldloc.s  0xE
0x18803  ldstr    aId// "Id"
0x18808  ldloc.0
0x18809  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass9_0::organizationId
0x1880e  box      [mscorlib]System.Guid
0x18813  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x18818  ldloc.s  0xD
0x1881a  ldstr    aOrganization// "Organization"
0x1881f  ldnull
0x18820  ldloc.s  0xE
0x18822  ldc.i4   0x11C
0x18827  ldstr    aDelete// "Delete"
0x1882c  ldstr    aDDbsShDccm2110_30// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x18831  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x18836  stloc.3
0x18837  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1883c  stloc.s  0xF
0x1883e  ldloc.s  0xF
0x18840  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x18845  ldloc.0
0x18846  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass9_0::organizationId
0x1884b  box      [mscorlib]System.Guid
0x18850  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x18855  ldloc.s  0xD
0x18857  ldstr    aOrganizationli// "OrganizationLifecycle"
0x1885c  ldnull
0x1885d  ldloc.s  0xF
0x1885f  ldc.i4   0x121
0x18864  ldstr    aDelete// "Delete"
0x18869  ldstr    aDDbsShDccm2110_30// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x1886e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x18873  stloc.2
0x18874  ldloc.3
0x18875  brtrue   loc_18921
0x1887a  ldloc.2
0x1887b  brfalse.s loc_188F9
0x1887d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x18882  stloc.s  0x10
0x18884  ldarg.3
0x18885  brfalse.s loc_188A2
0x18887  ldloc.s  0x10
0x18889  ldstr    aEntriesForOrga// "Entries for Organization with Id: {0} a"...
0x1888e  ldloc.0
0x1888f  ldftn    instance object <>c__DisplayClass9_0::<Delete>b__0()
0x18895  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x1889a  call     class [mscorlib]System.Text.StringBuilder Microsoft.Crm.CrmLive.Provisioning.StringBuilderExtensions::AppendLine(class [mscorlib]System.Text.StringBuilder builder, string format, class [mscorlib]System.Func`1<object> arg)
0x1889f  pop
0x188a0  br.s     loc_188D5
0x188a2  ldloc.s  0x10
0x188a4  ldstr    aEntriesForOrga_0// "Entries for Organization with Id: {0} a"...
0x188a9  ldloc.0
0x188aa  ldftn    instance object <>c__DisplayClass9_0::<Delete>b__1()
0x188b0  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x188b5  call     class [mscorlib]System.Text.StringBuilder Microsoft.Crm.CrmLive.Provisioning.StringBuilderExtensions::AppendLine(class [mscorlib]System.Text.StringBuilder builder, string format, class [mscorlib]System.Func`1<object> arg)
0x188ba  pop
0x188bb  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x188c0  ldstr    aOrganizationli// "OrganizationLifecycle"
0x188c5  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x188ca  ldloc.0
0x188cb  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass9_0::organizationId
0x188d0  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteOrganizationRelatedRecords(string, string, valuetype [mscorlib]System.Guid)
0x188d5  ldloc.s  5
0x188d7  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x188dc  ldstr    aOrganizationli_1// "OrganizationLifecycle.Id"
0x188e1  ldstr    aDeleteorganiza// "DeleteOrganization"
0x188e6  ldloc.s  0x10
0x188e8  callvirt instance string [mscorlib]System.Object::ToString()
0x188ed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateEntry(valuetype [mscorlib]System.Guid, string, string, string)
0x188f2  stloc.s  4
0x188f4  leave    loc_18EAA
0x188f9  ldloc.0
0x188fa  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass9_0::organizationId
0x188ff  ldc.i4.s 0x4A
0x18901  ldstr    aBothOrganizati// "Both organization and organizationlifec"...
0x18906  ldc.i4.0
0x18907  newarr   [mscorlib]System.Object
0x1890c  call     string [mscorlib]System.String::Format(string, object[])
0x18911  ldc.i4.0
0x18912  newarr   [mscorlib]System.Object
0x18917  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1891c  leave    loc_18EAA
0x18921  ldloc.3
0x18922  ldstr    aState// "State"
0x18927  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1892c  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0x18931  stloc.s  0x11
0x18933  ldloc.s  0x11
0x18935  call     bool Microsoft.Crm.CrmLive.Provisioning.Organization::ValidateOrganizationCanBeDeleted(valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState orgState)
0x1893a  brtrue.s loc_18969
0x1893c  ldloc.0
0x1893d  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass9_0::organizationId
0x18942  call     void Microsoft.Crm.CrmLive.Provisioning.Organization::ResetProvisioningActionInProgress(valuetype [mscorlib]System.Guid orgId)
0x18947  ldstr    aOrganizationIs// "Organization is not disabled, pending o"...
0x1894c  ldloca.s 0x11
0x1894e  constrained. [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0x18954  callvirt instance string [mscorlib]System.Object::ToString()
0x18959  call     string [mscorlib]System.String::Concat(string, string)
0x1895e  ldc.i4   0x8004B02F
0x18963  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x18968  throw
0x18969  ldloc.1
0x1896a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1896f  ldloc.0
0x18970  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass9_0::organizationId
0x18975  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Id(valuetype [mscorlib]System.Guid)
0x1897a  ldloc.1
0x1897b  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x18980  ldloc.3
0x18981  ldstr    aUniquename// "UniqueName"
0x18986  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1898b  castclass [mscorlib]System.String
0x18990  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_UniqueName(string)
0x18995  ldloc.1
0x18996  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1899b  ldloc.3
0x1899c  ldstr    aFriendlyname// "FriendlyName"
0x189a1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x189a6  castclass [mscorlib]System.String
0x189ab  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_FriendlyName(string)
0x189b0  ldloc.1
0x189b1  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x189b6  ldloc.3
0x189b7  ldstr    aType// "Type"
0x189bc  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x189c1  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType
0x189c6  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Type(valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType)
0x189cb  ldloc.1
0x189cc  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x189d1  ldloc.3
0x189d2  ldstr    aScalegroupid// "ScaleGroupId"
0x189d7  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x189dc  unbox.any [mscorlib]System.Guid
0x189e1  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0x189e6  ldloc.1
0x189e7  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x189ec  ldloc.3
0x189ed  ldstr    aSqlservername// "SqlServerName"
0x189f2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x189f7  castclass [mscorlib]System.String
0x189fc  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_SqlServerName(string)
0x18a01  ldloc.1
0x18a02  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x18a07  ldloc.3
0x18a08  ldstr    aMirroredsqlser// "MirroredSqlServerName"
0x18a0d  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18a12  castclass [mscorlib]System.String
0x18a17  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_MirroredSqlServerName(string)
0x18a1c  ldloc.1
0x18a1d  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x18a22  ldloc.3
0x18a23  ldstr    aSrsurl// "SrsUrl"
0x18a28  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18a2d  castclass [mscorlib]System.String
0x18a32  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_SrsUrl(string)
0x18a37  ldloc.1
0x18a38  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x18a3d  ldloc.3
0x18a3e  ldstr    aDatabasename// "DatabaseName"
0x18a43  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18a48  castclass [mscorlib]System.String
0x18a4d  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_DatabaseName(string)
0x18a52  ldloc.1
0x18a53  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x18a58  ldloc.3
0x18a59  ldstr    aAvailabilitygr_1// "AvailabilityGroup"
0x18a5e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18a63  castclass [mscorlib]System.String
0x18a68  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_AvailabilityGroupName(string)
0x18a6d  ldloc.1
0x18a6e  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x18a73  ldloc.3
0x18a74  ldstr    aStoragegroupid// "StorageGroupId"
0x18a79  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18a7e  unbox.any [mscorlib]System.Guid
0x18a83  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_StorageGroupId(valuetype [mscorlib]System.Guid)
0x18a88  ldloc.1
0x18a89  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x18a8e  ldloc.3
0x18a8f  ldstr    aConnectionstri// "ConnectionString"
0x18a94  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18a99  castclass [mscorlib]System.String
0x18a9e  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_ConnectionString(string)
0x18aa3  ldloc.1
0x18aa4  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x18aa9  ldloc.3
0x18aaa  ldstr    aIsbackedbyxdb// "IsBackedByXdb"
0x18aaf  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x18ab4  brtrue.s loc_18ABE
0x18ab6  ldc.i4.0
0x18ab7  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x18abc  br.s     loc_18ACE
0x18abe  ldloc.3
0x18abf  ldstr    aIsbackedbyxdb// "IsBackedByXdb"
0x18ac4  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18ac9  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0x18ace  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_IsBackedByXdb(valuetype [mscorlib]System.Nullable`1<bool>)
0x18ad3  ldloc.2
0x18ad4  brfalse  loc_18B66
0x18ad9  ldloc.1
0x18ada  ldsfld   string [mscorlib]System.String::Empty
0x18adf  ldloc.2
0x18ae0  ldstr    aInitialuserfir// "InitialUserFirstName"
0x18ae5  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18aea  castclass [mscorlib]System.String
0x18aef  ldloc.2
0x18af0  ldstr    aInitialuserlas// "InitialUserLastName"
0x18af5  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18afa  castclass [mscorlib]System.String
0x18aff  ldloc.2
0x18b00  ldstr    aInitialuserema// "InitialUserEmail"
0x18b05  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18b0a  castclass [mscorlib]System.String
0x18b0f  ldloc.2
0x18b10  ldstr    aInitialuserpui// "InitialUserPuid"
0x18b15  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18b1a  castclass [mscorlib]System.String
0x18b1f  ldsfld   string [mscorlib]System.String::Empty
0x18b24  ldsfld   string [mscorlib]System.String::Empty
0x18b29  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::.ctor(string, string, string, string, string, string, string)
0x18b2e  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_InitialUser(class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties value)
0x18b33  ldloc.2
0x18b34  ldstr    aContextid// "ContextId"
0x18b39  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x18b3e  brfalse.s loc_18B4D
0x18b40  ldloc.2
0x18b41  ldstr    aContextid// "ContextId"
0x18b46  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18b4b  brtrue.s loc_18B54
0x18b4d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x18b52  br.s     loc_18B64
0x18b54  ldloc.2
0x18b55  ldstr    aContextid// "ContextId"
0x18b5a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18b5f  unbox.any [mscorlib]System.Guid
0x18b64  stloc.s  7
0x18b66  leave.s  loc_18B74
0x18b68  ldloc.s  0xD
0x18b6a  brfalse.s loc_18B73
0x18b6c  ldloc.s  0xD
0x18b6e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18b73  endfinally
0x18b74  ldloc.1
0x18b75  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x18b7a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ScaleGroupId()
0x18b7f  stloc.s  8
0x18b81  ldloc.1
0x18b82  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x18b87  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_IsBackedByXdb()
0x18b8c  stloc.s  0x12
0x18b8e  ldloca.s 0x12
0x18b90  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x18b95  stloc.s  9
0x18b97  ldsfld   string [mscorlib]System.String::Empty
0x18b9c  stloc.s  0xA
0x18b9e  ldarg.s  4
0x18ba0  brtrue.s loc_18BB5
0x18ba2  ldloc.s  9
0x18ba4  brtrue.s loc_18BB5
0x18ba6  ldloc.0
0x18ba7  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass9_0::organizationId
0x18bac  ldloc.s  8
0x18bae  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SqlBackupRestoreUtility::GenerateBackupPath(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x18bb3  stloc.s  0xA
0x18bb5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction>::.ctor()
0x18bba  stloc.s  0xB
0x18bbc  ldarg.s  4
0x18bbe  brtrue.s loc_18BE7
0x18bc0  ldloc.s  0xB
0x18bc2  ldloc.1
0x18bc3  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.QueueMobileOfflineProvisioningWorkItemAction::.ctor(class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties organizationProperties)
0x18bc8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction>::Add(var<u1>)
0x18bcd  ldloc.s  0xB
0x18bcf  ldloc.1
0x18bd0  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.DeprovisionRelationshipIntelligenceAction::.ctor(class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties organizationProperties)
0x18bd5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction>::Add(var<u1>)
0x18bda  ldloc.s  0xB
0x18bdc  ldloc.1
  ... truncated ...
```
