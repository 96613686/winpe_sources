# ActiveDirectoryHelper::DomainDnsNameFromDomainName(ushort const *,ushort * *,unsigned __int64 *)

- ea: `0x18009280c`
- end: `0x180092b12`
- name: `?DomainDnsNameFromDomainName@ActiveDirectoryHelper@@AEAAJPEBGPEAPEAGPEA_K@Z`
- size: `774`
- prototype: `__int64 __fastcall(ActiveDirectoryHelper *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18009328c`

## callees

- `0x180001aa0`
- `0x180038984`
- `0x18004a888`
- `0x1800787d4`
- `0x180078820`
- `0x18009280c`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x180092aed`
- `netutils!NetApiBufferFree` at `0x180092aed`
- `logoncli!DsGetDcNameW` at `0x180092852`
- `logoncli!DsGetDcNameW` at `0x180092852`

## string_xrefs

- `0x1800928a2`: `onecore\termsrv\rdp\win\security\activedirectoryhelper.cpp`
- `0x18009294a`: `onecore\termsrv\rdp\win\security\activedirectoryhelper.cpp`
- `0x1800929fc`: `onecore\termsrv\rdp\win\security\activedirectoryhelper.cpp`
- `0x180092a90`: `onecore\termsrv\rdp\win\security\activedirectoryhelper.cpp`
- `0x180092a6c`: `StringCchCopy failed`

## pseudocode

```c

```
