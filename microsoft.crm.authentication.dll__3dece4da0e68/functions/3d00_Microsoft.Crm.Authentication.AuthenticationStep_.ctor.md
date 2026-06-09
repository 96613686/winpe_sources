# Microsoft.Crm.Authentication.AuthenticationStep::.ctor

- ea: `0x3d00`
- end: `0x3d2b`
- name: `Microsoft.Crm.Authentication.AuthenticationStep::.ctor`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4dc0`

## callees

- `0x4790`

## string_xrefs

- `0x3d12`: `providerXml`

## pseudocode

```c

```

## disassembly

```asm
0x3d00  ldarg.0
0x3d01  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::.ctor()
0x3d06  ldarg.1
0x3d07  ldstr    aPredicate// "predicate"
0x3d0c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3d11  ldarg.2
0x3d12  ldstr    aProviderxml// "providerXml"
0x3d17  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3d1c  ldarg.0
0x3d1d  ldarg.1
0x3d1e  stfld    class Microsoft.Crm.Authentication.IAuthenticationPredicate Microsoft.Crm.Authentication.AuthenticationStep::_predicate
0x3d23  ldarg.0
0x3d24  ldarg.2
0x3d25  stfld    class Microsoft.Crm.Authentication.AuthenticationProviderXml Microsoft.Crm.Authentication.AuthenticationStep::_providerXml
0x3d2a  ret
```
