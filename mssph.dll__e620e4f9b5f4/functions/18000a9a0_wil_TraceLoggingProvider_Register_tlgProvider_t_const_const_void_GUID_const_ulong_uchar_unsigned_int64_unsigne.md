# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x18000a9a0`
- end: `0x18000aa58`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `184`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001684c`

## callees

- `0x18000a9a0`
- `0x18000fcd0`
- `0x180027010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000aa04`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000aa04`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000aa1f`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000aa1f`

## pseudocode

```c

```
