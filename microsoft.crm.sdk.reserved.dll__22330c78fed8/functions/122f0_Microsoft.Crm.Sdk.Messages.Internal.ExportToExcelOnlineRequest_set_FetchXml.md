# Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelOnlineRequest::set_FetchXml

- ea: `0x122f0`
- end: `0x12302`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelOnlineRequest::set_FetchXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x12400`

## string_xrefs

- `0x122f6`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x122f0  ldarg.0
0x122f1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x122f6  ldstr    aFetchxml// "FetchXml"
0x122fb  ldarg.1
0x122fc  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x12301  ret
```
