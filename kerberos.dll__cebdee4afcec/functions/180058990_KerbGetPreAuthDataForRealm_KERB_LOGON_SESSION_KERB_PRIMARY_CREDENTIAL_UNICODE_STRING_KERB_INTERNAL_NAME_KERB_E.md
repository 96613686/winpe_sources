# KerbGetPreAuthDataForRealm(_KERB_LOGON_SESSION *,_KERB_PRIMARY_CREDENTIAL *,_UNICODE_STRING *,_KERB_INTERNAL_NAME *,_KERB_ENCRYPTION_KEY *,KERB_KDC_REQUEST_preauth_data_s *,_LARGE_INTEGER *,uchar,uchar,long,uchar,uchar *,KERB_KDC_REQUEST_preauth_data_s * *,_KERB_ENCRYPTION_KEY *,KERB_KDC_REQUEST_BODY *,_KERB_MESSAGE_BUFFER *,ulong *,KerbKeyAgreement * *)

- ea: `0x180058990`
- end: `0x180058f0d`
- name: `?KerbGetPreAuthDataForRealm@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_PRIMARY_CREDENTIAL@@PEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@PEAU_KERB_ENCRYPTION_KEY@@PEAUKERB_KDC_REQUEST_preauth_data_s@@PEAT_LARGE_INTEGER@@EEJEPEAEPEAPEAU6@4PEAUKERB_KDC_REQUEST_BODY@@PEAU_KERB_MESSAGE_BUFFER@@PEAKPEAPEAVKerbKeyAgreement@@@Z`
- size: `1405`
- prototype: `__int64 __fastcall(struct _KERB_LOGON_SESSION *, struct _KERB_PRIMARY_CREDENTIAL *, struct _UNICODE_STRING *, struct _KERB_INTERNAL_NAME *, struct _KERB_ENCRYPTION_KEY *, struct KERB_KDC_REQUEST_preauth_data_s *, union _LARGE_INTEGER *, unsigned __int8, unsigned __int8, int, char, bool *, struct KERB_KDC_REQUEST_preauth_data_s **, struct _KERB_ENCRYPTION_KEY *, struct KERB_KDC_REQUEST_BODY *, struct _KERB_MESSAGE_BUFFER *, struct _UNICODE_STRING *, struct KerbKeyAgreement **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180019678`

## callees

- `0x180014c50`
- `0x180029c50`
- `0x180048390`
- `0x180058990`
- `0x180070680`
- `0x18008b70c`
- `0x1800904f4`
- `0x1800a9c28`
- `0x1800b9fb4`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180058a97`
- `ntdll!RtlEnterCriticalSection` at `0x180058a97`
- `ntdll!RtlLeaveCriticalSection` at `0x180058ac8`
- `ntdll!RtlLeaveCriticalSection` at `0x180058ada`
- `ntdll!RtlLeaveCriticalSection` at `0x180058af7`
- `ntdll!RtlLeaveCriticalSection` at `0x180058ac8`
- `ntdll!RtlLeaveCriticalSection` at `0x180058ada`
- `ntdll!RtlLeaveCriticalSection` at `0x180058af7`

## string_xrefs

- `0x180058bcb`: `KerbGetPreAuthDataForRealm: KDC asked for freshness while we did not.  Update realm cache.\n`
- `0x180058d26`: `KerbGetPreAuthDataForRealm: KDC offered no freshness token which we asked for.  Update realm cache.\n`

## pseudocode

```c

```
