# Microsoft.Crm.Sdk.Messages.Internal.SaveEntityGroupConfigurationRequest::.ctor

- ea: `0x6880`
- end: `0x68a0`
- name: `Microsoft.Crm.Sdk.Messages.Internal.SaveEntityGroupConfigurationRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6810`
- `0x6860`

## string_xrefs

- `0x6887`: `SaveEntityGroupConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x6880  ldarg.0
0x6881  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x6886  ldarg.0
0x6887  ldstr    aSaveentitygrou// "SaveEntityGroupConfiguration"
0x688c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x6891  ldarg.0
0x6892  ldnull
0x6893  call     instance void Microsoft.Crm.Sdk.Messages.Internal.SaveEntityGroupConfigurationRequest::set_EntityGroupName(string value)
0x6898  ldarg.0
0x6899  ldnull
0x689a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.SaveEntityGroupConfigurationRequest::set_EntityGroupConfiguration(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.QuickFindConfigurationCollection value)
0x689f  ret
```
