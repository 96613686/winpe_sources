# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180184fd4`
- end: `0x180185078`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `164`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180184f48`

## callees

- `0x180184fd4`
- `0x1801a132c`
- `0x1801ad380`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180185053`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180185053`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180185023`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180185023`

## pseudocode

```c

```
