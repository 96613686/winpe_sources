# PatchSdb_SetProxyInfo(void * &,ushort const *)

- ea: `0x180088444`
- end: `0x180088534`
- name: `?PatchSdb_SetProxyInfo@@YAKAEAPEAXPEBG@Z`
- size: `240`
- prototype: `unsigned int __fastcall(void **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180087c20`

## callees

- `0x180012920`
- `0x180088444`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800884a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800884ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800884a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800884ef`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008850f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008851e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008850f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008851e`
- `WINHTTP!WinHttpSetOption` at `0x1800884e5`
- `WINHTTP!WinHttpSetOption` at `0x1800884e5`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18008849e`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18008849e`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180088490`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180088490`

## pseudocode

```c

```
