# Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::get_NonceCookieHandler

- ea: `0x94e0`
- end: `0x94f9`
- name: `Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::get_NonceCookieHandler`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x9500`
- `0x9550`

## callees

- `0x8f30`
- `0x94e0`

## pseudocode

```c

```

## disassembly

```asm
0x94e0  ldarg.0
0x94e1  ldfld    class Microsoft.Crm.Authentication.Claims.INonceCookieHandler Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_nonceCookieHandler
0x94e6  dup
0x94e7  brtrue.s loc_94F8
0x94e9  pop
0x94ea  ldarg.0
0x94eb  newobj   instance void Microsoft.Crm.Authentication.Claims.NonceCookieHandler::.ctor()
0x94f0  dup
0x94f1  stloc.0
0x94f2  stfld    class Microsoft.Crm.Authentication.Claims.INonceCookieHandler Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_nonceCookieHandler
0x94f7  ldloc.0
0x94f8  ret
```
