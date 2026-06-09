# Microsoft.Crm.Sdk.Messages.Internal.CreateOrUpdateImportMapFromAppRequest::set_MapXml

- ea: `0x6490`
- end: `0x64a2`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateOrUpdateImportMapFromAppRequest::set_MapXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x6500`

## string_xrefs

- `0x6496`: `MapXml`

## pseudocode

```c

```

## disassembly

```asm
0x6490  ldarg.0
0x6491  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x6496  ldstr    aMapxml// "MapXml"
0x649b  ldarg.1
0x649c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x64a1  ret
```
