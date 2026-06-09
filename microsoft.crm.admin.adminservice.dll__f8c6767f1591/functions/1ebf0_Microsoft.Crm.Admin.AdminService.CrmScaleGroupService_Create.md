# Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::Create

- ea: `0x1ebf0`
- end: `0x1ee54`
- name: `Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::Create`
- size: `612`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callees

- `0x18790`
- `0x1e880`
- `0x1e940`
- `0x1ebf0`
- `0x1f6d0`
- `0x20160`
- `0x20180`
- `0x201a0`
- `0x201e0`
- `0x20230`
- `0x20270`
- `0x202b0`
- `0x202f0`
- `0x20330`
- `0x20370`
- `0x203b0`
- `0x203f0`
- `0x20430`
- `0x204d0`
- `0x20510`
- `0x205d0`
- `0x2f2d0`
- `0x2f310`

## string_xrefs

- `0x1ed37`: `Create`
- `0x1ed3c`: `D:\a\1\s\src\CrmLive\Admin\ScaleGroup\CrmScaleGroupService.cs`
- `0x1edfb`: `Created ScaleGroup, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x1ebf0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1ebf5  ldc.i4.s 9
0x1ebf7  ldstr    aCreatingScaleg// "Creating ScaleGroup, Name=({0}), WebApp"...
0x1ebfc  ldc.i4.5
0x1ebfd  newarr   [mscorlib]System.Object
0x1ec02  dup
0x1ec03  ldc.i4.0
0x1ec04  ldarg.1
0x1ec05  stelem.ref
0x1ec06  dup
0x1ec07  ldc.i4.1
0x1ec08  ldarg.2
0x1ec09  stelem.ref
0x1ec0a  dup
0x1ec0b  ldc.i4.2
0x1ec0c  ldarg.3
0x1ec0d  stelem.ref
0x1ec0e  dup
0x1ec0f  ldc.i4.3
0x1ec10  ldarg.s  6
0x1ec12  box      [mscorlib]System.Guid
0x1ec17  stelem.ref
0x1ec18  dup
0x1ec19  ldc.i4.4
0x1ec1a  ldarg.s  7
0x1ec1c  stelem.ref
0x1ec1d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ec22  ldarg.1
0x1ec23  ldstr    aScalegroupName// "ScaleGroup name"
0x1ec28  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1ec2d  ldarg.2
0x1ec2e  ldstr    aWebapplication// "WebApplicationUrl"
0x1ec33  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1ec38  ldarg.3
0x1ec39  ldstr    aReportserverur// "reportServerUrl"
0x1ec3e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1ec43  ldarg.s  4
0x1ec45  ldstr    aInternalsdkend// "internalSdkEndpoint"
0x1ec4a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1ec4f  ldarg.s  5
0x1ec51  ldstr    aExternalsdkend// "externalSdkEndpoint"
0x1ec56  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1ec5b  newobj   instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::.ctor()
0x1ec60  stloc.0
0x1ec61  ldloc.0
0x1ec62  ldarg.1
0x1ec63  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::MakeGuidFromName(string)
0x1ec68  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_Id(valuetype [mscorlib]System.Guid value)
0x1ec6d  ldloc.0
0x1ec6e  ldarg.1
0x1ec6f  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_Name(string value)
0x1ec74  ldloc.0
0x1ec75  ldc.i4.0
0x1ec76  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_State(valuetype [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupState value)
0x1ec7b  ldloc.0
0x1ec7c  ldc.i4.1
0x1ec7d  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_ProvisioningState(valuetype [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupProvisioningState value)
0x1ec82  ldloc.0
0x1ec83  ldarg.2
0x1ec84  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_WebApplication(string value)
0x1ec89  ldloc.0
0x1ec8a  ldarg.3
0x1ec8b  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_ReportServer(string value)
0x1ec90  ldloc.0
0x1ec91  ldarg.s  4
0x1ec93  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_InternalSdkEndpoint(string value)
0x1ec98  ldloc.0
0x1ec99  ldarg.s  5
0x1ec9b  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_ExternalSdkEndpoint(string value)
0x1eca0  ldloc.0
0x1eca1  ldarg.s  6
0x1eca3  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_WitnessServerId(valuetype [mscorlib]System.Guid value)
0x1eca8  ldloc.0
0x1eca9  ldarg.s  7
0x1ecab  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_HelpContentServer(string value)
0x1ecb0  ldloc.0
0x1ecb1  ldarg.s  8
0x1ecb3  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_SqlServerName(string value)
0x1ecb8  ldloc.0
0x1ecb9  ldarg.s  9
0x1ecbb  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_StatsSqlServerName(string value)
0x1ecc0  ldloc.0
0x1ecc1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1ecc6  ldstr    aOrgdbsizeoverh// "OrgDbSizeOverhead"
0x1eccb  ldc.i4   0xC8
0x1ecd0  box      [mscorlib]System.Int32
0x1ecd5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1ecda  ldloc.0
0x1ecdb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1ece0  ldstr    aStatscollectio// "StatsCollectionEnabled"
0x1ece5  ldc.i4.0
0x1ece6  box      [mscorlib]System.Boolean
0x1eceb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1ecf0  ldloc.0
0x1ecf1  ldarg.s  0xA
0x1ecf3  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_ScaleGroupVersion(string value)
0x1ecf8  ldloc.0
0x1ecf9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1ecfe  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_PodId(valuetype [mscorlib]System.Guid value)
0x1ed03  ldarg.s  0xB
0x1ed05  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ed0a  brtrue.s loc_1ED20
0x1ed0c  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmPodService::.ctor()
0x1ed11  ldarg.s  0xB
0x1ed13  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmPodService::RetrieveIdFromName(string name)
0x1ed18  stloc.1
0x1ed19  ldloc.0
0x1ed1a  ldloc.1
0x1ed1b  callvirt instance void Microsoft.Crm.Admin.AdminService.ScaleGroupData::set_PodId(valuetype [mscorlib]System.Guid value)
0x1ed20  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1ed25  stloc.2
0x1ed26  ldloc.2
0x1ed27  ldstr    aScalegroup// "ScaleGroup"
0x1ed2c  ldloc.0
0x1ed2d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1ed32  ldc.i4   0xEF
0x1ed37  ldstr    aCreate// "Create"
0x1ed3c  ldstr    aDA1SSrcCrmlive_42// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Scale"...
0x1ed41  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x1ed46  unbox.any [mscorlib]System.Guid
0x1ed4b  stloc.3
0x1ed4c  ldloc.0
0x1ed4d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x1ed52  ldloc.3
0x1ed53  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1ed58  brfalse.s loc_1ED65
0x1ed5a  ldstr    aScalegroupIdsM// "ScaleGroup Ids must be equal"
0x1ed5f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x1ed64  throw
0x1ed65  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::.ctor()
0x1ed6a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1ed6f  stloc.s  4
0x1ed71  ldloc.s  4
0x1ed73  ldstr    aDefaultorganiz// "DefaultOrganizationId"
0x1ed78  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1ed7d  box      [mscorlib]System.Guid
0x1ed82  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1ed87  ldarg.s  4
0x1ed89  newobj   instance void [System]System.Uri::.ctor(string)
0x1ed8e  stloc.s  5
0x1ed90  ldarg.2
0x1ed91  newobj   instance void [System]System.Uri::.ctor(string)
0x1ed96  stloc.s  6
0x1ed98  ldloc.s  4
0x1ed9a  ldstr    aAdrootdomainsc// "ADRootDomainScheme"
0x1ed9f  ldloc.s  5
0x1eda1  callvirt instance string [System]System.Uri::get_Scheme()
0x1eda6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1edab  ldloc.s  4
0x1edad  ldstr    aAdsdkrootdomai// "ADSdkRootDomain"
0x1edb2  ldloc.s  5
0x1edb4  callvirt instance string [System]System.Uri::get_Authority()
0x1edb9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1edbe  ldloc.s  4
0x1edc0  ldstr    aAdwebapplicati// "ADWebApplicationRootDomain"
0x1edc5  ldloc.s  6
0x1edc7  callvirt instance string [System]System.Uri::get_Authority()
0x1edcc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1edd1  ldloc.s  4
0x1edd3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmDeploymentService::Create(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag deployment)
0x1edd8  stloc.s  7
0x1edda  ldloc.s  7
0x1eddc  ldstr    aDeploymentId// "Deployment id"
0x1ede1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1ede6  ldarg.0
0x1ede7  ldloc.0
0x1ede8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x1eded  ldloc.s  7
0x1edef  call     instance void Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::AddDeployment(valuetype [mscorlib]System.Guid scaleGroupId, valuetype [mscorlib]System.Guid deploymentId)
0x1edf4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1edf9  ldc.i4.s 9
0x1edfb  ldstr    aCreatedScalegr// "Created ScaleGroup, Id=({0})"
0x1ee00  ldc.i4.1
0x1ee01  newarr   [mscorlib]System.Object
0x1ee06  dup
0x1ee07  ldc.i4.0
0x1ee08  ldloc.0
0x1ee09  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x1ee0e  box      [mscorlib]System.Guid
0x1ee13  stelem.ref
0x1ee14  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ee19  ldloc.0
0x1ee1a  stloc.s  8
0x1ee1c  leave.s  loc_1EE51
0x1ee1e  ldloc.2
0x1ee1f  brfalse.s loc_1EE27
0x1ee21  ldloc.2
0x1ee22  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ee27  endfinally
0x1ee28  stloc.s  9
0x1ee2a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1ee2f  ldc.i4.s 9
0x1ee31  ldstr    aExceptionCreat_3// "Exception creating ScaleGroup, Name=({0"...
0x1ee36  ldc.i4.2
0x1ee37  newarr   [mscorlib]System.Object
0x1ee3c  dup
0x1ee3d  ldc.i4.0
0x1ee3e  ldarg.1
0x1ee3f  stelem.ref
0x1ee40  dup
0x1ee41  ldc.i4.1
0x1ee42  ldloc.s  9
0x1ee44  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1ee49  stelem.ref
0x1ee4a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ee4f  rethrow
0x1ee51  ldloc.s  8
0x1ee53  ret
```
