# Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteSignoutCookie

- ea: `0xe500`
- end: `0xe50c`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteSignoutCookie`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd940`

## callees

- `0xe410`

## string_xrefs

- `0xe501`: `MSISSignOut`

## pseudocode

```c

```

## disassembly

```asm
0xe500  ldarg.0
0xe501  ldstr    aMsissignout// "MSISSignOut"
0xe506  call     instance void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteFedCookie(string name)
0xe50b  ret
```
