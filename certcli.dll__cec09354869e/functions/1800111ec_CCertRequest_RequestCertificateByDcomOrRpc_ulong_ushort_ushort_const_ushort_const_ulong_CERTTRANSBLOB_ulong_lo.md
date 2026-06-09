# CCertRequest::_RequestCertificateByDcomOrRpc(ulong,ushort *,ushort const *,ushort const *,ulong,_CERTTRANSBLOB *,ulong *,long *,_CERTTRANSBLOB *,_CERTTRANSBLOB *,_CERTTRANSBLOB *,_CERTTRANSBLOB *)

- ea: `0x1800111ec`
- end: `0x180011541`
- name: `?_RequestCertificateByDcomOrRpc@CCertRequest@@AEAAJKPEAGPEBG1KPEAU_CERTTRANSBLOB@@PEAKPEAJ2222@Z`
- size: `853`
- prototype: `__int64 __fastcall(CCertRequest *this, unsigned int, unsigned __int16 *, BYTE *, BYTE *, unsigned int, struct _CERTTRANSBLOB *, unsigned int *, unsigned int *, struct _CERTTRANSBLOB *, struct _CERTTRANSBLOB *, struct _CERTTRANSBLOB *, struct _CERTTRANSBLOB *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010440`
- `0x180011700`

## callees

- `0x18001053c`
- `0x1800111ec`
- `0x180011ba0`
- `0x180011e14`
- `0x18003f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001127f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001127f`
- `OLEAUT32!__imp_SysFreeString` at `0x180011525`
- `OLEAUT32!__imp_SysFreeString` at `0x180011525`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180011271`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180011271`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001151b`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001151b`

## pseudocode

```c

```
