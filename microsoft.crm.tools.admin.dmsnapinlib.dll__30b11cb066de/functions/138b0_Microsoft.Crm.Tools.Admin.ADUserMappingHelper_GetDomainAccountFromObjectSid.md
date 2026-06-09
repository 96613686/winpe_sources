# Microsoft.Crm.Tools.Admin.ADUserMappingHelper::GetDomainAccountFromObjectSid

- ea: `0x138b0`
- end: `0x138cd`
- name: `Microsoft.Crm.Tools.Admin.ADUserMappingHelper::GetDomainAccountFromObjectSid`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x13420`

## string_xrefs

- `0x138b1`: `objectSid`

## pseudocode

```c

```

## disassembly

```asm
0x138b0  ldarg.0
0x138b1  ldstr    aObjectsid// "objectSid"
0x138b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x138bb  ldarg.0
0x138bc  ldloca.s 0
0x138be  ldloca.s 1
0x138c0  call     void [Microsoft.Crm.ADUtility]Microsoft.Crm.SecurityUtils::GetAccountFromSid(unsigned int8[], string&, string&)
0x138c5  ldloc.1
0x138c6  ldloc.0
0x138c7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::.ctor(string, string)
0x138cc  ret
```
