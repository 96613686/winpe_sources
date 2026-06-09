# Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_ActivityXml

- ea: `0x15bf0`
- end: `0x15c02`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_ActivityXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15e10`

## string_xrefs

- `0x15bf6`: `ActivityXml`

## pseudocode

```c

```

## disassembly

```asm
0x15bf0  ldarg.0
0x15bf1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x15bf6  ldstr    aActivityxml// "ActivityXml"
0x15bfb  ldarg.1
0x15bfc  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x15c01  ret
```
