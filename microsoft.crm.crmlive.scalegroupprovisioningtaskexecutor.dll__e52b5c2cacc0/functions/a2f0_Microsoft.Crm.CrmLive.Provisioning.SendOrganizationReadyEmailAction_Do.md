# Microsoft.Crm.CrmLive.Provisioning.SendOrganizationReadyEmailAction::Do

- ea: `0xa2f0`
- end: `0xa3dc`
- name: `Microsoft.Crm.CrmLive.Provisioning.SendOrganizationReadyEmailAction::Do`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x64b0`
- `0x6520`
- `0x6550`
- `0x91b0`
- `0xa2f0`
- `0xa3e0`

## string_xrefs

- `0xa31b`: `Organization Ready Email for Organization `
- `0xa377`: `SendOrganizationReadyEmailAction For Organization: {0} Failed with Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xa2f0  ldarg.0
0xa2f1  ldarg.0
0xa2f2  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa2f7  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa2fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xa301  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0xa306  ldarg.0
0xa307  call     instance class [mscorlib]System.Tuple`3<string, string[], string[]> Microsoft.Crm.CrmLive.Provisioning.SendOrganizationReadyEmailAction::PickTemplate()
0xa30c  stloc.0
0xa30d  ldloc.0
0xa30e  brtrue.s loc_A315
0xa310  leave    loc_A3DB
0xa315  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::.ctor()
0xa31a  dup
0xa31b  ldstr    aOrganizationRe// "Organization Ready Email for Organizati"...
0xa320  ldarg.0
0xa321  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa326  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa32b  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0xa330  call     string [mscorlib]System.String::Concat(string, string)
0xa335  ldc.i4.1
0xa336  ldarg.0
0xa337  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa33c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa341  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xa346  ldloc.0
0xa347  callvirt instance var<u1> class [mscorlib]System.Tuple`3<string, string[], string[]>::get_Item1()
0xa34c  ldloc.0
0xa34d  callvirt instance var<u1> class [mscorlib]System.Tuple`3<string, string[], string[]>::get_Item2()
0xa352  ldloc.0
0xa353  callvirt instance var<u1> class [mscorlib]System.Tuple`3<string, string[], string[]>::get_Item3()
0xa358  ldc.i4.0
0xa359  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xa35e  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0xa363  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::Create(string, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationTargetType, valuetype [mscorlib]System.Guid, string, string[], string[], valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationStatusCode, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xa368  stloc.1
0xa369  ldloc.1
0xa36a  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::SendEmail(valuetype [mscorlib]System.Guid)
0xa36f  leave.s  loc_A3C5
0xa371  stloc.2
0xa372  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa377  ldstr    aSendorganizati// "SendOrganizationReadyEmailAction For Or"...
0xa37c  ldc.i4.2
0xa37d  newarr   [mscorlib]System.Object
0xa382  dup
0xa383  ldc.i4.0
0xa384  ldarg.0
0xa385  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa38a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa38f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xa394  box      [mscorlib]System.Guid
0xa399  stelem.ref
0xa39a  dup
0xa39b  ldc.i4.1
0xa39c  ldloc.2
0xa39d  stelem.ref
0xa39e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa3a3  stloc.3
0xa3a4  ldloc.2
0xa3a5  ldarg.0
0xa3a6  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa3ab  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa3b0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xa3b5  ldc.i4.s 0xA
0xa3b7  ldloc.3
0xa3b8  ldc.i4.0
0xa3b9  newarr   [mscorlib]System.Object
0xa3be  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa3c3  leave.s  loc_A3C5
0xa3c5  ldarg.0
0xa3c6  ldarg.0
0xa3c7  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa3cc  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa3d1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xa3d6  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0xa3db  ret
```
