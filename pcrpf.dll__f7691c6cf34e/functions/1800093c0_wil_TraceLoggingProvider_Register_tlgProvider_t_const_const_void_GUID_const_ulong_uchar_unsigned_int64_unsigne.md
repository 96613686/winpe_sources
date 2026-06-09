# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x1800093c0`
- end: `0x18000948b`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `203`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800066d0`
- `0x18000de98`

## callees

- `0x180003270`
- `0x1800093c0`
- `0x180059010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000942d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000942d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000944b`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000944b`

## pseudocode

```c

```
