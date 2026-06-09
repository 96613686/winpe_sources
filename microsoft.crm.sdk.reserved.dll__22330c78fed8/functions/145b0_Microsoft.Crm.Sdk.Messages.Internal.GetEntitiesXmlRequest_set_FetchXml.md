# Microsoft.Crm.Sdk.Messages.Internal.GetEntitiesXmlRequest::set_FetchXml

- ea: `0x145b0`
- end: `0x145c2`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetEntitiesXmlRequest::set_FetchXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x145d0`

## string_xrefs

- `0x145b6`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x145b0  ldarg.0
0x145b1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x145b6  ldstr    aFetchxml// "FetchXml"
0x145bb  ldarg.1
0x145bc  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x145c1  ret
```
