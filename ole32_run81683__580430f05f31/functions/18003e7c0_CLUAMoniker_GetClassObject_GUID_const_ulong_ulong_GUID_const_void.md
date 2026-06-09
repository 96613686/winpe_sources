# CLUAMoniker::GetClassObject(_GUID const &,ulong,ulong,_GUID const &,void * *)

- ea: `0x18003e7c0`
- end: `0x18003e9cb`
- name: `?GetClassObject@CLUAMoniker@@UEAAJAEBU_GUID@@KK0PEAPEAX@Z`
- size: `523`
- prototype: `HRESULT __fastcall(CLUAMoniker *this, const _GUID *pClassID, unsigned int dwClsContext, unsigned int locale, const _GUID *riid, void **ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18003e7c0`
- `0x18003ee6c`
- `0x1800ce010`

## import_xrefs

- `USER32!GetActiveWindow` at `0x18003e8d8`
- `USER32!GetActiveWindow` at `0x18003e8d8`
- `USER32!IsWindowEnabled` at `0x18003e918`
- `USER32!IsWindowEnabled` at `0x18003e918`
- `USER32!EnableWindow` at `0x18003e96b`
- `USER32!EnableWindow` at `0x18003e96b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003e89b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003e89b`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18003e817`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18003e817`

## pseudocode

```c

```
