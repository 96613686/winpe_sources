# Microsoft.Crm.Sdk.Messages.Internal.GetFieldAndPropertiesXmlRequest::set_FetchXml

- ea: `0x14490`
- end: `0x144a2`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetFieldAndPropertiesXmlRequest::set_FetchXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x144b0`

## string_xrefs

- `0x14496`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x14490  ldarg.0
0x14491  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14496  ldstr    aFetchxml// "FetchXml"
0x1449b  ldarg.1
0x1449c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x144a1  ret
```
