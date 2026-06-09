# NlDomainScavenger(_DOMAIN_INFO *,void *)

- ea: `0x18006e960`
- end: `0x18006ec9f`
- name: `?NlDomainScavenger@@YAKPEAU_DOMAIN_INFO@@PEAX@Z`
- size: `831`
- prototype: `unsigned int __fastcall(struct _DOMAIN_INFO *, void *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003ac0`
- `0x18000bcec`
- `0x18000bd98`
- `0x18000da94`
- `0x18002707c`
- `0x180027870`
- `0x1800291f4`
- `0x18002c400`
- `0x180033a34`
- `0x18003e71c`
- `0x1800536e4`
- `0x180066904`
- `0x1800675c0`
- `0x1800694d0`
- `0x18006e960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006ec50`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006ec50`
- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x18006e9b8`
- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x18006e9b8`
- `ntdll!RtlLeaveCriticalSection` at `0x18006ea8e`
- `ntdll!RtlLeaveCriticalSection` at `0x18006eb5a`
- `ntdll!RtlLeaveCriticalSection` at `0x18006ebef`
- `ntdll!RtlLeaveCriticalSection` at `0x18006ea8e`
- `ntdll!RtlLeaveCriticalSection` at `0x18006eb5a`
- `ntdll!RtlLeaveCriticalSection` at `0x18006ebef`
- `ntdll!RtlEnterCriticalSection` at `0x18006ea0e`
- `ntdll!RtlEnterCriticalSection` at `0x18006eb3f`
- `ntdll!RtlEnterCriticalSection` at `0x18006eba0`
- `ntdll!RtlEnterCriticalSection` at `0x18006ea0e`
- `ntdll!RtlEnterCriticalSection` at `0x18006eb3f`
- `ntdll!RtlEnterCriticalSection` at `0x18006eba0`
- `gmsaclient!GMSARefreshPasswords` at `0x18006e9c4`
- `gmsaclient!GMSARefreshPasswords` at `0x18006e9c4`
- `netutils!NetApiBufferFree` at `0x18006eb19`
- `netutils!NetApiBufferFree` at `0x18006eb19`

## string_xrefs

- `0x18006eac7`: `NlDomainScavenger: Can't become writer of client session.\n`
- `0x18006ec15`: `DomainScavenger: Try again to update the role.\n`
- `0x18006ec5d`: `DomainScavenger: Try again to update the trusted domain list.\n`

## pseudocode

```c

```
