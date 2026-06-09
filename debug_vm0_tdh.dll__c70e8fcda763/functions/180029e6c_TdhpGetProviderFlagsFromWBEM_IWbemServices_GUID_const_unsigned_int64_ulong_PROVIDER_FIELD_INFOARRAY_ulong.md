# TdhpGetProviderFlagsFromWBEM(IWbemServices *,_GUID const *,unsigned __int64,ulong,_PROVIDER_FIELD_INFOARRAY *,ulong *)

- ea: `0x180029e6c`
- end: `0x180029efe`
- name: `?TdhpGetProviderFlagsFromWBEM@@YAKPEAUIWbemServices@@PEBU_GUID@@_KKPEAU_PROVIDER_FIELD_INFOARRAY@@PEAK@Z`
- size: `146`
- prototype: `unsigned int __usercall@<eax>(struct IWbemServices *@<rcx>, const struct _GUID *@<rdx>, unsigned __int64@<r8>, unsigned int@<r9d>, struct _PROVIDER_FIELD_INFOARRAY *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800172a0`
- `0x18002b4e0`

## callees

- `0x1800064d0`
- `0x1800076e0`
- `0x18000c740`
- `0x180029e6c`
- `0x18002ac2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180029e98`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180029e98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029edc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029edc`

## pseudocode

```c

```
