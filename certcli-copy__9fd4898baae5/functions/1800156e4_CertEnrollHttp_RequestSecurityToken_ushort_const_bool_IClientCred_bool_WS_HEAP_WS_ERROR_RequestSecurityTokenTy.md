# CertEnrollHttp::RequestSecurityToken(ushort const *,bool,IClientCred *,bool,_WS_HEAP *,_WS_ERROR *,RequestSecurityTokenType *,RequestSecurityTokenResponseType * *)

- ea: `0x1800156e4`
- end: `0x1800158a3`
- name: `?RequestSecurityToken@CertEnrollHttp@@YAJPEBG_NPEAUIClientCred@@1PEAU_WS_HEAP@@PEAU_WS_ERROR@@PEAURequestSecurityTokenType@@PEAPEAURequestSecurityTokenResponseType@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(CertEnrollHttp *this, const unsigned __int16 *, struct IClientCred *, struct IClientCred *, WS_HEAP *heap, struct _WS_HEAP *error, struct _WS_ERROR *, struct RequestSecurityTokenType *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180014cac`
- `0x18001506c`

## callees

- `0x18001418c`
- `0x1800144cc`
- `0x1800156e4`
- `0x18001e5f8`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001570e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001570e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001588a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001588a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800157a0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800157a0`
- `webservices!WsCall` at `0x180015836`
- `webservices!WsCall` at `0x180015836`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x1800157aa`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x1800157aa`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001573c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180015773`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001573c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180015773`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18001585f`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18001585f`

## pseudocode

```c

```
