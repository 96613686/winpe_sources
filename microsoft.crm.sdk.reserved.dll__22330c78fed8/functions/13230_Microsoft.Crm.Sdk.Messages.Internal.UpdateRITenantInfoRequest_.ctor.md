# Microsoft.Crm.Sdk.Messages.Internal.UpdateRITenantInfoRequest::.ctor

- ea: `0x13230`
- end: `0x13250`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateRITenantInfoRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x131c0`
- `0x13210`

## string_xrefs

- `0x13237`: `UpdateRITenantInfo`

## pseudocode

```c

```

## disassembly

```asm
0x13230  ldarg.0
0x13231  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x13236  ldarg.0
0x13237  ldstr    aUpdateritenant// "UpdateRITenantInfo"
0x1323c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x13241  ldarg.0
0x13242  ldnull
0x13243  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateRITenantInfoRequest::set_HubName(string value)
0x13248  ldarg.0
0x13249  ldnull
0x1324a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateRITenantInfoRequest::set_PrimaryKey(string value)
0x1324f  ret
```
