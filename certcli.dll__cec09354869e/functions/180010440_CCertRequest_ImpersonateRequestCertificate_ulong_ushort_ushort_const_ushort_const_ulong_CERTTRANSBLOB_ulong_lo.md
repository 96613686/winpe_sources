# CCertRequest::_ImpersonateRequestCertificate(ulong,ushort *,ushort const *,ushort const *,ulong,_CERTTRANSBLOB *,ulong *,long *,_CERTTRANSBLOB *,_CERTTRANSBLOB *,_CERTTRANSBLOB *,_CERTTRANSBLOB *)

- ea: `0x180010440`
- end: `0x180010535`
- name: `?_ImpersonateRequestCertificate@CCertRequest@@AEAAJKPEAGPEBG1KPEAU_CERTTRANSBLOB@@PEAKPEAJ2222@Z`
- size: `245`
- prototype: `__int64 __fastcall(CCertRequest *this, enum WELL_KNOWN_SID_TYPE, unsigned __int16 *, BYTE *, unsigned __int16 *, unsigned int, struct _CERTTRANSBLOB *, unsigned int *, unsigned int *, struct _CERTTRANSBLOB *, struct _CERTTRANSBLOB *, struct _CERTTRANSBLOB *, struct _CERTTRANSBLOB *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011700`

## callees

- `0x180010440`
- `0x1800111ec`
- `0x18001e5f8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180010509`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180010509`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x180010513`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x180010513`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800104ff`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180010522`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800104ff`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180010522`

## pseudocode

```c

```
