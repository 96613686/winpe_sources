# CLUAMoniker::CreateInstance(_GUID const &,IUnknown *,ulong,ulong,ulong,tagMULTI_QI *)

- ea: `0x18003e9e0`
- end: `0x18003ebed`
- name: `?CreateInstance@CLUAMoniker@@UEAAJAEBU_GUID@@PEAUIUnknown@@KKKPEAUtagMULTI_QI@@@Z`
- size: `525`
- prototype: `HRESULT __fastcall(CLUAMoniker *this, const _GUID *pClassID, IUnknown *pUnkOuter, unsigned int dwClsContext, unsigned int locale, unsigned int cmq, tagMULTI_QI *pResults)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18003e9e0`
- `0x18003ee6c`
- `0x1800ce010`

## import_xrefs

- `USER32!GetActiveWindow` at `0x18003eaef`
- `USER32!GetActiveWindow` at `0x18003eaef`
- `USER32!IsWindowEnabled` at `0x18003eb2f`
- `USER32!IsWindowEnabled` at `0x18003eb2f`
- `USER32!EnableWindow` at `0x18003eb8d`
- `USER32!EnableWindow` at `0x18003eb8d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003eab2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003eab2`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18003ea2e`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18003ea2e`

## pseudocode

```c

```
