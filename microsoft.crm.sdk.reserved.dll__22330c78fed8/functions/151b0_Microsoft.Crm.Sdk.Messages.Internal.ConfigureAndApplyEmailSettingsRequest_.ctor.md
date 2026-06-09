# Microsoft.Crm.Sdk.Messages.Internal.ConfigureAndApplyEmailSettingsRequest::.ctor

- ea: `0x151b0`
- end: `0x151c9`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ConfigureAndApplyEmailSettingsRequest::.ctor`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x15190`

## string_xrefs

- `0x151b7`: `ConfigureAndApplyEmailSettings`

## pseudocode

```c

```

## disassembly

```asm
0x151b0  ldarg.0
0x151b1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x151b6  ldarg.0
0x151b7  ldstr    aConfigureandap// "ConfigureAndApplyEmailSettings"
0x151bc  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x151c1  ldarg.0
0x151c2  ldc.i4.0
0x151c3  call     instance void Microsoft.Crm.Sdk.Messages.Internal.ConfigureAndApplyEmailSettingsRequest::set_EnableCrmAppForOutlook(bool value)
0x151c8  ret
```
