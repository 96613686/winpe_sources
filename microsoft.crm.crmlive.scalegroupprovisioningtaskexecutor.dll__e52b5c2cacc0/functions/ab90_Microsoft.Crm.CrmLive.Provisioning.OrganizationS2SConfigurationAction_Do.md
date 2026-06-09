# Microsoft.Crm.CrmLive.Provisioning.OrganizationS2SConfigurationAction::Do

- ea: `0xab90`
- end: `0xace8`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationS2SConfigurationAction::Do`
- size: `344`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x64b0`
- `0x6520`
- `0x6550`
- `0x91b0`
- `0xab50`
- `0xab90`
- `0xacf0`

## string_xrefs

- `0xabd2`: `Configuring S2S for organization [{0}, {1}]`
- `0xac3a`: `Configuring S2S for organization [{0}, {1}] succeeded`
- `0xac8b`: `Configuring S2S for organization [{0}, {1}] failed. Error: {2}`

## pseudocode

```c

```

## disassembly

```asm
0xab90  ldarg.0
0xab91  ldarg.0
0xab92  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xab97  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xab9c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xaba1  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0xaba6  ldarg.0
0xaba7  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xabac  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xabb1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xabb6  call     bool Microsoft.Crm.CrmLive.Provisioning.OrganizationS2SConfigurationAction::IsOsdpOrganization(valuetype [mscorlib]System.Guid orgId)
0xabbb  brfalse  loc_ACD1
0xabc0  ldarg.0
0xabc1  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xabc6  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xabcb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xabd0  ldc.i4.s 0xA
0xabd2  ldstr    aConfiguringS2s// "Configuring S2S for organization [{0}, "...
0xabd7  ldc.i4.2
0xabd8  newarr   [mscorlib]System.Object
0xabdd  dup
0xabde  ldc.i4.0
0xabdf  ldarg.0
0xabe0  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xabe5  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xabea  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0xabef  stelem.ref
0xabf0  dup
0xabf1  ldc.i4.1
0xabf2  ldarg.0
0xabf3  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xabf8  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xabfd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xac02  box      [mscorlib]System.Guid
0xac07  stelem.ref
0xac08  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xac0d  ldarg.0
0xac0e  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xac13  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xac18  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xac1d  ldarg.0
0xac1e  call     instance bool Microsoft.Crm.CrmLive.Provisioning.OrganizationS2SConfigurationAction::get_IsNewOrganization()
0xac23  call     void [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.S2SUtility::ConfigureOrganization(valuetype [mscorlib]System.Guid, bool)
0xac28  ldarg.0
0xac29  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xac2e  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xac33  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xac38  ldc.i4.s 0xA
0xac3a  ldstr    aConfiguringS2s_0// "Configuring S2S for organization [{0}, "...
0xac3f  ldc.i4.2
0xac40  newarr   [mscorlib]System.Object
0xac45  dup
0xac46  ldc.i4.0
0xac47  ldarg.0
0xac48  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xac4d  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xac52  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0xac57  stelem.ref
0xac58  dup
0xac59  ldc.i4.1
0xac5a  ldarg.0
0xac5b  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xac60  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xac65  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xac6a  box      [mscorlib]System.Guid
0xac6f  stelem.ref
0xac70  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xac75  leave.s  loc_ACD1
0xac77  stloc.0
0xac78  ldloc.0
0xac79  ldarg.0
0xac7a  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xac7f  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xac84  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xac89  ldc.i4.s 0xA
0xac8b  ldstr    aConfiguringS2s_1// "Configuring S2S for organization [{0}, "...
0xac90  ldc.i4.3
0xac91  newarr   [mscorlib]System.Object
0xac96  dup
0xac97  ldc.i4.0
0xac98  ldarg.0
0xac99  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xac9e  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xaca3  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0xaca8  stelem.ref
0xaca9  dup
0xacaa  ldc.i4.1
0xacab  ldarg.0
0xacac  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xacb1  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xacb6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xacbb  box      [mscorlib]System.Guid
0xacc0  stelem.ref
0xacc1  dup
0xacc2  ldc.i4.2
0xacc3  ldloc.0
0xacc4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0xacc9  stelem.ref
0xacca  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xaccf  rethrow
0xacd1  ldarg.0
0xacd2  ldarg.0
0xacd3  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xacd8  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xacdd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xace2  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0xace7  ret
```
