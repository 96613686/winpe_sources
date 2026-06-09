# URL::accessAllowed(bool,IInternetSecurityManager *,ushort const *,ushort const *,ushort const *,bool)

- ea: `0x10130f3f`
- end: `0x101312db`
- name: `?accessAllowed@URL@@SGJ_NPAUIInternetSecurityManager@@PBG220@Z`
- size: `924`
- prototype: `HRESULT __fastcall(bool fSecure, IInternetSecurityManager *pSecMgr, wchar_t *pwszReqUrl, const wchar_t *pwszBaseUrl, const wchar_t *pwszSecureUrl, bool fZoneRelaxed)`
- caller_count: `8`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x100500c0`
- `0x10131770`
- `0x101343d3`
- `0x1013cf4c`
- `0x1013df10`
- `0x1013e570`
- `0x1013e680`
- `0x1013eae0`

## callees

- `0x1004fc3e`
- `0x10067bc0`
- `0x1006b510`
- `0x100762a2`
- `0x10130ef9`
- `0x10130f3f`
- `0x10170be0`
- `0x101711a8`
- `0x101711b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x101312ab`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x101312ab`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1013120e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1013120e`

## pseudocode

```c

```
