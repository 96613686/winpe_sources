# Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelRequest::.ctor

- ea: `0x10990`
- end: `0x109b7`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelRequest::.ctor`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x108d0`
- `0x10920`
- `0x10970`

## string_xrefs

- `0x10997`: `ExportTemplateToExcel`

## pseudocode

```c

```

## disassembly

```asm
0x10990  ldarg.0
0x10991  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x10996  ldarg.0
0x10997  ldstr    aExporttemplate_1// "ExportTemplateToExcel"
0x1099c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x109a1  ldarg.0
0x109a2  ldnull
0x109a3  call     instance void Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelRequest::set_EntityLocalizedDisplayName(string value)
0x109a8  ldarg.0
0x109a9  ldnull
0x109aa  call     instance void Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelRequest::set_LayoutXml(string value)
0x109af  ldarg.0
0x109b0  ldnull
0x109b1  call     instance void Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelRequest::set_FetchXml(string value)
0x109b6  ret
```
