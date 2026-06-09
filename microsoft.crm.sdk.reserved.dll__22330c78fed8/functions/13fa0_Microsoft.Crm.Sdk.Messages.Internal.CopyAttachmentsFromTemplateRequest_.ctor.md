# Microsoft.Crm.Sdk.Messages.Internal.CopyAttachmentsFromTemplateRequest::.ctor

- ea: `0x13fa0`
- end: `0x13fc0`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CopyAttachmentsFromTemplateRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x13f30`
- `0x13f80`

## string_xrefs

- `0x13fa7`: `CopyAttachmentsFromTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x13fa0  ldarg.0
0x13fa1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x13fa6  ldarg.0
0x13fa7  ldstr    aCopyattachment// "CopyAttachmentsFromTemplate"
0x13fac  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x13fb1  ldarg.0
0x13fb2  ldnull
0x13fb3  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CopyAttachmentsFromTemplateRequest::set_Template(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x13fb8  ldarg.0
0x13fb9  ldnull
0x13fba  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CopyAttachmentsFromTemplateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x13fbf  ret
```
