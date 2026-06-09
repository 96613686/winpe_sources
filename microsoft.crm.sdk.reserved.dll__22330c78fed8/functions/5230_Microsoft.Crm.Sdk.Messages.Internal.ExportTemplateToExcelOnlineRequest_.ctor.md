# Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelOnlineRequest::.ctor

- ea: `0x5230`
- end: `0x525e`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelOnlineRequest::.ctor`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x5120`
- `0x5170`
- `0x51c0`
- `0x5210`

## string_xrefs

- `0x5237`: `ExportTemplateToExcelOnline`

## pseudocode

```c

```

## disassembly

```asm
0x5230  ldarg.0
0x5231  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x5236  ldarg.0
0x5237  ldstr    aExporttemplate_0// "ExportTemplateToExcelOnline"
0x523c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x5241  ldarg.0
0x5242  ldnull
0x5243  call     instance void Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelOnlineRequest::set_Template(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x5248  ldarg.0
0x5249  ldnull
0x524a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelOnlineRequest::set_FetchXml(string value)
0x524f  ldarg.0
0x5250  ldnull
0x5251  call     instance void Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelOnlineRequest::set_QueryApi(string value)
0x5256  ldarg.0
0x5257  ldnull
0x5258  call     instance void Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelOnlineRequest::set_QueryParameters(class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection value)
0x525d  ret
```
