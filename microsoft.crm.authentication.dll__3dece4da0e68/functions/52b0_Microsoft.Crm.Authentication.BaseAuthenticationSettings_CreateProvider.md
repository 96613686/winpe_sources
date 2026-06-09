# Microsoft.Crm.Authentication.BaseAuthenticationSettings::CreateProvider

- ea: `0x52b0`
- end: `0x52cd`
- name: `Microsoft.Crm.Authentication.BaseAuthenticationSettings::CreateProvider`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3de0`
- `0x4c90`

## callees

- `0x4880`
- `0x52d0`

## pseudocode

```c

```

## disassembly

```asm
0x52b0  ldarg.0
0x52b1  ldtoken  Microsoft.Crm.Authentication.IAuthenticationProvider
0x52b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x52bb  call     object Microsoft.Crm.Authentication.BaseAuthenticationSettings::CreateType(string typeName, class [mscorlib]System.Type requiredBaseType)
0x52c0  castclass Microsoft.Crm.Authentication.IAuthenticationProvider
0x52c5  dup
0x52c6  ldarg.1
0x52c7  callvirt instance void Microsoft.Crm.Authentication.IAuthenticationProvider::Configure(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration)
0x52cc  ret
```
