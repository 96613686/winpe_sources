# CWAMTokenHandler::RestoreWebAccountId(ushort *,ushort *,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,int)

- ea: `0x1805de9cc`
- end: `0x1805df0d4`
- name: `?RestoreWebAccountId@CWAMTokenHandler@@AEAAJPEAG00AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z`
- size: `1800`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1805e2bac`

## callees

- `0x1800011f4`
- `0x1800031a8`
- `0x1800054f4`
- `0x180005ccc`
- `0x18000e348`
- `0x1800829d4`
- `0x180082ad8`
- `0x180085e04`
- `0x180129620`
- `0x180129678`
- `0x1805de9cc`
- `0x1805dfc7c`
- `0x180688f3e`
- `0x180688f86`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1805df026`
- `KERNEL32!GetLastError` at `0x1805df026`
- `KERNEL32!LocalFree` at `0x1805defac`
- `KERNEL32!LocalFree` at `0x1805defbb`
- `KERNEL32!LocalFree` at `0x1805defac`
- `KERNEL32!LocalFree` at `0x1805defbb`
- `ADVAPI32!RegGetValueW` at `0x1805dec67`
- `ADVAPI32!RegGetValueW` at `0x1805deda1`
- `ADVAPI32!RegGetValueW` at `0x1805dedf7`
- `ADVAPI32!RegGetValueW` at `0x1805dec67`
- `ADVAPI32!RegGetValueW` at `0x1805deda1`
- `ADVAPI32!RegGetValueW` at `0x1805dedf7`
- `CRYPT32!CryptUnprotectData` at `0x1805deec3`
- `CRYPT32!CryptUnprotectData` at `0x1805deec3`

## string_xrefs

- `0x1805deb0b`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.cpp`
- `0x1805deba0`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.cpp`
- `0x1805dece8`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.cpp`
- `0x1805dee4b`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.cpp`
- `0x1805df080`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.cpp`
- `0x1805dec17`: `Reading web account ID from ClientID based registry path`
- `0x1805ded51`: `Reading web account ID from legacy registry path`
- `0x1805def07`: `Token descriptions don't match.`
- `0x1805deb1b`: `Registry path is too long`

## pseudocode

```c

```
