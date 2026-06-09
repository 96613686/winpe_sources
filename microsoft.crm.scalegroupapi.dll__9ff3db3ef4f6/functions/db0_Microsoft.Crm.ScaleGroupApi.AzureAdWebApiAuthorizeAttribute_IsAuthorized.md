# Microsoft.Crm.ScaleGroupApi.AzureAdWebApiAuthorizeAttribute::IsAuthorized

- ea: `0xdb0`
- end: `0xdbb`
- name: `Microsoft.Crm.ScaleGroupApi.AzureAdWebApiAuthorizeAttribute::IsAuthorized`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xdc0`

## pseudocode

```c

```

## disassembly

```asm
0xdb0  call     class [mscorlib]System.Security.Claims.ClaimsPrincipal [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Current()
0xdb5  call     bool Microsoft.Crm.ScaleGroupApi.AzureAdWebApiAuthorizeAttribute::AuthorizeCaller(class [mscorlib]System.Security.Claims.ClaimsPrincipal caller)
0xdba  ret
```
