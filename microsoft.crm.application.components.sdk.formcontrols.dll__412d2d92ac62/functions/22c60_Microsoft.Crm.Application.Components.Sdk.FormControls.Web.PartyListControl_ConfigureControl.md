# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::ConfigureControl

- ea: `0x22c60`
- end: `0x22cb9`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::ConfigureControl`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x182d0`
- `0x1f6a0`
- `0x1f8f0`
- `0x1f930`
- `0x1f940`
- `0x1fe30`
- `0x22c60`

## string_xrefs

- `0x22cae`: `try {updateFaxNumber();}catch(e){}`

## pseudocode

```c

```

## disassembly

```asm
0x22c60  ldarg.0
0x22c61  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::ConfigureControl()
0x22c66  ldarg.0
0x22c67  ldarg.0
0x22c68  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x22c6d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x22c72  call     int32[] [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Utility.ActivityHelper::BuildAllowedObjectTypeCodeList(int32[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x22c77  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[] value)
0x22c7c  ldarg.0
0x22c7d  ldstr    aMsCrmLookupPar_2// "ms-crm-Lookup-Party"
0x22c82  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupImageClass(string value)
0x22c87  ldarg.0
0x22c88  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x22c8d  brfalse.s loc_22CB8
0x22c8f  ldarg.0
0x22c90  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x22c95  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata
0x22c9a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x22c9f  stloc.0
0x22ca0  ldstr    aFaxpartylist// "faxpartylist"
0x22ca5  ldloc.0
0x22ca6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22cab  brfalse.s loc_22CB8
0x22cad  ldarg.0
0x22cae  ldstr    aTryUpdatefaxnu// "try {updateFaxNumber();}catch(e){}"
0x22cb3  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_OnSelect(string value)
0x22cb8  ret
```
