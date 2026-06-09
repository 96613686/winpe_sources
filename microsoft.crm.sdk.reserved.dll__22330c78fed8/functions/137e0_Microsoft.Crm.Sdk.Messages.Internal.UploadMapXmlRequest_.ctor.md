# Microsoft.Crm.Sdk.Messages.Internal.UploadMapXmlRequest::.ctor

- ea: `0x137e0`
- end: `0x13800`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UploadMapXmlRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x13770`
- `0x137c0`

## string_xrefs

- `0x137e7`: `UploadMapXml`

## pseudocode

```c

```

## disassembly

```asm
0x137e0  ldarg.0
0x137e1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x137e6  ldarg.0
0x137e7  ldstr    aUploadmapxml// "UploadMapXml"
0x137ec  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x137f1  ldarg.0
0x137f2  ldnull
0x137f3  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UploadMapXmlRequest::set_mapXml(string value)
0x137f8  ldarg.0
0x137f9  ldnull
0x137fa  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UploadMapXmlRequest::set_mapName(string value)
0x137ff  ret
```
