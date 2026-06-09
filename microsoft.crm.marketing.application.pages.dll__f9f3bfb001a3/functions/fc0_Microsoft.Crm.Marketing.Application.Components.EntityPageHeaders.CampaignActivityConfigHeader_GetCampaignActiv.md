# Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::GetCampaignActivityTemplateFlag

- ea: `0xfc0`
- end: `0x103e`
- name: `Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::GetCampaignActivityTemplateFlag`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf10`
- `0x1dd0`

## callees

- `0xfc0`

## string_xrefs

- `0xff8`: `istemplate`
- `0x1004`: `istemplate`
- `0x1023`: `Parent Campaign for this CA is Template = {0}`

## pseudocode

```c

```

## disassembly

```asm
0xfc0  ldc.i4.0
0xfc1  stloc.0
0xfc2  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadCampaign()
0xfc7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfcc  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfd1  brfalse.s loc_1014
0xfd3  ldstr    aCampaign// "campaign"
0xfd8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfdd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfe2  newobj   instance void [Microsoft.Crm.Marketing.Application.Platform]Microsoft.Crm.Marketing.Application.Platform.Campaign::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xfe7  stloc.1
0xfe8  ldloc.1
0xfe9  ldarg.0
0xfea  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0xfef  ldloc.1
0xff0  ldc.i4.1
0xff1  newarr   [mscorlib]System.String
0xff6  dup
0xff7  ldc.i4.0
0xff8  ldstr    aIstemplate// "istemplate"
0xffd  stelem.ref
0xffe  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string[])
0x1003  ldloc.1
0x1004  ldstr    aIstemplate// "istemplate"
0x1009  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x100e  unbox.any [mscorlib]System.Boolean
0x1013  stloc.0
0x1014  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1019  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x101e  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x1023  ldstr    aParentCampaign// "Parent Campaign for this CA is Template"...
0x1028  ldc.i4.1
0x1029  newarr   [mscorlib]System.Object
0x102e  dup
0x102f  ldc.i4.0
0x1030  ldloc.0
0x1031  box      [mscorlib]System.Boolean
0x1036  stelem.ref
0x1037  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x103c  ldloc.0
0x103d  ret
```
