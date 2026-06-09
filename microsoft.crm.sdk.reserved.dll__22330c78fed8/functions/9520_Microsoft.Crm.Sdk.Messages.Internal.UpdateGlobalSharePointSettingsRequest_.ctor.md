# Microsoft.Crm.Sdk.Messages.Internal.UpdateGlobalSharePointSettingsRequest::.ctor

- ea: `0x9520`
- end: `0x9547`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateGlobalSharePointSettingsRequest::.ctor`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x9460`
- `0x94b0`
- `0x9500`

## string_xrefs

- `0x9527`: `UpdateGlobalSharePointSettings`

## pseudocode

```c

```

## disassembly

```asm
0x9520  ldarg.0
0x9521  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x9526  ldarg.0
0x9527  ldstr    aUpdateglobalsh// "UpdateGlobalSharePointSettings"
0x952c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x9531  ldarg.0
0x9532  ldnull
0x9533  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateGlobalSharePointSettingsRequest::set_SharePointRealm(string value)
0x9538  ldarg.0
0x9539  ldc.i4.0
0x953a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateGlobalSharePointSettingsRequest::set_IsSharePointOnline(bool value)
0x953f  ldarg.0
0x9540  ldc.i4.0
0x9541  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateGlobalSharePointSettingsRequest::set_UseAuthorizationServer(bool value)
0x9546  ret
```
