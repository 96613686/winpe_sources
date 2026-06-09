# CLUAMoniker::GetClassObject(_GUID const &,ulong,ulong,_GUID const &,void * *)

- ea: `0x180056f20`
- end: `0x18005713f`
- name: `?GetClassObject@CLUAMoniker@@UEAAJAEBU_GUID@@KK0PEAPEAX@Z`
- size: `543`
- prototype: `HRESULT __fastcall(CLUAMoniker *this, const _GUID *pClassID, unsigned int dwClsContext, unsigned int locale, const _GUID *riid, void **ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180056f20`
- `0x1800d8010`

## import_xrefs

- `USER32!GetActiveWindow` at `0x18005703d`
- `USER32!GetActiveWindow` at `0x18005703d`
- `USER32!IsWindowEnabled` at `0x180057080`
- `USER32!IsWindowEnabled` at `0x180057080`
- `USER32!EnableWindow` at `0x1800570d7`
- `USER32!EnableWindow` at `0x1800570d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180056ff8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180056ff8`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180056f7b`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180056f7b`

## pseudocode

```c

```
