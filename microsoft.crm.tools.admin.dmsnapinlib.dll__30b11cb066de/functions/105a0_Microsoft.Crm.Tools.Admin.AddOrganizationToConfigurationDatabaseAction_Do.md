# Microsoft.Crm.Tools.Admin.AddOrganizationToConfigurationDatabaseAction::Do

- ea: `0x105a0`
- end: `0x10797`
- name: `Microsoft.Crm.Tools.Admin.AddOrganizationToConfigurationDatabaseAction::Do`
- size: `503`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x84f0`
- `0x8630`
- `0x8650`
- `0x8670`
- `0x86e0`
- `0x8720`
- `0x8760`
- `0x8ab0`
- `0x8bf0`
- `0x8cd0`
- `0x9170`
- `0x91d0`
- `0x9210`
- `0x105a0`
- `0x107a0`
- `0x10820`
- `0x10840`
- `0x10880`

## pseudocode

```c

```

## disassembly

```asm
0x105a0  ldarg.1
0x105a1  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0x105a6  stloc.0
0x105a7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x105ac  stloc.1
0x105ad  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x105b2  stloc.2
0x105b3  ldc.i4.0
0x105b4  stloc.3
0x105b5  ldloc.0
0x105b6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x105bb  pop
0x105bc  ldloc.0
0x105bd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x105c2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x105c7  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x105cc  brfalse.s loc_10601
0x105ce  ldloc.0
0x105cf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x105d4  stloc.1
0x105d5  ldarg.0
0x105d6  ldloc.1
0x105d7  call     instance bool Microsoft.Crm.Tools.Admin.AddOrganizationToConfigurationDatabaseAction::VerifyIfOrganizationExists(valuetype [mscorlib]System.Guid organizationId)
0x105dc  stloc.3
0x105dd  ldstr    aVerifyiforgani// "VerifyIfOrganizationExists Returned: {0"...
0x105e2  ldc.i4.2
0x105e3  newarr   [mscorlib]System.Object
0x105e8  dup
0x105e9  ldc.i4.0
0x105ea  ldloc.3
0x105eb  box      [mscorlib]System.Boolean
0x105f0  stelem.ref
0x105f1  dup
0x105f2  ldc.i4.1
0x105f3  ldloc.1
0x105f4  box      [mscorlib]System.Guid
0x105f9  stelem.ref
0x105fa  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x105ff  br.s     loc_1063D
0x10601  ldloc.2
0x10602  ldloc.0
0x10603  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationUniqueName()
0x10608  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::TryIdFromName(string)
0x1060d  stloc.1
0x1060e  ldloca.s 1
0x10610  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10615  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x1061a  brfalse.s loc_1062B
0x1061c  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x10621  stloc.1
0x10622  ldloc.0
0x10623  ldloc.1
0x10624  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x10629  br.s     loc_1063D
0x1062b  ldstr    aOrganizationFo// "Organization found by name"
0x10630  ldc.i4.0
0x10631  newarr   [mscorlib]System.Object
0x10636  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1063b  ldc.i4.1
0x1063c  stloc.3
0x1063d  ldloc.0
0x1063e  ldarg.0
0x1063f  ldloc.0
0x10640  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x10645  call     instance string Microsoft.Crm.Tools.Admin.AddOrganizationToConfigurationDatabaseAction::DressDatabaseNameIfNecessary(string databaseName)
0x1064a  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_DatabaseName(string value)
0x1064f  ldloc.3
0x10650  brtrue   loc_10757
0x10655  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::.ctor()
0x1065a  stloc.s  4
0x1065c  ldloc.s  4
0x1065e  ldloc.1
0x1065f  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Id(valuetype [mscorlib]System.Guid)
0x10664  ldloc.s  4
0x10666  ldloc.0
0x10667  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationUniqueName()
0x1066c  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_UniqueName(string)
0x10671  ldloc.s  4
0x10673  ldloc.0
0x10674  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationFriendlyName()
0x10679  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_FriendlyName(string)
0x1067e  ldloc.s  4
0x10680  ldloc.0
0x10681  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x10686  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1068b  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_SqlServerName(string)
0x10690  ldloc.s  4
0x10692  ldloc.0
0x10693  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x10698  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_DatabaseName(string)
0x1069d  ldloc.s  4
0x1069f  ldloc.0
0x106a0  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ConnectionString()
0x106a5  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_ConnectionString(string)
0x106aa  ldloc.0
0x106ab  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x106b0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x106b5  brtrue.s loc_106C4
0x106b7  ldloc.s  4
0x106b9  ldloc.0
0x106ba  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x106bf  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_SrsUrl(string)
0x106c4  ldloc.s  4
0x106c6  ldc.i4.2
0x106c7  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_State(valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState)
0x106cc  ldloc.s  4
0x106ce  ldloc.0
0x106cf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ScaleGroupId()
0x106d4  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0x106d9  ldloc.s  4
0x106db  ldloc.0
0x106dc  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationType()
0x106e1  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Type(valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType)
0x106e6  ldnull
0x106e7  ldloc.0
0x106e8  callvirt instance class [System]System.Uri Microsoft.Crm.Tools.Admin.OrganizationInfo::get_HelpContentServerUrl()
0x106ed  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x106f2  brfalse.s loc_10706
0x106f4  ldloc.s  4
0x106f6  ldloc.0
0x106f7  callvirt instance class [System]System.Uri Microsoft.Crm.Tools.Admin.OrganizationInfo::get_HelpContentServerUrl()
0x106fc  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x10701  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_HelpContentServerUrl(string)
0x10706  ldloc.s  4
0x10708  call     int32 Microsoft.Crm.Tools.Admin.AddOrganizationToConfigurationDatabaseAction::CalculateInitialPartitionNumber()
0x1070d  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_PartitionNumber(int32)
0x10712  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x10717  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x1071c  call     class [System]System.Diagnostics.FileVersionInfo [System]System.Diagnostics.FileVersionInfo::GetVersionInfo(string)
0x10721  stloc.s  5
0x10723  ldloc.s  4
0x10725  ldloc.s  5
0x10727  callvirt instance int32 [System]System.Diagnostics.FileVersionInfo::get_ProductMajorPart()
0x1072c  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_MajorVersion(int32)
0x10731  ldloc.s  4
0x10733  ldloc.s  5
0x10735  callvirt instance int32 [System]System.Diagnostics.FileVersionInfo::get_ProductMinorPart()
0x1073a  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_MinorVersion(int32)
0x1073f  ldloc.s  4
0x10741  ldloc.s  5
0x10743  callvirt instance int32 [System]System.Diagnostics.FileVersionInfo::get_ProductBuildPart()
0x10748  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_BuildNumber(int32)
0x1074d  ldloc.2
0x1074e  ldloc.s  4
0x10750  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Create(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData)
0x10755  br.s     loc_10790
0x10757  ldloc.2
0x10758  ldloc.1
0x10759  ldc.i4.2
0x1075a  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::SetState(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState)
0x1075f  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::.ctor()
0x10764  stloc.s  6
0x10766  ldloc.s  6
0x10768  ldloc.1
0x10769  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Id(valuetype [mscorlib]System.Guid)
0x1076e  ldloc.s  6
0x10770  ldloc.0
0x10771  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x10776  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_SqlServerName(string)
0x1077b  ldloc.s  6
0x1077d  ldloc.0
0x1077e  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ConnectionString()
0x10783  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_ConnectionString(string)
0x10788  ldloc.2
0x10789  ldloc.s  6
0x1078b  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Update(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData)
0x10790  ldarg.0
0x10791  call     instance void Microsoft.Crm.Tools.Admin.AddOrganizationToConfigurationDatabaseAction::CreateDeploymentIfNotPresent()
0x10796  ret
```
