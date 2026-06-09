# Microsoft.Crm.Authentication.Claims.CrmSessionSecurityTokenHandler::.ctor

- ea: `0x9c90`
- end: `0x9c9c`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionSecurityTokenHandler::.ctor`
- size: `12`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xab70`
- `0x109c0`

## callees

- `0x9c40`
- `0x9ca0`

## pseudocode

```c

```

## disassembly

```asm
0x9c90  ldarg.0
0x9c91  call     class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.CookieTransform> Microsoft.Crm.Authentication.Claims.CrmSessionSecurityTokenHandler::get_DefaultTransforms()
0x9c96  call     instance void Microsoft.Crm.Authentication.Claims.CrmSessionSecurityTokenHandler::.ctor(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.CookieTransform> defaultTransforms)
0x9c9b  ret
```
