# DnsConnectionManager::MatchPolicyRule(ushort const *,ushort const *,_SID *,ulong,DnsHostPolicySuffixRule * *)

- ea: `0x18003fcf4`
- end: `0x18003fe02`
- name: `?MatchPolicyRule@DnsConnectionManager@@AEAAJPEBG0PEAU_SID@@KPEAPEAVDnsHostPolicySuffixRule@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, const unsigned __int16 *, const unsigned __int16 *, struct _SID *, unsigned int, struct DnsHostPolicySuffixRule **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003deb0`
- `0x18003e99c`

## callees

- `0x18003fcf4`
- `0x18003fe10`
- `0x1800dc9e0`
- `0x1800ddfa8`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003fd1b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003fd1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003fd71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003fd71`

## pseudocode

```c

```
