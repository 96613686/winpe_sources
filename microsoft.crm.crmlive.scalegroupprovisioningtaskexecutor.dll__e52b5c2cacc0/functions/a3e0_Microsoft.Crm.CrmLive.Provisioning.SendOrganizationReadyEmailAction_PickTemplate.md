# Microsoft.Crm.CrmLive.Provisioning.SendOrganizationReadyEmailAction::PickTemplate

- ea: `0xa3e0`
- end: `0xa4af`
- name: `Microsoft.Crm.CrmLive.Provisioning.SendOrganizationReadyEmailAction::PickTemplate`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xa2f0`

## callees

- `0x64b0`
- `0x91b0`
- `0xa3e0`

## string_xrefs

- `0xa43b`: `OrganizationReadyEmail_OsdpPreview`
- `0xa460`: `OrganizationReadyEmail_Preview`
- `0xa468`: `Default template for OrganizationReadyEmail`

## pseudocode

```c

```

## disassembly

```asm
0xa3e0  ldnull
0xa3e1  stloc.0
0xa3e2  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xa3e7  ldstr    aPartnerdesigna// "PartnerDesignationUrl"
0xa3ec  ldc.i4.0
0xa3ed  callvirt T0x2B000011
0xa3f2  stloc.1
0xa3f3  ldc.i4.0
0xa3f4  newarr   [mscorlib]System.String
0xa3f9  stloc.2
0xa3fa  ldc.i4.0
0xa3fb  newarr   [mscorlib]System.String
0xa400  stloc.3
0xa401  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0xa406  ldarg.0
0xa407  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa40c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa411  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xa416  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0xa41b  stloc.s  4
0xa41d  ldarg.0
0xa41e  ldfld    bool Microsoft.Crm.CrmLive.Provisioning.SendOrganizationReadyEmailAction::_isProvisionTask
0xa423  ldloc.s  4
0xa425  and
0xa426  brfalse.s loc_A441
0xa428  ldarg.0
0xa429  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa42e  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa433  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Type()
0xa438  ldc.i4.7
0xa439  bne.un.s loc_A441
0xa43b  ldstr    aOrganizationre// "OrganizationReadyEmail_OsdpPreview"
0xa440  stloc.0
0xa441  ldarg.0
0xa442  ldfld    bool Microsoft.Crm.CrmLive.Provisioning.SendOrganizationReadyEmailAction::_isProvisionTask
0xa447  brtrue.s loc_A4A1
0xa449  ldloc.s  4
0xa44b  brtrue.s loc_A4A1
0xa44d  ldarg.0
0xa44e  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa453  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa458  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Type()
0xa45d  ldc.i4.7
0xa45e  bne.un.s loc_A468
0xa460  ldstr    aOrganizationre_0// "OrganizationReadyEmail_Preview"
0xa465  stloc.0
0xa466  br.s     loc_A4A1
0xa468  ldstr    aDefaultTemplat// "Default template for OrganizationReadyE"...
0xa46d  stloc.0
0xa46e  ldc.i4.2
0xa46f  newarr   [mscorlib]System.String
0xa474  dup
0xa475  ldc.i4.0
0xa476  ldstr    aOrganizationPu// "ORGANIZATION_PURCHASE_DATE"
0xa47b  stelem.ref
0xa47c  dup
0xa47d  ldc.i4.1
0xa47e  ldstr    aPartnerDesigna// "PARTNER_DESIGNATION_URL"
0xa483  stelem.ref
0xa484  stloc.2
0xa485  ldc.i4.2
0xa486  newarr   [mscorlib]System.String
0xa48b  dup
0xa48c  ldc.i4.0
0xa48d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Today()
0xa492  stloc.s  5
0xa494  ldloca.s 5
0xa496  call     instance string [mscorlib]System.DateTime::ToLongDateString()
0xa49b  stelem.ref
0xa49c  dup
0xa49d  ldc.i4.1
0xa49e  ldloc.1
0xa49f  stelem.ref
0xa4a0  stloc.3
0xa4a1  ldloc.0
0xa4a2  brtrue.s loc_A4A6
0xa4a4  ldnull
0xa4a5  ret
0xa4a6  ldloc.0
0xa4a7  ldloc.2
0xa4a8  ldloc.3
0xa4a9  call     T0x2B00002E
0xa4ae  ret
```
