# Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::WriteSignedOutCookie

- ea: `0xe510`
- end: `0xe51c`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::WriteSignedOutCookie`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xe520`

## callees

- `0xe470`

## string_xrefs

- `0xe511`: `MSISSignOut`

## pseudocode

```c

```

## disassembly

```asm
0xe510  ldarg.0
0xe511  ldstr    aMsissignout// "MSISSignOut"
0xe516  call     instance void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::WriteFedCookie(string name)
0xe51b  ret
```
