# Microsoft.Crm.Authentication.Telemetry.CrmSessionAuthenticationType::.ctor

- ea: `0x7270`
- end: `0x727e`
- name: `Microsoft.Crm.Authentication.Telemetry.CrmSessionAuthenticationType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x7271`: `CrmSessionAuthenticationManager_AuthenticateSessionSecurityToken`

## pseudocode

```c

```

## disassembly

```asm
0x7270  ldarg.0
0x7271  ldstr    aCrmsessionauth// "CrmSessionAuthenticationManager_Authent"...
0x7276  ldc.i4.1
0x7277  ldc.i4.1
0x7278  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Authentication.Telemetry.CrmSessionAuthenticationType>::.ctor(string, bool, bool)
0x727d  ret
```
