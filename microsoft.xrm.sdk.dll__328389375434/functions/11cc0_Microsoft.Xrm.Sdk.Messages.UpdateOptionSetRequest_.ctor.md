# Microsoft.Xrm.Sdk.Messages.UpdateOptionSetRequest::.ctor

- ea: `0x11cc0`
- end: `0x11ce0`
- name: `Microsoft.Xrm.Sdk.Messages.UpdateOptionSetRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0x11c00`
- `0x11c50`

## string_xrefs

- `0x11cc7`: `UpdateOptionSet`

## pseudocode

```c

```

## disassembly

```asm
0x11cc0  ldarg.0
0x11cc1  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x11cc6  ldarg.0
0x11cc7  ldstr    aUpdateoptionse// "UpdateOptionSet"
0x11ccc  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0x11cd1  ldarg.0
0x11cd2  ldnull
0x11cd3  call     instance void Microsoft.Xrm.Sdk.Messages.UpdateOptionSetRequest::set_OptionSet(class Microsoft.Xrm.Sdk.Metadata.OptionSetMetadataBase value)
0x11cd8  ldarg.0
0x11cd9  ldc.i4.0
0x11cda  call     instance void Microsoft.Xrm.Sdk.Messages.UpdateOptionSetRequest::set_MergeLabels(bool value)
0x11cdf  ret
```
