# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x18000e740`
- end: `0x18000e7fa`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `186`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800363e8`

## callees

- `0x18000e740`
- `0x18002a3d0`
- `0x180089010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000e79d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000e79d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000e7b8`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000e7b8`

## pseudocode

```c

```
