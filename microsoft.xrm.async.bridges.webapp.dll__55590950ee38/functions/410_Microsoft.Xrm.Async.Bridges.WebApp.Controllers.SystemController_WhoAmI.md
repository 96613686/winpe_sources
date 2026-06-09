# Microsoft.Xrm.Async.Bridges.WebApp.Controllers.SystemController::WhoAmI

- ea: `0x410`
- end: `0x427`
- name: `Microsoft.Xrm.Async.Bridges.WebApp.Controllers.SystemController::WhoAmI`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x300`

## pseudocode

```c

```

## disassembly

```asm
0x410  ldarg.0
0x411  ldarg.0
0x412  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x417  isinst   [mscorlib]System.Security.Claims.ClaimsPrincipal
0x41c  newobj   instance void Microsoft.Xrm.Async.Bridges.WebApp.Models.WhoAmIMessage::.ctor(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal)
0x421  callvirt T0x2B000011
0x426  ret
```
