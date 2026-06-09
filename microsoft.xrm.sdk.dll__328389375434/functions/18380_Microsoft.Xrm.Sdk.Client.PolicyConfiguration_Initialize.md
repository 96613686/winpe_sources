# Microsoft.Xrm.Sdk.Client.PolicyConfiguration::Initialize

- ea: `0x18380`
- end: `0x1839c`
- name: `Microsoft.Xrm.Sdk.Client.PolicyConfiguration::Initialize`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18360`

## callees

- `0x18330`
- `0x183a0`
- `0x183d0`

## string_xrefs

- `0x18387`: `SecureTokenServiceIdentifier`

## pseudocode

```c

```

## disassembly

```asm
0x18380  ldarg.0
0x18381  ldarg.0
0x18382  call     instance class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy Microsoft.Xrm.Sdk.Client.PolicyConfiguration::get_XrmPolicy()
0x18387  ldstr    aSecuretokenser// "SecureTokenServiceIdentifier"
0x1838c  ldsfld   string [mscorlib]System.String::Empty
0x18391  call     string Microsoft.Xrm.Sdk.Client.PolicyHelper::GetPolicyValue(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy, string elementName, string defaultValue)
0x18396  call     instance void Microsoft.Xrm.Sdk.Client.PolicyConfiguration::set_SecureTokenServiceIdentifier(string value)
0x1839b  ret
```
