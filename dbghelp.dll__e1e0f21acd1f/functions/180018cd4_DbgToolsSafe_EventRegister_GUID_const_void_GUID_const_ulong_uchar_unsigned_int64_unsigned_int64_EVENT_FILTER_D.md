# DbgToolsSafe_EventRegister(_GUID const *,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *),void *,unsigned __int64 *)

- ea: `0x180018cd4`
- end: `0x180018d3b`
- name: `?DbgToolsSafe_EventRegister@@YAKPEBU_GUID@@P6AX0KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z3PEA_K@Z`
- size: `103`
- prototype: `unsigned int __fastcall(const struct _GUID *, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *), void *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180018c3c`

## callees

- `0x180018cd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018d2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018d2c`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180018cfa`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180018cfa`

## pseudocode

```c

```
