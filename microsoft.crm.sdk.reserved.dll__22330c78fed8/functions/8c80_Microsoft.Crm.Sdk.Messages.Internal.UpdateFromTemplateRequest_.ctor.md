# Microsoft.Crm.Sdk.Messages.Internal.UpdateFromTemplateRequest::.ctor

- ea: `0x8c80`
- end: `0x8caf`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateFromTemplateRequest::.ctor`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x8bc0`
- `0x8c10`
- `0x8c60`

## string_xrefs

- `0x8c87`: `UpdateFromTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x8c80  ldarg.0
0x8c81  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x8c86  ldarg.0
0x8c87  ldstr    aUpdatefromtemp// "UpdateFromTemplate"
0x8c8c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x8c91  ldarg.0
0x8c92  ldloca.s 0
0x8c94  initobj  [mscorlib]System.Guid
0x8c9a  ldloc.0
0x8c9b  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateFromTemplateRequest::set_ReportId(valuetype [mscorlib]System.Guid value)
0x8ca0  ldarg.0
0x8ca1  ldnull
0x8ca2  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateFromTemplateRequest::set_WizardXml(string value)
0x8ca7  ldarg.0
0x8ca8  ldc.i4.0
0x8ca9  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateFromTemplateRequest::set_IsOrgReport(bool value)
0x8cae  ret
```
