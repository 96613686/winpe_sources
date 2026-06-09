# WinHttpConnection::Initialize(ushort const *,ushort,WinHttpSession &)

- ea: `0x18003a368`
- end: `0x18003a636`
- name: `?Initialize@WinHttpConnection@@QEAAJPEBGGAEAVWinHttpSession@@@Z`
- size: `718`
- prototype: `int(WinHttpConnection *__hidden this, const unsigned __int16 *, unsigned __int16, struct WinHttpSession *)`
- caller_count: `9`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180064b9c`
- `0x180066f68`
- `0x180079b64`
- `0x180083dc8`
- `0x180088bac`
- `0x1800b447c`
- `0x1800b60a4`
- `0x1800b885c`
- `0x1800ba1ac`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x180011fc0`
- `0x1800307c4`
- `0x18003a368`
- `0x180043ef8`
- `0x180044d30`
- `0x18008b2a4`
- `0x18008c820`
- `0x180090e50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a588`
- `WINHTTP!WinHttpConnect` at `0x18003a579`
- `WINHTTP!WinHttpConnect` at `0x18003a579`

## string_xrefs

- `0x18003a5b1`: `EventWriteWinhttpConnectFailureEvent`
- `0x18003a5b8`: `Logger::WriteWinhttpConnectFailureEvent`
- `0x18003a4ef`: `CopyStringNullSafeW`
- `0x18003a48a`: `%s: pcszServerName is too large to be included in URL_COMPONENTS.`

## pseudocode

```c

```
