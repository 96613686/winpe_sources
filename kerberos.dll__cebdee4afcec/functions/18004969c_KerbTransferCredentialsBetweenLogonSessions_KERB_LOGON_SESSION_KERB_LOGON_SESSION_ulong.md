# KerbTransferCredentialsBetweenLogonSessions(_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,ulong)

- ea: `0x18004969c`
- end: `0x180049f91`
- name: `?KerbTransferCredentialsBetweenLogonSessions@@YAJPEAU_KERB_LOGON_SESSION@@0K@Z`
- size: `2293`
- prototype: `__int64 __fastcall(struct _KERB_LOGON_SESSION *, struct _KERB_LOGON_SESSION *, char)`
- caller_count: `1`
- callee_count: `34`
- tags: `loader_planting`

## callers

- `0x180058590`

## callees

- `0x180004660`
- `0x1800063e8`
- `0x1800068d0`
- `0x1800069a0`
- `0x180008e18`
- `0x1800093f0`
- `0x180009afc`
- `0x18000a630`
- `0x18000b300`
- `0x18000b5c0`
- `0x18002b678`
- `0x180031f6c`
- `0x180032f70`
- `0x180037aa0`
- `0x18004969c`
- `0x18004a1cc`
- `0x180060774`
- `0x180060c04`
- `0x1800644b8`
- `0x1800654c8`
- `0x180066ee0`
- `0x18006cd70`
- `0x18006ce44`
- `0x18006d240`
- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x18008b70c`
- `0x18008f410`
- `0x180090d08`
- `0x180091024`
- `0x1800ac4b4`
- `0x1800bf338`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180049c77`
- `ntdll!RtlInitUnicodeString` at `0x180049c77`
- `ntdll!RtlReleaseResource` at `0x18004985f`
- `ntdll!RtlReleaseResource` at `0x18004985f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004982c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004982c`
- `ntdll!RtlEnterCriticalSection` at `0x180049775`
- `ntdll!RtlEnterCriticalSection` at `0x1800497f6`
- `ntdll!RtlEnterCriticalSection` at `0x180049800`
- `ntdll!RtlEnterCriticalSection` at `0x1800499d7`
- `ntdll!RtlEnterCriticalSection` at `0x180049d13`
- `ntdll!RtlEnterCriticalSection` at `0x180049d1d`
- `ntdll!RtlEnterCriticalSection` at `0x180049e1d`
- `ntdll!RtlEnterCriticalSection` at `0x180049e27`
- `ntdll!RtlEnterCriticalSection` at `0x180049775`
- `ntdll!RtlEnterCriticalSection` at `0x1800497f6`
- `ntdll!RtlEnterCriticalSection` at `0x180049800`
- `ntdll!RtlEnterCriticalSection` at `0x1800499d7`
- `ntdll!RtlEnterCriticalSection` at `0x180049d13`
- `ntdll!RtlEnterCriticalSection` at `0x180049d1d`
- `ntdll!RtlEnterCriticalSection` at `0x180049e1d`
- `ntdll!RtlEnterCriticalSection` at `0x180049e27`
- `ntdll!RtlLeaveCriticalSection` at `0x180049793`
- `ntdll!RtlLeaveCriticalSection` at `0x180049998`
- `ntdll!RtlLeaveCriticalSection` at `0x1800499a2`
- `ntdll!RtlLeaveCriticalSection` at `0x180049cad`
- `ntdll!RtlLeaveCriticalSection` at `0x180049dce`
- `ntdll!RtlLeaveCriticalSection` at `0x180049dd7`
- `ntdll!RtlLeaveCriticalSection` at `0x180049e3c`
- `ntdll!RtlLeaveCriticalSection` at `0x180049e46`
- `ntdll!RtlLeaveCriticalSection` at `0x180049793`
- `ntdll!RtlLeaveCriticalSection` at `0x180049998`
- `ntdll!RtlLeaveCriticalSection` at `0x1800499a2`
- `ntdll!RtlLeaveCriticalSection` at `0x180049cad`
- `ntdll!RtlLeaveCriticalSection` at `0x180049dce`
- `ntdll!RtlLeaveCriticalSection` at `0x180049dd7`
- `ntdll!RtlLeaveCriticalSection` at `0x180049e3c`
- `ntdll!RtlLeaveCriticalSection` at `0x180049e46`
- `KerbClientShared!KerbClientFreeSupplementalCredentials` at `0x180049f3a`
- `KerbClientShared!KerbClientFreeSupplementalCredentials` at `0x180049f3a`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x180049896`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x180049896`
- `LSASRV!LsaIEfsAcceptSmartcardCredentials` at `0x180049d6a`
- `LSASRV!LsaIEfsAcceptSmartcardCredentials` at `0x180049d6a`

## string_xrefs

- `0x1800497d4`: `Failed to duplicate ticket cache entry %x\n`

## pseudocode

```c

```
