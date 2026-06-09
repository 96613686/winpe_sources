# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180018030`
- end: `0x1800181d3`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `419`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, __int64, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180017f54`

## callees

- `0x18001715c`
- `0x180018030`
- `0x18001c110`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800180fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800180fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001814c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001814c`

## pseudocode

```c

```
