# CLUAMoniker::CreateInstance(_GUID const &,IUnknown *,ulong,ulong,ulong,tagMULTI_QI *)

- ea: `0x180056cd0`
- end: `0x180056ef6`
- name: `?CreateInstance@CLUAMoniker@@UEAAJAEBU_GUID@@PEAUIUnknown@@KKKPEAUtagMULTI_QI@@@Z`
- size: `550`
- prototype: `HRESULT __fastcall(CLUAMoniker *this, const _GUID *pClassID, IUnknown *pUnkOuter, unsigned int dwClsContext, unsigned int locale, unsigned int cmq, tagMULTI_QI *pResults)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180056cd0`
- `0x1800d8010`

## import_xrefs

- `USER32!GetActiveWindow` at `0x180056de8`
- `USER32!GetActiveWindow` at `0x180056de8`
- `USER32!IsWindowEnabled` at `0x180056e2b`
- `USER32!IsWindowEnabled` at `0x180056e2b`
- `USER32!EnableWindow` at `0x180056e8e`
- `USER32!EnableWindow` at `0x180056e8e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180056da3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180056da3`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180056d26`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180056d26`

## pseudocode

```c

```
