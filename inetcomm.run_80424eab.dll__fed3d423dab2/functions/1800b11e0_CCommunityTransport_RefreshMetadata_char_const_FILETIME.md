# CCommunityTransport::RefreshMetadata(char const *,_FILETIME *)

- ea: `0x1800b11e0`
- end: `0x1800b144e`
- name: `?RefreshMetadata@CCommunityTransport@@UEAAJPEBDPEAU_FILETIME@@@Z`
- size: `622`
- prototype: `__int64 __fastcall(CCommunityTransport *__hidden this, const char *, FILETIME *lpFileTime)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012cd0`
- `0x180022420`
- `0x1800247c8`
- `0x180090860`
- `0x1800adca0`
- `0x1800b11e0`
- `0x1800b1ad4`
- `0x1800c9fe8`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!FileTimeToSystemTime` at `0x1800b1297`
- `KERNEL32!FileTimeToSystemTime` at `0x1800b1297`
- `KERNEL32!LeaveCriticalSection` at `0x1800b1406`
- `KERNEL32!LeaveCriticalSection` at `0x1800b1406`
- `KERNEL32!EnterCriticalSection` at `0x1800b122a`
- `KERNEL32!EnterCriticalSection` at `0x1800b122a`
- `KERNEL32!GetDateFormatA` at `0x1800b12c4`
- `KERNEL32!GetDateFormatA` at `0x1800b12c4`
- `KERNEL32!GetTimeFormatA` at `0x1800b12e9`
- `KERNEL32!GetTimeFormatA` at `0x1800b12e9`

## string_xrefs

- `0x1800b1382`: `<Query xmlns="http://microsoft.com/Microsoft.MSCOM.Communities.Discussions/"><sXsd>%s</sXsd><eExpType>0</eExpType><sExpression>%s</sExpression>%s</Query>`

## pseudocode

```c

```
