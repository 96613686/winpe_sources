# Microsoft.Crm.Authentication.BaseAuthenticationSettings::CreatePredicate

- ea: `0x5290`
- end: `0x52ad`
- name: `Microsoft.Crm.Authentication.BaseAuthenticationSettings::CreatePredicate`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4e20`

## callees

- `0x4090`
- `0x52d0`

## pseudocode

```c

```

## disassembly

```asm
0x5290  ldarg.1
0x5291  ldtoken  Microsoft.Crm.Authentication.IAuthenticationPredicate
0x5296  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x529b  call     object Microsoft.Crm.Authentication.BaseAuthenticationSettings::CreateType(string typeName, class [mscorlib]System.Type requiredBaseType)
0x52a0  castclass Microsoft.Crm.Authentication.IAuthenticationPredicate
0x52a5  dup
0x52a6  ldarg.2
0x52a7  callvirt instance void Microsoft.Crm.Authentication.IAuthenticationPredicate::Configure(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration)
0x52ac  ret
```
