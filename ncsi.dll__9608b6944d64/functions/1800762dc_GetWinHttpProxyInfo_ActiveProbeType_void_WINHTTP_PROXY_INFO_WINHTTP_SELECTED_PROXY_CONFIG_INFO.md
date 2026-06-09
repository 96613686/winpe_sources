# GetWinHttpProxyInfo(_ActiveProbeType,void *,_WINHTTP_PROXY_INFO *,_WINHTTP_SELECTED_PROXY_CONFIG_INFO *)

- ea: `0x1800762dc`
- end: `0x180076429`
- name: `?GetWinHttpProxyInfo@@YAXW4_ActiveProbeType@@PEAXPEAU_WINHTTP_PROXY_INFO@@PEAU_WINHTTP_SELECTED_PROXY_CONFIG_INFO@@@Z`
- size: `333`
- prototype: `void __high(enum _ActiveProbeType, void *, struct _WINHTTP_PROXY_INFO *, struct _WINHTTP_SELECTED_PROXY_CONFIG_INFO *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180076174`
- `0x180076430`

## callees

- `0x1800083a8`
- `0x1800296e8`
- `0x180047240`
- `0x1800762dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800763be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800763be`
- `WINHTTP!WinHttpQueryOption` at `0x18007633e`
- `WINHTTP!WinHttpQueryOption` at `0x1800763b4`
- `WINHTTP!WinHttpQueryOption` at `0x18007633e`
- `WINHTTP!WinHttpQueryOption` at `0x1800763b4`

## pseudocode

```c

```
