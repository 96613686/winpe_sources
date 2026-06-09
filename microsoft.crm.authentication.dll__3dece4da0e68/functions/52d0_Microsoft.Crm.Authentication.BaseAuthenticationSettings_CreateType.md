# Microsoft.Crm.Authentication.BaseAuthenticationSettings::CreateType

- ea: `0x52d0`
- end: `0x52d8`
- name: `Microsoft.Crm.Authentication.BaseAuthenticationSettings::CreateType`
- size: `8`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5290`
- `0x52b0`

## callees

- `0x2110`

## pseudocode

```c

```

## disassembly

```asm
0x52d0  ldarg.0
0x52d1  ldarg.1
0x52d2  call     object Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::CreateType(string typeName, class [mscorlib]System.Type requiredBaseType)
0x52d7  ret
```
