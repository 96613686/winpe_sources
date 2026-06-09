# SHGetDefaultConnectedIdentityProvider(_GUID *)

- ea: `0x1401cae30`
- end: `0x1401caf1e`
- name: `?SHGetDefaultConnectedIdentityProvider@@YAJPEAU_GUID@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140077758`

## callees

- `0x1401040e0`
- `0x1401cae30`
- `0x1401caf24`
- `0x1401caf70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401caed8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401caed8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401cae9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401cae9e`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x1401cae75`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x1401cae75`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1401cae8f`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1401caebc`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1401cae8f`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1401caebc`

## pseudocode

```c

```
