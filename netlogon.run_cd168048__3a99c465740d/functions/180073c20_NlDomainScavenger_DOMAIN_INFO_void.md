# NlDomainScavenger(_DOMAIN_INFO *,void *)

- ea: `0x180073c20`
- end: `0x180073f33`
- name: `?NlDomainScavenger@@YAKPEAU_DOMAIN_INFO@@PEAX@Z`
- size: `787`
- prototype: `unsigned int __fastcall(struct _DOMAIN_INFO *, void *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003ce0`
- `0x18000c440`
- `0x18000e0e0`
- `0x1800283ec`
- `0x180028c70`
- `0x18002a8e0`
- `0x18002de5c`
- `0x180035924`
- `0x180040f18`
- `0x1800570c0`
- `0x180058aa4`
- `0x18006b5b4`
- `0x18006c2e8`
- `0x18006e444`
- `0x180073c20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180073ee1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180073ee1`
- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x180073c6f`
- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x180073c6f`
- `ntdll!RtlLeaveCriticalSection` at `0x180073d52`
- `ntdll!RtlLeaveCriticalSection` at `0x180073e3e`
- `ntdll!RtlLeaveCriticalSection` at `0x180073d52`
- `ntdll!RtlLeaveCriticalSection` at `0x180073e3e`
- `ntdll!RtlEnterCriticalSection` at `0x180073ccb`
- `ntdll!RtlEnterCriticalSection` at `0x180073e1d`
- `ntdll!RtlEnterCriticalSection` at `0x180073ccb`
- `ntdll!RtlEnterCriticalSection` at `0x180073e1d`
- `gmsaclient!GMSARefreshPasswords` at `0x180073c81`
- `gmsaclient!GMSARefreshPasswords` at `0x180073c81`
- `netutils!NetApiBufferFree` at `0x180073df1`
- `netutils!NetApiBufferFree` at `0x180073df1`

## string_xrefs

- `0x180073d95`: `NlDomainScavenger: Can't become writer of client session.\n`
- `0x180073e9d`: `DomainScavenger: Try again to update the role.\n`
- `0x180073ef4`: `DomainScavenger: Try again to update the trusted domain list.\n`

## pseudocode

```c

```
