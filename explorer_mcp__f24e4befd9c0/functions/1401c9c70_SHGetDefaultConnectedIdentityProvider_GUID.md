# SHGetDefaultConnectedIdentityProvider(_GUID *)

- ea: `0x1401c9c70`
- end: `0x1401c9d81`
- name: `?SHGetDefaultConnectedIdentityProvider@@YAJPEAU_GUID@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140019b3c`

## callees

- `0x14010e160`
- `0x1401c9c70`
- `0x1401c9d88`
- `0x1401c9dd8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c9d34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c9d34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401c9cee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401c9cee`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x1401c9cb5`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x1401c9cb5`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1401c9cd9`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1401c9d12`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1401c9cd9`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1401c9d12`

## pseudocode

```c

```
