# URL::accessAllowed(bool,IInternetSecurityManager *,ushort const *,ushort const *,ushort const *,bool)

- ea: `0x1013104f`
- end: `0x101313eb`
- name: `?accessAllowed@URL@@SGJ_NPAUIInternetSecurityManager@@PBG220@Z`
- size: `924`
- prototype: `HRESULT __fastcall(bool fSecure, IInternetSecurityManager *pSecMgr, wchar_t *pwszReqUrl, const wchar_t *pwszBaseUrl, const wchar_t *pwszSecureUrl, bool fZoneRelaxed)`
- caller_count: `8`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x10050030`
- `0x10131880`
- `0x101344e3`
- `0x1013d05c`
- `0x1013e020`
- `0x1013e680`
- `0x1013e790`
- `0x1013ebf0`

## callees

- `0x1004fbae`
- `0x10067b20`
- `0x1006b470`
- `0x100762d2`
- `0x10131009`
- `0x1013104f`
- `0x10170cd0`
- `0x10171298`
- `0x101712a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x101313bb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x101313bb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1013131e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1013131e`

## pseudocode

```c

```
