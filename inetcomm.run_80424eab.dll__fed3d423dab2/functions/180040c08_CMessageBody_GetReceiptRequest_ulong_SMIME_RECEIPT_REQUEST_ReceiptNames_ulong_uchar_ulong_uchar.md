# CMessageBody::_GetReceiptRequest(ulong,_SMIME_RECEIPT_REQUEST * *,ReceiptNames *,ulong *,uchar * *,ulong *,uchar * *)

- ea: `0x180040c08`
- end: `0x180041275`
- name: `?_GetReceiptRequest@CMessageBody@@AEAAJKPEAPEAU_SMIME_RECEIPT_REQUEST@@PEAUReceiptNames@@PEAKPEAPEAE23@Z`
- size: `1645`
- prototype: `__int64 __fastcall(CMessageBody *__hidden this, unsigned int, struct _SMIME_RECEIPT_REQUEST **, struct ReceiptNames *, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003cd00`
- `0x18003e090`
- `0x180040c08`

## callees

- `0x18000deac`
- `0x180040c08`
- `0x180041ee0`
- `0x18004218c`
- `0x1800cc996`
- `0x1800cc9a2`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!lstrcmpA` at `0x180040d8e`
- `KERNEL32!lstrcmpA` at `0x180041100`
- `KERNEL32!lstrcmpA` at `0x180041121`
- `KERNEL32!lstrcmpA` at `0x180040d8e`
- `KERNEL32!lstrcmpA` at `0x180041100`
- `KERNEL32!lstrcmpA` at `0x180041121`
- `CRYPT32!CryptDecodeObjectEx` at `0x180040e75`
- `CRYPT32!CryptDecodeObjectEx` at `0x180041173`
- `CRYPT32!CryptDecodeObjectEx` at `0x180040e75`
- `CRYPT32!CryptDecodeObjectEx` at `0x180041173`

## string_xrefs

- `0x180040c9b`: `y-security`

## pseudocode

```c

```
