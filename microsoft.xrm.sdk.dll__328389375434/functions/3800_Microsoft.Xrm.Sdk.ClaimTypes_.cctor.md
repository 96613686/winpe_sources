# Microsoft.Xrm.Sdk.ClaimTypes::.cctor

- ea: `0x3800`
- end: `0x3851`
- name: `Microsoft.Xrm.Sdk.ClaimTypes::.cctor`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x3800`: `http://schemas.microsoft.com/xrm/2011/Claims/Organization`
- `0x380a`: `http://schemas.microsoft.com/xrm/2011/Claims/User`
- `0x3814`: `http://schemas.microsoft.com/xrm/2011/Claims/InitiatingUser`
- `0x381e`: `http://schemas.microsoft.com/xrm/2011/Claims/PluginAssembly`
- `0x3828`: `http://schemas.microsoft.com/xrm/2011/Claims/PluginPublisher`
- `0x3832`: `http://schemas.microsoft.com/xrm/2011/Claims/EntityLogicalName`
- `0x383c`: `http://schemas.microsoft.com/xrm/2011/Claims/RequestName`
- `0x3846`: `http://schemas.microsoft.com/xrm/2011/Claims/SecurityToken`

## pseudocode

```c

```

## disassembly

```asm
0x3800  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/xrm/2011/C"...
0x3805  stsfld   string Microsoft.Xrm.Sdk.ClaimTypes::Organization
0x380a  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/xrm/2011/C"...
0x380f  stsfld   string Microsoft.Xrm.Sdk.ClaimTypes::User
0x3814  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/xrm/2011/C"...
0x3819  stsfld   string Microsoft.Xrm.Sdk.ClaimTypes::InitiatingUser
0x381e  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/xrm/2011/C"...
0x3823  stsfld   string Microsoft.Xrm.Sdk.ClaimTypes::PluginAssembly
0x3828  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/xrm/2011/C"...
0x382d  stsfld   string Microsoft.Xrm.Sdk.ClaimTypes::PluginPublisher
0x3832  ldstr    aHttpSchemasMic_5// "http://schemas.microsoft.com/xrm/2011/C"...
0x3837  stsfld   string Microsoft.Xrm.Sdk.ClaimTypes::EntityLogicalName
0x383c  ldstr    aHttpSchemasMic_6// "http://schemas.microsoft.com/xrm/2011/C"...
0x3841  stsfld   string Microsoft.Xrm.Sdk.ClaimTypes::RequestName
0x3846  ldstr    aHttpSchemasMic_7// "http://schemas.microsoft.com/xrm/2011/C"...
0x384b  stsfld   string Microsoft.Xrm.Sdk.ClaimTypes::SecurityToken
0x3850  ret
```
