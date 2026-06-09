# Microsoft.Xrm.Sdk.Client.LiveIdAuthenticationConfiguration::.cctor

- ea: `0x182c0`
- end: `0x182fd`
- name: `Microsoft.Xrm.Sdk.Client.LiveIdAuthenticationConfiguration::.cctor`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x182de`: `http://schemas.xmlsoap.org/ws/2004/09/policy`
- `0x182e8`: `http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd`

## pseudocode

```c

```

## disassembly

```asm
0x182c0  ldstr    aUrnLiveidDevic// "urn:liveid:device"
0x182c5  stsfld   string Microsoft.Xrm.Sdk.Client.LiveIdAuthenticationConfiguration::DeviceTokenId
0x182ca  ldstr    aUser// "user"
0x182cf  stsfld   string Microsoft.Xrm.Sdk.Client.LiveIdAuthenticationConfiguration::UserNameTokenId
0x182d4  ldstr    aDevicesoftware// "devicesoftware"
0x182d9  stsfld   string Microsoft.Xrm.Sdk.Client.LiveIdAuthenticationConfiguration::DeviceUserNameTokenId
0x182de  ldstr    aHttpSchemasXml_1// "http://schemas.xmlsoap.org/ws/2004/09/p"...
0x182e3  stsfld   string Microsoft.Xrm.Sdk.Client.LiveIdAuthenticationConfiguration::PolicyReference
0x182e8  ldstr    aHttpDocsOasisO_1// "http://docs.oasis-open.org/wss/2004/01/"...
0x182ed  stsfld   string Microsoft.Xrm.Sdk.Client.LiveIdAuthenticationConfiguration::SecurityTokenSchema
0x182f2  ldstr    aMbiFedSsl// "MBI_FED_SSL"
0x182f7  stsfld   string Microsoft.Xrm.Sdk.Client.LiveIdAuthenticationConfiguration::DefaultPolicy
0x182fc  ret
```
